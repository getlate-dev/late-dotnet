# Late.Model.MediaItem
Media referenced in posts. URLs must be publicly reachable over HTTPS by the destination platforms. When using third‑party storage, ensure signed links remain valid until upload completes.  **Uploading Media:** Use `POST /v1/media/presign` to get a presigned URL, then upload your file directly to cloud storage. Supports files up to 5GB. See the `/v1/media/presign` endpoint documentation for details.  **Automatic Media Compression:** Late automatically compresses media that exceeds platform limits, so you don't need to worry about file size restrictions. Compression happens server-side during publishing.  **Image compression by platform:** - Twitter/X: >5 MB - Instagram: >8 MB - Threads: >8 MB - Facebook: >10 MB - LinkedIn: >8 MB - TikTok: >20 MB - Pinterest: >32 MB - Reddit: >20 MB - Snapchat: >20 MB - Telegram: >10 MB - Bluesky: >1 MB - YouTube (thumbnails): >2 MB - Google Business: >5 MB  **Video compression by platform:** - Twitter/X: >512 MB - Instagram Stories: >100 MB - Instagram Reels: >300 MB - Facebook: >4 GB - LinkedIn: >5 GB - TikTok: >4 GB - Pinterest: >2 GB - Snapchat: >500 MB - Telegram: >50 MB  Note: Videos larger than 200 MB may not be compressed due to server timeout constraints. For best results, compress very large videos before uploading. 

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

