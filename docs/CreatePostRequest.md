# Late.Model.CreatePostRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Title** | **string** |  | [optional] 
**Content** | **string** | Post caption/text. Optional when media is attached or all platforms have customContent. Required for text-only posts. | [optional] 
**MediaItems** | [**List&lt;CreatePostRequestMediaItemsInner&gt;**](CreatePostRequestMediaItemsInner.md) |  | [optional] 
**Platforms** | [**List&lt;CreatePostRequestPlatformsInner&gt;**](CreatePostRequestPlatformsInner.md) |  | [optional] 
**ScheduledFor** | **DateTime** |  | [optional] 
**PublishNow** | **bool** |  | [optional] [default to false]
**IsDraft** | **bool** |  | [optional] [default to false]
**Timezone** | **string** |  | [optional] [default to "UTC"]
**Tags** | **List&lt;string&gt;** | Tags/keywords. YouTube constraints: each tag max 100 chars, combined max 500 chars, duplicates auto-removed. | [optional] 
**Hashtags** | **List&lt;string&gt;** |  | [optional] 
**Mentions** | **List&lt;string&gt;** |  | [optional] 
**CrosspostingEnabled** | **bool** |  | [optional] [default to true]
**Metadata** | **Dictionary&lt;string, Object&gt;** |  | [optional] 
**TiktokSettings** | [**TikTokPlatformData**](TikTokPlatformData.md) | Root-level TikTok settings applied to all TikTok platforms. Merged into each platform&#39;s platformSpecificData, with platform-specific settings taking precedence. | [optional] 
**QueuedFromProfile** | **string** | Profile ID to schedule via queue. When provided without scheduledFor, the post is auto-assigned to the next available slot. Do not call /v1/queue/next-slot and use that time in scheduledFor, as that bypasses queue locking. | [optional] 
**QueueId** | **string** | Specific queue ID to use when scheduling via queue. Only used when queuedFromProfile is also provided. If omitted, uses the profile&#39;s default queue.  | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

