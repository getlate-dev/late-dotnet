# Late.Model.CreateWebhookSettingsRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Name** | **string** | Webhook name (max 50 characters) | [optional] 
**Url** | **string** | Webhook endpoint URL (must be HTTPS in production) | [optional] 
**Secret** | **string** | Secret key for HMAC-SHA256 signature verification | [optional] 
**Events** | **List&lt;CreateWebhookSettingsRequest.EventsEnum&gt;** | Events to subscribe to | [optional] 
**IsActive** | **bool** | Enable or disable webhook delivery | [optional] 
**CustomHeaders** | **Dictionary&lt;string, string&gt;** | Custom headers to include in webhook requests | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

