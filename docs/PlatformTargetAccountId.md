# Zernio.Model.PlatformTargetAccountId

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Id** | **string** |  | [optional] 
**Platform** | **string** |  | [optional] 
**ProfileId** | [**SocialAccountProfileId**](SocialAccountProfileId.md) |  | [optional] 
**Username** | **string** |  | [optional] 
**DisplayName** | **string** |  | [optional] 
**ProfilePicture** | **string** | URL to the account&#39;s profile picture on the platform. May be null if the platform does not provide one. | [optional] 
**ProfileUrl** | **string** | Full profile URL for the connected account on its platform. | [optional] 
**IsActive** | **bool** |  | [optional] 
**FollowersCount** | **decimal** | Follower count (only included if user has analytics add-on) | [optional] 
**FollowersLastUpdated** | **DateTime** | Last time follower count was updated (only included if user has analytics add-on) | [optional] 
**ParentAccountId** | **string** | Reference to the parent posting SocialAccount. Set for ads accounts that share or derive from a posting account&#39;s OAuth token. null for standalone ads (Google Ads) and all posting accounts.  | [optional] 
**Enabled** | **bool** | Whether the user explicitly activated this account. false means the account was created as a side effect (e.g., posting account auto-created when user connected ads first). Posting UI and scheduler ignore accounts with enabled: false.  | [optional] 
**Metadata** | **Object** | Platform-specific metadata. Fields vary by platform. For WhatsApp accounts, includes: - qualityRating: Phone number quality rating from Meta (GREEN, YELLOW, RED, or UNKNOWN) - nameStatus: Display name review status (APPROVED, PENDING_REVIEW, DECLINED, or NONE). Messages cannot be sent until the display name is approved by Meta. - messagingLimitTier: Maximum unique business-initiated conversations per 24h rolling window (TIER_250, TIER_1K, TIER_10K, TIER_100K, or TIER_UNLIMITED). Scales automatically as quality rating improves. - verifiedName: Meta-verified business display name - displayPhoneNumber: Formatted phone number (e.g., \&quot;+1 555-123-4567\&quot;) - wabaId: WhatsApp Business Account ID - phoneNumberId: Meta phone number ID  | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

