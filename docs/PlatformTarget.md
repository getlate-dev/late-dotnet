# Late.Model.PlatformTarget

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Platform** | **string** | Supported values: twitter, threads, instagram, youtube, facebook, linkedin, pinterest, reddit, tiktok, bluesky, googlebusiness, telegram | [optional] 
**AccountId** | [**PlatformTargetAccountId**](PlatformTargetAccountId.md) |  | [optional] 
**CustomContent** | **string** | Platform-specific text override. When set, this content is used instead of the top-level post content for this platform. Useful for tailoring captions per platform (e.g. keeping tweets under 280 characters). | [optional] 
**CustomMedia** | [**List&lt;MediaItem&gt;**](MediaItem.md) |  | [optional] 
**ScheduledFor** | **DateTime** | Optional per-platform scheduled time override (uses post.scheduledFor when omitted) | [optional] 
**PlatformSpecificData** | [**PlatformTargetPlatformSpecificData**](PlatformTargetPlatformSpecificData.md) |  | [optional] 
**Status** | **string** | Platform-specific status: pending, publishing, published, failed | [optional] 
**PlatformPostId** | **string** | The native post ID on the platform (populated after successful publish) | [optional] 
**PlatformPostUrl** | **string** | Public URL of the published post on the platform. Populated after successful publish. For immediate posts (publishNow&#x3D;true),  this is included in the response. For scheduled posts, fetch the post  via GET /v1/posts/{postId} after the scheduled time.  | [optional] 
**PublishedAt** | **DateTime** | Timestamp when the post was published to this platform | [optional] 
**ErrorMessage** | **string** | Human-readable error message when status is &#39;failed&#39;. Contains platform-specific error details explaining why the publish failed. Examples: - \&quot;Instagram access token has expired. Please reconnect your account.\&quot; - \&quot;Post text exceeds the 500 character limit for Threads.\&quot; - \&quot;You do not have enough karma to post in this subreddit.\&quot; - \&quot;Video is too long for Reels. Facebook Reels must be 90 seconds or less.\&quot;  | [optional] 
**ErrorCategory** | **string** | Error category for programmatic handling: - auth_expired: Token expired or revoked, account needs reconnection - user_content: Content doesn&#39;t meet platform requirements (too long, wrong format, etc.) - user_abuse: Rate limits, spam detection, excessive posting - account_issue: Account configuration problems (missing board, inactive account) - platform_rejected: Platform rules violated (banned, suspended, policy violation) - platform_error: Platform-side issues (5xx errors, maintenance) - system_error: Late infrastructure issues (timeouts, network errors) - unknown: Unclassified error  | [optional] 
**ErrorSource** | **string** | Who/what caused the error: - user: User action required (fix content, reconnect account) - platform: Platform-side issue (outage, API change) - system: Late system issue (rare)  | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

