# Late.Model.CreatePostRequestPlatformsInner

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Platform** | **string** |  | [optional] 
**AccountId** | **string** |  | [optional] 
**CustomContent** | **string** | Platform-specific text override. When set, this content is used instead of the top-level post content for this platform. Useful for tailoring captions per platform (e.g. keeping tweets under 280 characters). | [optional] 
**CustomMedia** | [**List&lt;CreatePostRequestMediaItemsInner&gt;**](CreatePostRequestMediaItemsInner.md) |  | [optional] 
**ScheduledFor** | **DateTime** | Optional per-platform scheduled time override. When omitted, the top-level scheduledFor is used. | [optional] 
**PlatformSpecificData** | [**CreatePostRequestPlatformsInnerPlatformSpecificData**](CreatePostRequestPlatformsInnerPlatformSpecificData.md) |  | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

