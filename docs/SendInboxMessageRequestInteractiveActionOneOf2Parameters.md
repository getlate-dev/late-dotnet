# Zernio.Model.SendInboxMessageRequestInteractiveActionOneOf2Parameters

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**FlowMessageVersion** | **string** | Defaults to \&quot;3\&quot; when omitted. | [optional] 
**FlowToken** | **string** | Opaque token you choose to correlate Flow responses with your own state (max 200 chars). | 
**FlowId** | **string** | Published Flow ID from Meta Business Manager. | 
**FlowCta** | **string** | Button label that opens the Flow (max 20 chars). | 
**FlowAction** | **string** | &#x60;navigate&#x60; sends the user to &#x60;flow_action_payload.screen&#x60;; &#x60;data_exchange&#x60; posts data to your Flow endpoint. | 
**FlowActionPayload** | [**SendInboxMessageRequestInteractiveActionOneOf2ParametersFlowActionPayload**](SendInboxMessageRequestInteractiveActionOneOf2ParametersFlowActionPayload.md) |  | [optional] 
**Mode** | **string** | Set to &#x60;draft&#x60; to test an unpublished Flow. | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

