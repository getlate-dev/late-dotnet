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
**PlatformPostUrl** | **string** | Public URL of the published post. Included in the response for immediate posts; for scheduled posts, fetch via GET /v1/posts/{postId} after publish time. | [optional] 
**PublishedAt** | **DateTime** | Timestamp when the post was published to this platform | [optional] 
**ErrorMessage** | **string** | Human-readable error message when status is failed. Contains platform-specific error details explaining why the publish failed. | [optional] 
**ErrorCategory** | **string** | Error category for programmatic handling: auth_expired (token expired/revoked), user_content (wrong format/too long), user_abuse (rate limits/spam), account_issue (config problems), platform_rejected (policy violation), platform_error (5xx/maintenance), system_error (Late infra), unknown | [optional] 
**ErrorSource** | **string** | Who caused the error: user (fix content/reconnect), platform (outage/API change), system (Late issue, rare) | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

