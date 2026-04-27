# Zernio.Model.SendWhatsAppConversion200Response

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Platform** | **string** |  | [optional] 
**EventsReceived** | **int** | Events accepted by Meta. | [optional] 
**EventsFailed** | **int** | Events rejected by Meta (see failures). | [optional] 
**Failures** | [**List&lt;SendConversions200ResponseFailuresInner&gt;**](SendConversions200ResponseFailuresInner.md) | Per-event failure detail. Empty when all events were accepted.  | [optional] 
**TraceId** | **string** | Meta &#x60;fbtrace_id&#x60; for debugging. Surface in support tickets.  | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

