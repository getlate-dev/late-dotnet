# Zernio.Model.AnalyticsSinglePostResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**PostId** | **string** |  | [optional] 
**LatePostId** | **string** | Original Zernio post ID if scheduled via Zernio | [optional] 
**Status** | **string** | Overall post status. \&quot;partial\&quot; when some platforms published and others failed. | [optional] 
**Content** | **string** |  | [optional] 
**ScheduledFor** | **DateTime** |  | [optional] 
**PublishedAt** | **DateTime** |  | [optional] 
**Analytics** | [**PostAnalytics**](PostAnalytics.md) |  | [optional] 
**PlatformAnalytics** | [**List&lt;PlatformAnalytics&gt;**](PlatformAnalytics.md) |  | [optional] 
**Platform** | **string** |  | [optional] 
**PlatformPostUrl** | **string** |  | [optional] 
**IsExternal** | **bool** |  | [optional] 
**SyncStatus** | **string** | Overall sync state across all platforms | [optional] 
**Message** | **string** | Human-readable status message for pending, partial, or failed states | [optional] 
**ThumbnailUrl** | **string** |  | [optional] 
**MediaType** | **string** |  | [optional] 
**MediaItems** | [**List&lt;AnalyticsSinglePostResponseMediaItemsInner&gt;**](AnalyticsSinglePostResponseMediaItemsInner.md) | All media items for this post. Carousel posts contain one entry per slide. | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

