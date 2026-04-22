# Zernio.Model.CreateWebhookSettingsRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Name** | **string** | Webhook name (1-50 characters) | 
**Url** | **string** | Webhook endpoint URL (must be a valid URL, whitespace trimmed) | 
**Secret** | **string** | Secret key for HMAC-SHA256 signature verification | [optional] 
**Events** | **List&lt;CreateWebhookSettingsRequest.EventsEnum&gt;** | Events to subscribe to (at least one required) | 
**IsActive** | **bool** | Enable or disable webhook delivery. Defaults to &#x60;true&#x60; when omitted. | [optional] [default to true]
**CustomHeaders** | **Dictionary&lt;string, string&gt;** | Custom headers to include in webhook requests | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

