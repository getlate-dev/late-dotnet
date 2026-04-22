# Zernio.Model.ConversionEventUser
User identity fields. More signals mean higher match rates.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Email** | **string** | Plaintext email. Hashed server-side. | [optional] 
**Phone** | **string** | Phone number, ideally E.164. Hashed server-side. | [optional] 
**FirstName** | **string** | Plaintext first name. Hashed server-side. | [optional] 
**LastName** | **string** | Plaintext last name. Hashed server-side. | [optional] 
**ExternalId** | **string** | Stable customer identifier (e.g. CRM user ID). Hashed server-side. | [optional] 
**IpAddress** | **string** | Client IP address. Sent plaintext. | [optional] 
**UserAgent** | **string** | Client user-agent string. Sent plaintext. | [optional] 
**Country** | **string** | ISO 3166-1 alpha-2 country code, e.g. &#39;us&#39;. | [optional] 
**ClickIds** | [**ConversionEventUserClickIds**](ConversionEventUserClickIds.md) |  | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

