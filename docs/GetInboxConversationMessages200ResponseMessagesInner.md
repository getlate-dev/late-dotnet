# Late.Model.GetInboxConversationMessages200ResponseMessagesInner

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Id** | **string** |  | [optional] 
**ConversationId** | **string** |  | [optional] 
**AccountId** | **string** |  | [optional] 
**Platform** | **string** |  | [optional] 
**Message** | **string** |  | [optional] 
**SenderId** | **string** |  | [optional] 
**SenderName** | **string** |  | [optional] 
**SenderVerifiedType** | **string** | X/Twitter verified badge type. Only present for Twitter/X messages. | [optional] 
**Direction** | **string** |  | [optional] 
**CreatedAt** | **DateTime** |  | [optional] 
**Attachments** | [**List&lt;GetInboxConversationMessages200ResponseMessagesInnerAttachmentsInner&gt;**](GetInboxConversationMessages200ResponseMessagesInnerAttachmentsInner.md) |  | [optional] 
**Subject** | **string** | Reddit message subject | [optional] 
**StoryReply** | **bool** | Instagram story reply | [optional] 
**IsStoryMention** | **bool** | Instagram story mention | [optional] 
**IsEdited** | **bool** | True if the sender has edited this message at least once. | [optional] 
**EditedAt** | **DateTime** | When the most recent edit happened. | [optional] 
**EditCount** | **int** | Total number of edits applied. | [optional] 
**EditHistory** | [**List&lt;GetInboxConversationMessages200ResponseMessagesInnerEditHistoryInner&gt;**](GetInboxConversationMessages200ResponseMessagesInnerEditHistoryInner.md) | Every prior version of the message, oldest first. | [optional] 
**IsDeleted** | **bool** | True if the sender has deleted (unsent) this message. The original &#x60;message&#x60; and &#x60;attachments&#x60; fields remain populated. | [optional] 
**DeletedAt** | **DateTime** |  | [optional] 
**DeliveryStatus** | **string** | Lifecycle status for outgoing messages. Not all platforms emit every state (see webhook support matrix). | [optional] 
**DeliveredAt** | **DateTime** |  | [optional] 
**ReadAt** | **DateTime** |  | [optional] 
**SentAt** | **DateTime** | Original send time for outgoing messages (used for Messenger watermark queries). | [optional] 
**DeliveryError** | [**GetInboxConversationMessages200ResponseMessagesInnerDeliveryError**](GetInboxConversationMessages200ResponseMessagesInnerDeliveryError.md) |  | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

