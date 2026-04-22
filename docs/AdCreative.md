# Zernio.Model.AdCreative
Platform-specific creative data. Fields vary by platform.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**ThumbnailUrl** | **string** | Primary thumbnail/image URL | [optional] 
**ImageUrl** | **string** | Alternative image URL | [optional] 
**VideoId** | **string** | Meta video ID for VIDEO-type ads. Null for non-video ads. Callers that need an embeddable MP4 can call GET /{videoId}?fields&#x3D;source with the page access token. | [optional] 
**VideoUrl** | **string** | Public Facebook watch URL for VIDEO-type ads (https://www.facebook.com/watch/?v&#x3D;{videoId}). Null for non-video ads. | [optional] 
**ObjectType** | **string** | Meta creative object_type (e.g. SHARE, VIDEO, PRIVACY_CHECK_FAIL, POST_DELETED). Use this to render state-aware previews — when Meta moderation strips image/video fields, only thumbnailUrl at 64x64 is available. | [optional] 
**MediaUrls** | **List&lt;string&gt;** | All media URLs for this ad (carousel images, multiple assets). Populated for Meta (carousel child_attachments), Google Ads (responsive display marketing_images), and LinkedIn (multi-image posts). | [optional] 
**Body** | **string** | Ad copy/text | [optional] 
**GoogleHeadline** | **string** | Google Ads headline | [optional] 
**GoogleDescription** | **string** | Google Ads description | [optional] 
**LinkUrl** | **string** | Destination URL | [optional] 
**PinterestImageUrl** | **string** |  | [optional] 
**PinterestTitle** | **string** |  | [optional] 
**PinterestDescription** | **string** |  | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

