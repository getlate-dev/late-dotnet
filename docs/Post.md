# Late.Model.Post

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Id** | **string** |  | [optional] 
**UserId** | [**PostUserId**](PostUserId.md) |  | [optional] 
**Title** | **string** | YouTube: title must be ≤ 100 characters.  | [optional] 
**Content** | **string** |  | [optional] 
**MediaItems** | [**List&lt;MediaItem&gt;**](MediaItem.md) |  | [optional] 
**Platforms** | [**List&lt;PlatformTarget&gt;**](PlatformTarget.md) |  | [optional] 
**ScheduledFor** | **DateTime** |  | [optional] 
**Timezone** | **string** |  | [optional] 
**Status** | **string** |  | [optional] 
**Tags** | **List&lt;string&gt;** | YouTube constraints: each tag max 100 chars, combined max 500 chars, duplicates removed. | [optional] 
**Hashtags** | **List&lt;string&gt;** |  | [optional] 
**Mentions** | **List&lt;string&gt;** |  | [optional] 
**Visibility** | **string** |  | [optional] 
**Metadata** | **Dictionary&lt;string, Object&gt;** |  | [optional] 
**QueuedFromProfile** | **string** | Profile ID if the post was scheduled via the queue | [optional] 
**QueueId** | **string** | Queue ID if the post was scheduled via a specific queue | [optional] 
**CreatedAt** | **DateTime** |  | [optional] 
**UpdatedAt** | **DateTime** |  | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

