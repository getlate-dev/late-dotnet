# Late.Model.MediaItem
Media referenced in posts. URLs must be publicly reachable over HTTPS by the destination platforms. When using third-party storage, ensure signed links remain valid until upload completes.  **Uploading Media:** Use `POST /v1/media/presign` to get a presigned URL, then upload your file directly to cloud storage. Supports files up to 5GB. See the `/v1/media/presign` endpoint documentation for details.  **Automatic Media Compression:** Late automatically compresses images and videos that exceed platform limits. Compression happens server-side during publishing. Videos larger than 200 MB may not be compressed due to server timeout constraints. 

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

