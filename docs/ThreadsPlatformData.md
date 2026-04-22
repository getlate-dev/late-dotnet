# Zernio.Model.ThreadsPlatformData
Up to 10 images per carousel (no videos). Videos must be H.264/AAC MP4, max 5 min. Images JPEG/PNG, max 8 MB. Use threadItems for reply chains.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**TopicTag** | **string** | Topic tag for post categorization and discoverability on Threads. Must be 1-50 characters, cannot contain periods (.) or ampersands (&amp;). Overrides auto-extraction from content hashtags when provided. | [optional] 
**ThreadItems** | [**List&lt;TwitterPlatformDataThreadItemsInner&gt;**](TwitterPlatformDataThreadItemsInner.md) | Complete sequence of posts in a Threads thread. The first item becomes the root post, subsequent items are chained as replies. When threadItems is provided, the top-level content field is used only for display and search purposes, it is NOT published. You must include your first post as threadItems[0].  | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

