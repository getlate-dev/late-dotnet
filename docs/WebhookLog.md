# Late.Model.WebhookLog
Webhook delivery log entry

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Id** | **string** |  | [optional] 
**WebhookId** | **string** | ID of the webhook that was triggered | [optional] 
**WebhookName** | **string** | Name of the webhook that was triggered | [optional] 
**Event** | **string** |  | [optional] 
**Url** | **string** |  | [optional] 
**Status** | **string** |  | [optional] 
**StatusCode** | **int** | HTTP status code from webhook endpoint | [optional] 
**RequestPayload** | **Object** | Payload sent to webhook endpoint | [optional] 
**ResponseBody** | **string** | Response body from webhook endpoint (truncated to 10KB) | [optional] 
**ErrorMessage** | **string** | Error message if delivery failed | [optional] 
**AttemptNumber** | **int** | Delivery attempt number (max 3 retries) | [optional] 
**ResponseTime** | **int** | Response time in milliseconds | [optional] 
**CreatedAt** | **DateTime** |  | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

