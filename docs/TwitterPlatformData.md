# Late.Model.TwitterPlatformData

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**ReplyToTweetId** | **string** | ID of an existing tweet to reply to. The published tweet will appear as a reply in that tweet&#39;s thread. For threads, only the first tweet replies to the target; subsequent tweets chain normally. | [optional] 
**ReplySettings** | **string** | Controls who can reply to the tweet. \&quot;following\&quot; allows only people you follow, \&quot;mentionedUsers\&quot; allows only mentioned users, \&quot;subscribers\&quot; allows only subscribers, \&quot;verified\&quot; allows only verified users. Omit for default (everyone can reply). For threads, applies to the first tweet only. Cannot be combined with replyToTweetId. | [optional] 
**ThreadItems** | [**List&lt;TwitterPlatformDataThreadItemsInner&gt;**](TwitterPlatformDataThreadItemsInner.md) | Sequence of tweets in a thread. First item is the root tweet. | [optional] 
**Poll** | [**TwitterPlatformDataPoll**](TwitterPlatformDataPoll.md) |  | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

