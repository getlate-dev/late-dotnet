# Late.Model.UpdateAdRequestTargeting
Meta-only. Targeting updates for other platforms are not supported after creation.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**AgeMin** | **int** |  | [optional] 
**AgeMax** | **int** |  | [optional] 
**Countries** | **List&lt;string&gt;** |  | [optional] 
**Interests** | [**List&lt;UpdateAdRequestTargetingInterestsInner&gt;**](UpdateAdRequestTargetingInterestsInner.md) | Interest objects from /v1/ads/interests. Each must include id and name. | [optional] 
**AdvantageAudience** | **int** | Meta only. Omit to preserve the existing setting on update. 0 &#x3D; disabled, 1 &#x3D; enabled. | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

