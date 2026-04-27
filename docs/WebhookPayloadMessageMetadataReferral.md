# Zernio.Model.WebhookPayloadMessageMetadataReferral
WhatsApp only. Click-to-WhatsApp (CTWA) ad attribution. Present only on the FIRST inbound message after a user reaches the business via a CTWA ad. Forwarded verbatim from Meta's referral envelope so it can be replayed to the Conversions API for Business Messaging. Attribution window is 7 days from click. 

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**CtwaClid** | **string** | Meta&#39;s GCLID-equivalent click identifier. | [optional] 
**SourceId** | **string** |  | [optional] 
**SourceType** | **string** |  | [optional] 
**SourceUrl** | **string** |  | [optional] 
**Headline** | **string** |  | [optional] 
**Body** | **string** |  | [optional] 
**MediaType** | **string** |  | [optional] 
**ImageUrl** | **string** |  | [optional] 
**VideoUrl** | **string** |  | [optional] 
**ThumbnailUrl** | **string** |  | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

