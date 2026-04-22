# Zernio.Model.WebhookPayloadMessageEdited
Webhook payload for message.edited events. Fires when the sender edits a previously-sent message. Supported platforms: Instagram, Facebook Messenger, Telegram. The message object reflects the LATEST state; editHistory contains every prior version in order (oldest first), so the last entry is the version immediately before the current content. 

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Id** | **string** |  | 
**Event** | **string** |  | 
**Message** | [**InboxWebhookMessage**](InboxWebhookMessage.md) |  | 
**EditHistory** | [**List&lt;WebhookPayloadMessageEditedEditHistoryInner&gt;**](WebhookPayloadMessageEditedEditHistoryInner.md) | Prior versions of the message, oldest first. | 
**EditCount** | **int** | Total number of edits applied to this message. | 
**EditedAt** | **DateTime** | When the most recent edit happened. | 
**Conversation** | [**InboxWebhookConversation**](InboxWebhookConversation.md) |  | 
**Account** | [**InboxWebhookAccount**](InboxWebhookAccount.md) |  | 
**Timestamp** | **DateTime** |  | 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

