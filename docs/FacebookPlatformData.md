# Late.Model.FacebookPlatformData
Constraints: - Posts cannot mix videos and images. - Multiple images supported via attached_media (up to 10 images for feed posts). - Multiple videos in the same post are not supported. - Stories require media (single image or video); text captions are not displayed with stories. - Stories are ephemeral (disappear after 24 hours). - Use pageId to post to multiple pages from the same account connection. 

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**ContentType** | **string** | Set to &#39;story&#39; to publish as a Facebook Page Story (24-hour ephemeral content). Requires media. | [optional] 
**FirstComment** | **string** | Optional first comment to post immediately after publishing (feed posts only, not stories) | [optional] 
**PageId** | **string** | Target Facebook Page ID for multi-page posting. If omitted, uses the selected/default page on the connection. Use GET /api/v1/accounts/{id}/facebook-page to list available pages.  | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

