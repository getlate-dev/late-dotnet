# Late.Model.MediaItem
Media referenced in posts. URLs must be publicly reachable over HTTPS. Use POST /v1/media/presign for uploads up to 5GB. Zernio auto-compresses images and videos that exceed platform limits (videos over 200 MB may not be compressed).

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Type** | **string** |  | [optional] 
**Url** | **string** |  | [optional] 
**Title** | **string** | Optional title for the media item. Used as the document title for LinkedIn PDF/carousel posts. If omitted, falls back to the post title, then the filename. | [optional] 
**Filename** | **string** |  | [optional] 
**Size** | **int** | Optional file size in bytes | [optional] 
**MimeType** | **string** | Optional MIME type (e.g. image/jpeg, video/mp4) | [optional] 
**Thumbnail** | **string** | Optional custom thumbnail/cover image URL for videos. Supported for Facebook video posts, Facebook Reels, and regular video uploads. Max 10MB, JPG/PNG recommended. | [optional] 
**InstagramThumbnail** | **string** | Optional custom cover image URL for Instagram Reels | [optional] 
**TiktokProcessed** | **bool** | Internal flag indicating the image was resized for TikTok | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

