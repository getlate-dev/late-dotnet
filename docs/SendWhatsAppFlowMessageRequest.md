# Zernio.Model.SendWhatsAppFlowMessageRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**AccountId** | **string** | WhatsApp social account ID | 
**To** | **string** | Recipient phone number (E.164 format, e.g. +1234567890) | 
**FlowId** | **string** | Published flow ID | 
**FlowCta** | **string** | CTA button text (e.g. &#39;Book Now&#39;, &#39;Sign Up&#39;) | 
**FlowAction** | **string** | Action type: navigate opens a screen directly, data_exchange hits your endpoint first | [optional] [default to FlowActionEnum.Navigate]
**FlowToken** | **string** | Unique token to correlate responses. Auto-generated UUID if omitted. | [optional] 
**FlowActionPayload** | [**SendWhatsAppFlowMessageRequestFlowActionPayload**](SendWhatsAppFlowMessageRequestFlowActionPayload.md) |  | [optional] 
**Body** | **string** | Message body text | 
**Header** | [**SendWhatsAppFlowMessageRequestHeader**](SendWhatsAppFlowMessageRequestHeader.md) |  | [optional] 
**Footer** | **string** | Optional footer text | [optional] 
**Draft** | **bool** | Set true to test an unpublished (DRAFT) flow | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

