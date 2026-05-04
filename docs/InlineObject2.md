# Zernio.Model.InlineObject2

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Error** | **string** | Human-readable error message suitable for end-user display. | 
**Code** | **string** | Machine-readable error code. Stable across versions. | 
**Reason** | **string** | Discriminator for which gate fired. | 
**DocumentationUrl** | **string** | Link to the relevant documentation page. | [optional] 
**DashboardUrl** | **string** | Deep-link to send the end-user to. For &#x60;free_tier_exceeded&#x60; and &#x60;twitter_passthrough&#x60; this is the Zernio billing tab. For &#x60;enterprise_required&#x60; this is the Zernio enterprise contact page.  | [optional] 
**Details** | [**InlineObject2Details**](InlineObject2Details.md) |  | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

