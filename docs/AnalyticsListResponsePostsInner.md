# Zernio.Model.AnalyticsListResponsePostsInner

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Id** | **string** |  | [optional] 
**LatePostId** | **string** | Original Zernio post ID if scheduled via Zernio | [optional] 
**Content** | **string** |  | [optional] 
**ScheduledFor** | **DateTime** |  | [optional] 
**PublishedAt** | **DateTime** |  | [optional] 
**Status** | **string** |  | [optional] 
**Analytics** | [**PostAnalytics**](PostAnalytics.md) |  | [optional] 
**Platforms** | [**List&lt;PlatformAnalytics&gt;**](PlatformAnalytics.md) |  | [optional] 
**Platform** | **string** |  | [optional] 
**PlatformPostUrl** | **string** |  | [optional] 
**IsExternal** | **bool** |  | [optional] 
**ProfileId** | **string** |  | [optional] 
**ThumbnailUrl** | **string** |  | [optional] 
**MediaType** | **string** |  | [optional] 
**MediaItems** | [**List&lt;AnalyticsSinglePostResponseMediaItemsInner&gt;**](AnalyticsSinglePostResponseMediaItemsInner.md) | All media items for this post. Carousel posts contain one entry per slide. | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

