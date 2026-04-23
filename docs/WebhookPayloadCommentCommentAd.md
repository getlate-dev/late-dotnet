# Zernio.Model.WebhookPayloadCommentCommentAd
Ad context. Present only when the comment was made on paid content. Instagram: populated from the webhook payload's `value.media.ad_id`/`ad_title`. Facebook: populated via a Graph API lookup of the parent post's `promotion_status`. Absent for comments on organic posts that are not currently promoted. 

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Id** | **string** | Meta ad ID (Instagram only). | [optional] 
**Title** | **string** | Ad creative title (Instagram only). | [optional] 
**PromotionStatus** | **string** | Facebook promotion status returned by Graph API. Common values: \&quot;active\&quot; (organic post currently boosted), \&quot;ineligible\&quot; (dark post / ad creative — not promotable because it already is an ad).  | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

