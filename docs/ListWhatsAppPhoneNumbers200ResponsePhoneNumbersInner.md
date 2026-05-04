# Zernio.Model.ListWhatsAppPhoneNumbers200ResponsePhoneNumbersInner
Phone number entry. Field names use Meta WhatsApp Cloud API snake_case (passed through unchanged); wabaId and wabaName are Zernio enrichment.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Id** | **string** | Phone Number ID (Meta) | [optional] 
**DisplayPhoneNumber** | **string** | E.164-formatted display number | [optional] 
**VerifiedName** | **string** | Meta-verified business name | [optional] 
**QualityRating** | **string** | GREEN, YELLOW, RED, or UNKNOWN | [optional] 
**NameStatus** | **string** | APPROVED, PENDING_REVIEW, DECLINED, or NONE | [optional] 
**MessagingLimitTier** | **string** | TIER_250, TIER_1K, TIER_10K, TIER_100K, or TIER_UNLIMITED | [optional] 
**WabaId** | **string** | WhatsApp Business Account ID (Zernio enrichment) | [optional] 
**WabaName** | **string** | WABA display name (Zernio enrichment) | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

