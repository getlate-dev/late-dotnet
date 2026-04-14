# Late.Model.AdCampaign

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**PlatformCampaignId** | **string** |  | [optional] 
**Platform** | **string** |  | [optional] 
**CampaignName** | **string** |  | [optional] 
**Status** | **AdStatus** | Derived from child ad statuses | [optional] 
**AdCount** | **int** |  | [optional] 
**Budget** | [**AdBudget**](AdBudget.md) |  | [optional] 
**Metrics** | [**AdMetrics**](AdMetrics.md) |  | [optional] 
**PlatformAdAccountId** | **string** |  | [optional] 
**AccountId** | **string** |  | [optional] 
**ProfileId** | **string** |  | [optional] 
**PlatformObjective** | **string** | Raw Meta campaign objective (e.g. OUTCOME_SALES, OUTCOME_LEADS, OUTCOME_TRAFFIC) | [optional] 
**OptimizationGoal** | **string** | Meta optimization goal shared across ad sets, or comma-separated values when ad sets differ (e.g. OFFSITE_CONVERSIONS, VALUE, LEAD_GENERATION) | [optional] 
**BidStrategy** | **string** | Campaign-level bid strategy (e.g. LOWEST_COST_WITHOUT_CAP, COST_CAP, LOWEST_COST_WITH_MIN_ROAS) | [optional] 
**PromotedObject** | [**AdTreeCampaignPromotedObject**](AdTreeCampaignPromotedObject.md) |  | [optional] 
**EarliestAd** | **DateTime** |  | [optional] 
**LatestAd** | **DateTime** |  | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

