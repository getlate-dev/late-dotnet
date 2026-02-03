# Late.Model.Webhook
Individual webhook configuration for receiving real-time notifications

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Id** | **string** | Unique webhook identifier | [optional] 
**Name** | **string** | Webhook name (for identification) | [optional] 
**Url** | **string** | Webhook endpoint URL | [optional] 
**Secret** | **string** | Secret key for HMAC-SHA256 signature (not returned in responses for security) | [optional] 
**Events** | **List&lt;Webhook.EventsEnum&gt;** | Events subscribed to | [optional] 
**IsActive** | **bool** | Whether webhook delivery is enabled | [optional] 
**LastFiredAt** | **DateTime** | Timestamp of last successful webhook delivery | [optional] 
**FailureCount** | **int** | Consecutive delivery failures (resets on success, webhook disabled at 10) | [optional] 
**CustomHeaders** | **Dictionary&lt;string, string&gt;** | Custom headers included in webhook requests | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

