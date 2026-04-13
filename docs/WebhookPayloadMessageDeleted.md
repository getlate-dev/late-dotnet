# Late.Model.WebhookPayloadMessageDeleted
Webhook payload for `message.deleted` events. Fires when the sender deletes (unsends) a message. Supported platforms: Instagram (incoming unsend) and WhatsApp (when the business deletes an outgoing message via the Cloud API).  The `message.text` and `message.attachments` fields retain the content that existed before the delete. The Zernio dashboard UI does not show this content, but authorized API consumers may access it for moderation, compliance, or archival use cases. 

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Id** | **string** |  | 
**Event** | **string** |  | 
**Message** | [**WebhookPayloadMessageMessage**](WebhookPayloadMessageMessage.md) |  | 
**DeletedAt** | **DateTime** |  | 
**Conversation** | [**WebhookPayloadMessageConversation**](WebhookPayloadMessageConversation.md) |  | 
**Account** | [**WebhookPayloadMessageAccount**](WebhookPayloadMessageAccount.md) |  | 
**Timestamp** | **DateTime** |  | 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

