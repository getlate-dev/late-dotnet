# Zernio.Model.UpdatePostRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Content** | **string** |  | [optional] 
**ScheduledFor** | **DateTime** |  | [optional] 
**TiktokSettings** | [**TikTokPlatformData**](TikTokPlatformData.md) | Root-level TikTok settings applied to all TikTok platforms. Merged into each platform&#39;s platformSpecificData, with platform-specific settings taking precedence. | [optional] 
**FacebookSettings** | [**FacebookPlatformData**](FacebookPlatformData.md) | Root-level Facebook settings applied to all Facebook platforms. Merged into each platform&#39;s platformSpecificData, with platform-specific settings taking precedence. | [optional] 
**Recycling** | [**RecyclingConfig**](RecyclingConfig.md) |  | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

