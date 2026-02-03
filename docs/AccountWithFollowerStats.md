# Late.Model.AccountWithFollowerStats

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Id** | **string** |  | [optional] 
**Platform** | **string** |  | [optional] 
**ProfileId** | [**SocialAccountProfileId**](SocialAccountProfileId.md) |  | [optional] 
**Username** | **string** |  | [optional] 
**DisplayName** | **string** |  | [optional] 
**ProfileUrl** | **string** | Full profile URL for the connected account. Available for all platforms: - Twitter/X: https://x.com/{username} - Instagram: https://instagram.com/{username} - TikTok: https://tiktok.com/@{username} - YouTube: https://youtube.com/@{handle} or https://youtube.com/channel/{id} - LinkedIn Personal: https://www.linkedin.com/in/{vanityName}/ - LinkedIn Organization: https://www.linkedin.com/company/{vanityName}/ - Threads: https://threads.net/@{username} - Pinterest: https://pinterest.com/{username} - Reddit: https://reddit.com/user/{username} - Bluesky: https://bsky.app/profile/{handle} - Facebook: https://facebook.com/{username} or https://facebook.com/{pageId} - Google Business: Google Maps URL for the business location  | [optional] 
**IsActive** | **bool** |  | [optional] 
**FollowersCount** | **decimal** | Follower count (only included if user has analytics add-on) | [optional] 
**FollowersLastUpdated** | **DateTime** | Last time follower count was updated (only included if user has analytics add-on) | [optional] 
**ProfilePicture** | **string** |  | [optional] 
**CurrentFollowers** | **decimal** | Current follower count | [optional] 
**LastUpdated** | **DateTime** |  | [optional] 
**Growth** | **decimal** | Follower change over period | [optional] 
**GrowthPercentage** | **decimal** | Percentage growth | [optional] 
**DataPoints** | **decimal** | Number of historical snapshots | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

