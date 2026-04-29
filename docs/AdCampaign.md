# Zernio.Model.AdCampaign

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**PlatformCampaignId** | **string** |  | [optional] 
**Platform** | **string** |  | [optional] 
**CampaignName** | **string** |  | [optional] 
**Status** | **AdStatus** | Delivery status derived from child ad statuses. Distinct from &#x60;reviewStatus&#x60;. | [optional] 
**ReviewStatus** | **string** | Platform-side review state of the campaign. See AdTreeCampaign.reviewStatus for the full description. | [optional] 
**PlatformCampaignStatus** | **string** | Raw platform-level campaign status (Meta &#x60;effective_status&#x60;). | [optional] 
**CampaignIssuesInfo** | **List&lt;Object&gt;** | Platform-reported campaign issues (Meta &#x60;issues_info[]&#x60;). | [optional] 
**AdCount** | **int** |  | [optional] 
**Budget** | [**AdCampaignBudget**](AdCampaignBudget.md) |  | [optional] 
**CampaignBudget** | [**AdCampaignCampaignBudget**](AdCampaignCampaignBudget.md) |  | [optional] 
**BudgetLevel** | **string** | Canonical CBO/ABO indicator. See AdTreeCampaign.budgetLevel. | [optional] 
**IsBudgetScheduleEnabled** | **bool** | Meta-only. Mirrors Campaign.is_budget_schedule_enabled. | [optional] [default to false]
**Currency** | **string** | ISO 4217 currency code for all budget amounts. Budgets are NOT normalized to USD. | [optional] 
**Metrics** | [**AdMetrics**](AdMetrics.md) |  | [optional] 
**PlatformAdAccountId** | **string** |  | [optional] 
**AccountId** | **string** |  | [optional] 
**ProfileId** | **string** |  | [optional] 
**PlatformObjective** | **string** | Raw Meta campaign objective (e.g. OUTCOME_SALES, OUTCOME_LEADS, OUTCOME_TRAFFIC) | [optional] 
**OptimizationGoal** | **string** | Meta optimization goal shared across ad sets, or comma-separated values when ad sets differ (e.g. OFFSITE_CONVERSIONS, VALUE, LEAD_GENERATION) | [optional] 
**BidStrategy** | **BidStrategy** | Campaign-level bid strategy. Ad sets inherit this unless they override. | [optional] 
**BidAmount** | **decimal** | Representative bid cap from the top-spending ad set (whole currency units). Populated when bidStrategy is LOWEST_COST_WITH_BID_CAP or COST_CAP. | [optional] 
**RoasAverageFloor** | **decimal** | Representative ROAS floor from the top-spending ad set. Decimal multiplier (2.0 &#x3D; 2.0x). | [optional] 
**PromotedObject** | [**AdTreeCampaignPromotedObject**](AdTreeCampaignPromotedObject.md) |  | [optional] 
**EarliestAd** | **DateTime** |  | [optional] 
**LatestAd** | **DateTime** |  | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

