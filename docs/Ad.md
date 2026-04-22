# Zernio.Model.Ad

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Id** | **string** |  | [optional] 
**Name** | **string** |  | [optional] 
**Platform** | **string** |  | [optional] 
**Status** | **AdStatus** |  | [optional] 
**AdType** | **string** |  | [optional] 
**Goal** | **string** | Available goals vary by platform. Meta (Facebook/Instagram) and TikTok support all 7. LinkedIn supports all except app_promotion. Twitter/X supports engagement, traffic, awareness, video_views, app_promotion. Pinterest and Google Ads support only engagement, traffic, awareness, video_views. | [optional] 
**IsExternal** | **bool** | True for ads synced from platform ad managers | [optional] 
**Budget** | [**AdBudget**](AdBudget.md) |  | [optional] 
**Metrics** | [**AdMetrics**](AdMetrics.md) |  | [optional] 
**PlatformAdId** | **string** |  | [optional] 
**PlatformAdAccountId** | **string** |  | [optional] 
**PlatformCampaignId** | **string** |  | [optional] 
**PlatformAdSetId** | **string** |  | [optional] 
**CampaignName** | **string** |  | [optional] 
**AdSetName** | **string** |  | [optional] 
**PlatformObjective** | **string** | Raw Meta campaign objective (e.g. OUTCOME_SALES, OUTCOME_LEADS, OUTCOME_TRAFFIC). Only present for Meta ads. | [optional] 
**OptimizationGoal** | **string** | Meta ad set optimization goal (e.g. OFFSITE_CONVERSIONS, VALUE, LEAD_GENERATION, LINK_CLICKS). Only present for Meta ads. | [optional] 
**BidStrategy** | **string** | Bid strategy (e.g. LOWEST_COST_WITHOUT_CAP, COST_CAP, LOWEST_COST_WITH_MIN_ROAS). Ad set level overrides campaign level. Only present for Meta ads. | [optional] 
**PromotedObject** | [**AdPromotedObject**](AdPromotedObject.md) |  | [optional] 
**Creative** | [**AdCreative**](AdCreative.md) |  | [optional] 
**Targeting** | **Object** |  | [optional] 
**Schedule** | [**AdSchedule**](AdSchedule.md) |  | [optional] 
**RejectionReason** | **string** |  | [optional] 
**CreatedAt** | **DateTime** |  | [optional] 
**UpdatedAt** | **DateTime** |  | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

