# Zernio.Model.GetGoogleBusinessLocationDetails200ResponseLocation
Compact public-facing summary derived from Google's `metadata`. Useful for surfacing the \"leave a review\" URL (e.g. behind a QR code) without parsing the raw block. Always populated regardless of readMask. For unverified or new locations Google omits placeId/reviewUrl/mapsUri, so those return as null and `isVerified` is false. 

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Name** | **string** | Business name as set in GBP | [optional] 
**PlaceId** | **string** | Google Maps Place ID for this location | [optional] 
**ReviewUrl** | **string** | Public \&quot;write a review\&quot; URL Google generates for this place | [optional] 
**MapsUri** | **string** | Public Google Maps URL for this location | [optional] 
**IsVerified** | **bool** | True when the location has Voice of Merchant (verified + live on Google) | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

