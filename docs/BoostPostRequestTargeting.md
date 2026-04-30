# Zernio.Model.BoostPostRequestTargeting

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**AgeMin** | **int** |  | [optional] 
**AgeMax** | **int** |  | [optional] 
**Countries** | **List&lt;string&gt;** | ISO country codes. Required for TikTok boosts (TikTok&#39;s ad group requires location_ids); optional on other platforms. | [optional] 
**Interests** | [**List&lt;UpdateAdRequestTargetingInterestsInner&gt;**](UpdateAdRequestTargetingInterestsInner.md) | Interest objects from /v1/ads/interests. Each must include id and name. | [optional] 
**AdvantageAudience** | **int** | Meta only. 0 &#x3D; disabled (default), 1 &#x3D; enabled. | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

