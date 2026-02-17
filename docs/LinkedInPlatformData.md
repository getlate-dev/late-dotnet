# Late.Model.LinkedInPlatformData
Up to 20 images, no multi-video. Single PDF supported (max 100MB, ~300 pages, cannot mix with other media). Link previews auto-generated when no media attached (disable with disableLinkPreview). Use organizationUrn for multi-org posting.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**OrganizationUrn** | **string** | Target LinkedIn Organization URN for multi-organization posting. Format: \&quot;urn:li:organization:123456789\&quot; If omitted, uses the selected/default organization on the connection. Use GET /api/v1/accounts/{id}/linkedin-organizations to list available organizations.  | [optional] 
**FirstComment** | **string** | Optional first comment to add after the post is created | [optional] 
**DisableLinkPreview** | **bool** | Set to true to disable automatic link previews for URLs in the post content (default is false) | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

