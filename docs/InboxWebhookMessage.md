# Zernio.Model.InboxWebhookMessage
The message object included in inbox webhook payloads.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Id** | **string** | Internal message ID | 
**ConversationId** | **string** | Internal conversation ID | 
**Platform** | **string** |  | 
**PlatformMessageId** | **string** | Platform&#39;s message ID | 
**Direction** | **string** |  | 
**Text** | **string** | Message text content (retained on deleted messages for API consumers; Zernio dashboard UI hides this) | 
**Attachments** | [**List&lt;InboxWebhookMessageAttachmentsInner&gt;**](InboxWebhookMessageAttachmentsInner.md) |  | 
**Sender** | [**InboxWebhookMessageSender**](InboxWebhookMessageSender.md) |  | 
**SentAt** | **DateTime** |  | 
**IsRead** | **bool** |  | 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

