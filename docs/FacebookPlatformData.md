# Late.Model.FacebookPlatformData
Cannot mix videos and images. Up to 10 images for feed posts. Stories require single image or video (no captions, ephemeral 24h). Use pageId for multi-page posting.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**ContentType** | **string** | Set to &#39;story&#39; to publish as a Facebook Page Story (24-hour ephemeral content). Requires media. | [optional] 
**FirstComment** | **string** | Optional first comment to post immediately after publishing (feed posts only, not stories) | [optional] 
**PageId** | **string** | Target Facebook Page ID for multi-page posting. If omitted, uses the selected/default page on the connection. Use GET /api/v1/accounts/{id}/facebook-page to list available pages.  | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

