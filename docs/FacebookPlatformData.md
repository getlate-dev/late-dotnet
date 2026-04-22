# Zernio.Model.FacebookPlatformData
Feed posts support up to 10 images (no mixed video+image). Stories require single media (24h, no captions). Reels require single vertical video (9:16, 3-60s). Geo-restriction is a hard visibility restriction: users outside the specified countries cannot see the post. Not supported for stories. 

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Draft** | **bool** | When true, creates the post as an unpublished draft visible in Facebook Publishing Tools instead of publishing immediately. Supported for feed posts (text, link, image, video) and reels. Not supported for stories. Drafts expire after ~30 days. | [optional] [default to false]
**ContentType** | **string** | Set to &#39;story&#39; for Page Stories (24h ephemeral) or &#39;reel&#39; for Reels (short vertical video). Defaults to feed post if omitted. | [optional] 
**Title** | **string** | Reel title (only for contentType&#x3D;reel). Separate from the caption/content field. | [optional] 
**FirstComment** | **string** | Optional first comment to post immediately after publishing (feed posts and reels, not stories). Skipped when draft is true. | [optional] 
**PageId** | **string** | Target Facebook Page ID for multi-page posting. If omitted, uses the default page. Use GET /v1/accounts/{id}/facebook-page to list pages. | [optional] 
**GeoRestriction** | [**GeoRestriction**](GeoRestriction.md) |  | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

