# Late.Model.TikTokPlatformData
TikTok platform-specific settings for video/photo posting.  **Constraints:** - Photo carousels support up to 35 images. - **Title length limits**:   - Videos: up to 2200 chars (full content used as title)   - Photos: content is automatically truncated to 90 chars for title (hashtags/URLs stripped). Use 'description' field for longer text (up to 4000 chars). - privacyLevel must be chosen from creator_info.privacy_level_options (no defaulting). - allowDuet and allowStitch required for videos; allowComment for all. - contentPreviewConfirmed and expressConsentGiven must be true before posting.  **Note:** Both camelCase and snake_case field names are accepted for backwards compatibility. The nested `tiktokSettings` object format is also still supported but deprecated. 

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Draft** | **bool** | When true, Late sends the post to the TikTok Creator Inbox as a draft instead of publishing it immediately. When omitted or false, TikTok uses direct posting (live publish) as usual.  | [optional] 
**PrivacyLevel** | **string** | One of the values returned by the TikTok creator info API for the account | [optional] 
**AllowComment** | **bool** | Allow comments on the post | [optional] 
**AllowDuet** | **bool** | Allow duets (required for video posts) | [optional] 
**AllowStitch** | **bool** | Allow stitches (required for video posts) | [optional] 
**CommercialContentType** | **string** | Type of commercial content disclosure | [optional] 
**BrandPartnerPromote** | **bool** | Whether the post promotes a brand partner | [optional] 
**IsBrandOrganicPost** | **bool** | Whether the post is a brand organic post | [optional] 
**ContentPreviewConfirmed** | **bool** | User has confirmed they previewed the content | [optional] 
**ExpressConsentGiven** | **bool** | User has given express consent for posting | [optional] 
**MediaType** | **string** | Optional override. Defaults based on provided media items. | [optional] 
**VideoCoverTimestampMs** | **int** | Optional for video posts. Timestamp in milliseconds to select which frame to use as thumbnail (defaults to 1000ms/1 second). | [optional] 
**PhotoCoverIndex** | **int** | Optional for photo carousels. Index of image to use as cover, 0-based (defaults to 0/first image). | [optional] 
**AutoAddMusic** | **bool** | When true, TikTok may add recommended music (photos only) | [optional] 
**VideoMadeWithAi** | **bool** | Set true to disclose AI-generated content | [optional] 
**Description** | **string** | Optional long-form description for photo posts (max 4000 chars). Recommended for photo posts when content exceeds 90 characters, as photo titles are automatically truncated to 90 chars (after stripping hashtags/URLs).  | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

