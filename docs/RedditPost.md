# Zernio.Model.RedditPost
A normalized Reddit post returned by the feed and search endpoints

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Id** | **string** | Reddit post ID (without type prefix) | [optional] 
**Fullname** | **string** | Reddit fullname (e.g. t3_abc123) | [optional] 
**Title** | **string** |  | [optional] 
**Author** | **string** |  | [optional] 
**Subreddit** | **string** |  | [optional] 
**Url** | **string** | Post URL (may be a gallery URL | [optional] 
**Permalink** | **string** | Full permalink to the Reddit post | [optional] 
**Selftext** | **string** | Self-post body text (empty string for link posts) | [optional] 
**CreatedUtc** | **decimal** | Unix timestamp of post creation | [optional] 
**Score** | **int** |  | [optional] 
**NumComments** | **int** |  | [optional] 
**Over18** | **bool** | Whether the post is marked NSFW | [optional] 
**Stickied** | **bool** |  | [optional] 
**FlairText** | **string** | Link flair text if set | [optional] 
**IsGallery** | **bool** | Whether the post is a gallery with multiple images | [optional] 
**GalleryImages** | **List&lt;string&gt;** | Individual image URLs for gallery posts (only present when isGallery is true) | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

