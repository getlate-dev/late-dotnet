# Zernio.Model.RecyclingState
Current recycling configuration and state on a post

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Enabled** | **bool** | Whether recycling is currently active | [optional] 
**Gap** | **int** | Number of interval units between reposts | [optional] 
**GapFreq** | **string** | Interval unit (week or month) | [optional] 
**StartDate** | **DateTime** |  | [optional] 
**ExpireCount** | **int** |  | [optional] 
**ExpireDate** | **DateTime** |  | [optional] 
**ContentVariations** | **List&lt;string&gt;** | Content variations for recycled copies (if configured) | [optional] 
**ContentVariationIndex** | **int** | Current position in the content variations rotation (read-only) | [optional] 
**RecycleCount** | **int** | How many recycled copies have been created so far (read-only) | [optional] 
**NextRecycleAt** | **DateTime** | When the next recycled copy will be created (read-only) | [optional] 
**LastRecycledAt** | **DateTime** | When the last recycled copy was created (read-only) | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

