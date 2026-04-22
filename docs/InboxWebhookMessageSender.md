# Zernio.Model.InboxWebhookMessageSender

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Id** | **string** | Sender&#39;s platform identifier. For WhatsApp this is the phone number (without leading &#x60;+&#x60;) when available, otherwise the &#x60;businessScopedUserId&#x60;. For other platforms, the platform&#39;s own user ID.  | 
**Name** | **string** |  | [optional] 
**Username** | **string** |  | [optional] 
**Picture** | **string** |  | [optional] 
**PhoneNumber** | **string** | WhatsApp only. Sender&#39;s phone number in E.164 format (with leading &#x60;+&#x60;).  **Nullable during the BSUID rollout (April 2026+).** WhatsApp users who adopt a username can message businesses without exposing a phone number — this field is omitted for them. Match by &#x60;businessScopedUserId&#x60; instead. See &#x60;docs/whatsapp-bsuid-migration.md&#x60;.  | [optional] 
**BusinessScopedUserId** | **string** | WhatsApp only. Business-scoped user ID (BSUID) — Meta&#39;s canonical identifier for a WhatsApp user within your business. Present when Meta includes it in the inbound payload (rollout in progress since early April 2026). **Recommended primary identity anchor** going forward; fall back to &#x60;phoneNumber&#x60; only when this field is absent.  | [optional] 
**ParentBusinessScopedUserId** | **string** | WhatsApp only. Parent BSUID for businesses with linked business portfolios. Omitted for standalone portfolios.  | [optional] 
**WhatsappUsername** | **string** | WhatsApp only. User&#39;s WhatsApp username (e.g. &#x60;@jane&#x60;). Not a stable identifier — users can change it. Useful for display, not recommended as an identity anchor.  | [optional] 
**InstagramProfile** | [**InboxWebhookMessageSenderInstagramProfile**](InboxWebhookMessageSenderInstagramProfile.md) |  | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

