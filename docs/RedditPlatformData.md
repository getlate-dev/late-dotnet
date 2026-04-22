# Zernio.Model.RedditPlatformData
Posts are either link (with URL/media), native video (via nativeVideo), or self (text-only). Use forceSelf to override. Subreddit defaults to the account's configured one. Some subreddits require a flair.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Subreddit** | **string** | Target subreddit name (without \&quot;r/\&quot; prefix). Overrides the default. Use GET /v1/accounts/{id}/reddit-subreddits to list options. | [optional] 
**Title** | **string** | Post title. Defaults to the first line of content, truncated to 300 characters. | [optional] 
**Url** | **string** | URL for link posts. If provided (and forceSelf is not true), creates a link post instead of a text post. | [optional] 
**ForceSelf** | **bool** | When true, creates a text/self post even when a URL or media is provided. | [optional] 
**FlairId** | **string** | Flair ID for the post. Required by some subreddits. Use GET /v1/accounts/{id}/reddit-flairs?subreddit&#x3D;name to list flairs. | [optional] 
**NativeVideo** | **bool** | Controls Reddit&#39;s native video upload flow. When true (default for video mediaItems), the video is uploaded to Reddit&#39;s CDN and submitted with kind&#x3D;video so it renders as an embedded Reddit video player. Reddit transcodes server-side (1080p/30fps cap). Set to false to fall back to a legacy link post. If the subreddit blocks video posts, the upload falls back to a link post automatically.  | [optional] [default to true]
**Videogif** | **bool** | When true (and nativeVideo is active), submits the video as a silent videogif (kind&#x3D;videogif). Use for short looping clips without audio. | [optional] 
**VideoPosterUrl** | **string** | Optional poster/thumbnail image URL for native video posts. If omitted, the first frame of the video is extracted and used automatically. | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

