# Late.Model.CreatePostRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Title** | **string** |  | [optional] 
**Content** | **string** | Post caption/text content. Optional when media is attached (images, videos, etc.). Required for text-only posts. Can also be omitted if all platforms have customContent set.  | [optional] 
**MediaItems** | [**List&lt;CreatePostRequestMediaItemsInner&gt;**](CreatePostRequestMediaItemsInner.md) |  | [optional] 
**Platforms** | [**List&lt;CreatePostRequestPlatformsInner&gt;**](CreatePostRequestPlatformsInner.md) |  | [optional] 
**ScheduledFor** | **DateTime** |  | [optional] 
**PublishNow** | **bool** |  | [optional] [default to false]
**IsDraft** | **bool** |  | [optional] [default to false]
**Timezone** | **string** |  | [optional] [default to "UTC"]
**Tags** | **List&lt;string&gt;** | Tags/keywords for the post. YouTube-specific constraints: - No count limit; duplicates are automatically removed - Each tag must be ≤ 100 characters - Combined total across all tags ≤ 500 characters (YouTube&#39;s limit)  | [optional] 
**Hashtags** | **List&lt;string&gt;** |  | [optional] 
**Mentions** | **List&lt;string&gt;** |  | [optional] 
**CrosspostingEnabled** | **bool** |  | [optional] [default to true]
**Metadata** | **Dictionary&lt;string, Object&gt;** |  | [optional] 
**TiktokSettings** | [**TikTokPlatformData**](TikTokPlatformData.md) | Root-level TikTok settings applied to all TikTok platforms in the request. This is a convenience shorthand. Settings here are merged into each TikTok platform&#39;s platformSpecificData, with platform-specific settings taking precedence.  | [optional] 
**QueuedFromProfile** | **string** | Profile ID to schedule via queue.  When provided (without &#x60;scheduledFor&#x60;), the post will be automatically assigned to the next available slot from the profile&#39;s queue. The system uses distributed locking to prevent race conditions when multiple posts are scheduled concurrently. Do not call &#x60;/v1/queue/next-slot&#x60; and then use that time in &#x60;scheduledFor&#x60;. That bypasses the queue system and can cause duplicate slot assignments.  | [optional] 
**QueueId** | **string** | Specific queue ID to use when scheduling via queue. Only used when queuedFromProfile is also provided. If omitted, uses the profile&#39;s default queue.  | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

