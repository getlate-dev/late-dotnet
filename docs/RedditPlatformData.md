# Late.Model.RedditPlatformData
Posts are either link (with URL/media) or self (text-only). Use forceSelf to override. Subreddit defaults to the account's configured one. Some subreddits require a flair.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Subreddit** | **string** | Target subreddit name (without \&quot;r/\&quot; prefix). Overrides the default. Use GET /v1/accounts/{id}/reddit-subreddits to list options. | [optional] 
**Title** | **string** | Post title. Defaults to the first line of content, truncated to 300 characters. | [optional] 
**Url** | **string** | URL for link posts. If provided (and forceSelf is not true), creates a link post instead of a text post. | [optional] 
**ForceSelf** | **bool** | When true, creates a text/self post even when a URL or media is provided. | [optional] 
**FlairId** | **string** | Flair ID for the post. Required by some subreddits. Use GET /v1/accounts/{id}/reddit-flairs?subreddit&#x3D;name to list flairs. | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

