# Late.Model.LinkedInPlatformData
Up to 20 images, no multi-video. Single PDF supported (max 100MB). Link previews auto-generated when no media attached. Use organizationUrn for multi-org posting.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**DocumentTitle** | **string** | Title displayed on LinkedIn document (PDF/carousel) posts. Required by LinkedIn for document posts. If omitted, falls back to the media item title, then the filename. | [optional] 
**OrganizationUrn** | **string** | Target LinkedIn Organization URN (e.g. \&quot;urn:li:organization:123456789\&quot;). If omitted, uses the default org. Use GET /v1/accounts/{id}/linkedin-organizations to list orgs. | [optional] 
**FirstComment** | **string** | Optional first comment to add after the post is created | [optional] 
**DisableLinkPreview** | **bool** | Set to true to disable automatic link previews for URLs in the post content (default is false) | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

