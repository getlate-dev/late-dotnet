# Zernio.Model.UpdatePostMetadataRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Platform** | **string** | The platform to update metadata on | 
**VideoId** | **string** | YouTube video ID (required for direct mode, ignored for post-based mode) | [optional] 
**AccountId** | **string** | Zernio social account ID (required for direct mode, ignored for post-based mode) | [optional] 
**Title** | **string** | New video title (max 100 characters for YouTube) | [optional] 
**Description** | **string** | New video description | [optional] 
**Tags** | **List&lt;string&gt;** | Array of keyword tags (max 500 characters combined for YouTube) | [optional] 
**CategoryId** | **string** | YouTube video category ID | [optional] 
**PrivacyStatus** | **string** | Video privacy setting | [optional] 
**ThumbnailUrl** | **string** | Public URL of a custom thumbnail image (JPEG, PNG, or GIF, max 2 MB, recommended 1280x720). Works on any video you own, including existing videos not published through Zernio. The channel must be verified (phone verification) to set custom thumbnails. | [optional] 
**MadeForKids** | **bool** | COPPA compliance flag. Set true for child-directed content (restricts comments, notifications, ad targeting). | [optional] 
**ContainsSyntheticMedia** | **bool** | AI-generated content disclosure. Set true if the video contains synthetic content that could be mistaken for real. YouTube may add a label. | [optional] 
**PlaylistId** | **string** | YouTube playlist ID to add the video to (e.g. &#39;PLxxxxxxxxxxxxx&#39;). Use GET /v1/accounts/{id}/youtube-playlists to list available playlists. Only playlists owned by the channel are supported. | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

