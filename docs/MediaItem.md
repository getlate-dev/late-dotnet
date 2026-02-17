# Late.Model.MediaItem
Media referenced in posts. URLs must be publicly reachable over HTTPS. When using third-party storage, ensure signed links remain valid until upload completes. Use POST /v1/media/presign to get a presigned URL for direct cloud storage upload (up to 5GB). Late automatically compresses images and videos that exceed platform limits server-side during publishing. Videos larger than 200 MB may not be compressed due to timeout constraints. 

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Type** | **string** |  | [optional] 
**Url** | **string** |  | [optional] 
**Filename** | **string** |  | [optional] 
**Size** | **int** | Optional file size in bytes | [optional] 
**MimeType** | **string** | Optional MIME type (e.g. image/jpeg, video/mp4) | [optional] 
**Thumbnail** | **string** | Optional thumbnail image URL for videos | [optional] 
**InstagramThumbnail** | **string** | Optional custom cover image URL for Instagram Reels | [optional] 
**TiktokProcessed** | **bool** | Internal flag indicating the image was resized for TikTok | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

