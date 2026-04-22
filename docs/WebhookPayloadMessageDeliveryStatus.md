# Zernio.Model.WebhookPayloadMessageDeliveryStatus
Shared payload for message.delivered, message.read, and message.failed events. Fires when the platform reports a new delivery state for an outgoing message.  Platform support:   * message.delivered — WhatsApp, Facebook Messenger.   * message.read      — WhatsApp, Facebook Messenger, Instagram.   * message.failed    — WhatsApp only (other platforms don't expose     per-message failure via webhook). 

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Id** | **string** |  | 
**Event** | **string** |  | 
**Message** | [**InboxWebhookMessage**](InboxWebhookMessage.md) |  | 
**StatusAt** | **DateTime** | When the platform reported this status. | 
**Error** | [**WebhookPayloadMessageDeliveryStatusError**](WebhookPayloadMessageDeliveryStatusError.md) |  | [optional] 
**Conversation** | [**InboxWebhookConversation**](InboxWebhookConversation.md) |  | 
**Account** | [**InboxWebhookAccount**](InboxWebhookAccount.md) |  | 
**Timestamp** | **DateTime** |  | 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

