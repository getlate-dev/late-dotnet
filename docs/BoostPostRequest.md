# Late.Model.BoostPostRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**PostId** | **string** | Zernio post ID (provide this or platformPostId) | [optional] 
**PlatformPostId** | **string** | Platform post ID (alternative to postId) | [optional] 
**AccountId** | **string** | Social account ID | 
**AdAccountId** | **string** | Platform ad account ID | 
**Name** | **string** |  | 
**Goal** | **string** | Available goals vary by platform. Meta (Facebook/Instagram) and TikTok support all 7. LinkedIn supports all except app_promotion. Twitter/X supports engagement, traffic, awareness, video_views, app_promotion. Pinterest and Google Ads support only engagement, traffic, awareness, video_views. | 
**Budget** | [**BoostPostRequestBudget**](BoostPostRequestBudget.md) |  | 
**Currency** | **string** |  | [optional] 
**Schedule** | [**BoostPostRequestSchedule**](BoostPostRequestSchedule.md) |  | [optional] 
**Targeting** | [**BoostPostRequestTargeting**](BoostPostRequestTargeting.md) |  | [optional] 
**BidAmount** | **decimal** | Max bid cap (Meta only) | [optional] 
**Tracking** | [**BoostPostRequestTracking**](BoostPostRequestTracking.md) |  | [optional] 
**SpecialAdCategories** | **List&lt;BoostPostRequest.SpecialAdCategoriesEnum&gt;** | Meta only. Required for housing, employment, credit, or political ads. | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

