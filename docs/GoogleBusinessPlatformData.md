# Zernio.Model.GoogleBusinessPlatformData
Text and single image only (no videos). Supports STANDARD, EVENT, OFFER, and ALERT post types. Posts appear on GBP, Google Search, and Maps. Use locationId for multi-location posting. Schedule dates accept both ISO 8601 strings (e.g. '2026-04-15T09:00:00Z') and Google's native {year, month, day} objects.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**LocationId** | **string** | Target GBP location ID (e.g. \&quot;locations/123456789\&quot;). If omitted, uses the default location. Use GET /v1/accounts/{id}/gmb-locations to list locations. | [optional] 
**LanguageCode** | **string** | BCP 47 language code (e.g. \&quot;en\&quot;, \&quot;de\&quot;, \&quot;es\&quot;). Auto-detected if omitted. Set explicitly for short or mixed-language posts. | [optional] 
**TopicType** | **string** | Post type. STANDARD is a regular update. EVENT requires the event object. OFFER requires the offer object. Defaults to STANDARD if omitted. | [optional] [default to TopicTypeEnum.STANDARD]
**CallToAction** | [**GoogleBusinessPlatformDataCallToAction**](GoogleBusinessPlatformDataCallToAction.md) |  | [optional] 
**Event** | [**GoogleBusinessPlatformDataEvent**](GoogleBusinessPlatformDataEvent.md) |  | [optional] 
**Offer** | [**GoogleBusinessPlatformDataOffer**](GoogleBusinessPlatformDataOffer.md) |  | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

