# Zernio.Model.WebhookPayloadMessageMetadata
Interactive message metadata (present when message is a quick reply tap, postback button tap, or inline keyboard callback)

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**QuickReplyPayload** | **string** | Payload from a quick reply tap (Facebook/Instagram Messenger). | [optional] 
**PostbackPayload** | **string** | Payload from a postback button tap (Facebook/Instagram Messenger). | [optional] 
**PostbackTitle** | **string** | Title of the tapped postback button (Facebook/Instagram Messenger). | [optional] 
**CallbackData** | **string** | Callback data from an inline keyboard button tap (Telegram). | [optional] 
**InteractiveType** | **string** | WhatsApp only. Which kind of interactive reply the user sent: &#x60;button_reply&#x60; (tap on an interactive button), &#x60;list_reply&#x60; (tap on a list row), or &#x60;nfm_reply&#x60; (a WhatsApp Flow submission).  | [optional] 
**InteractiveId** | **string** | WhatsApp only. The &#x60;id&#x60; of the tapped button or list row, matching the &#x60;id&#x60; you supplied when the message was sent. Not set for Flow responses.  | [optional] 
**ButtonPayload** | **string** | WhatsApp only. Payload attached to a tapped template button. Template buttons emit a plain &#x60;button&#x60; webhook (not an interactive reply), so &#x60;interactiveType&#x60; is empty while this field is populated.  | [optional] 
**FlowResponseJson** | **string** | WhatsApp only. Raw &#x60;nfm_reply.response_json&#x60; string returned by a Flow submission. Useful if you need the exact wire payload; for typed access use &#x60;flowResponseData&#x60; instead.  | [optional] 
**FlowResponseData** | **Dictionary&lt;string, Object&gt;** | WhatsApp only. Parsed Flow response JSON. Populated when &#x60;flowResponseJson&#x60; is valid JSON; otherwise omitted. Keys and value types depend on the specific Flow that was submitted.  | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

