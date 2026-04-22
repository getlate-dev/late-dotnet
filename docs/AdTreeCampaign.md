# Zernio.Model.AdTreeCampaign
Campaign with nested ad sets and rolled-up metrics

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**PlatformCampaignId** | **string** |  | [optional] 
**Platform** | **string** |  | [optional] 
**CampaignName** | **string** |  | [optional] 
**Status** | **AdStatus** | Delivery status derived from child ad statuses. Distinct from &#x60;reviewStatus&#x60;, which reflects the platform-side review state. | [optional] 
**ReviewStatus** | **string** | Platform-side review state of the campaign. Independent of the children-derived delivery &#x60;status&#x60;: a campaign can have ads already active (status&#x3D;active) while the campaign itself is still being reviewed by the platform (reviewStatus&#x3D;in_review). For Meta, derived from &#x60;effective_status&#x60; + &#x60;issues_info&#x60; on the Campaign, plus ad-level PENDING_REVIEW rollup.  | [optional] 
**PlatformCampaignStatus** | **string** | Raw platform-level campaign status (Meta &#x60;effective_status&#x60;: ACTIVE, PAUSED, DELETED, ARCHIVED, IN_PROCESS, WITH_ISSUES). Distinct from per-ad &#x60;platformStatus&#x60;. | [optional] 
**CampaignIssuesInfo** | **List&lt;Object&gt;** | Platform-reported campaign issues (Meta &#x60;issues_info[]&#x60;). Populated only when the platform has delivery issues to report; contains the specific error codes and messages. | [optional] 
**AdCount** | **int** | Total ads across all ad sets | [optional] 
**AdSetCount** | **int** |  | [optional] 
**Budget** | [**AdTreeCampaignBudget**](AdTreeCampaignBudget.md) |  | [optional] 
**CampaignBudget** | [**AdTreeCampaignCampaignBudget**](AdTreeCampaignCampaignBudget.md) |  | [optional] 
**BudgetLevel** | **string** | Canonical CBO/ABO indicator. &#x60;campaign&#x60; &#x3D; CBO (Advantage Campaign Budget, budget lives on the campaign). &#x60;adset&#x60; &#x3D; ABO (budget lives on each ad set). Route budget updates to the matching Meta entity. | [optional] 
**IsBudgetScheduleEnabled** | **bool** | Meta-only. Mirrors Campaign.is_budget_schedule_enabled — true when the campaign uses budget scheduling (time-based budget changes). Independent of CBO/ABO. | [optional] [default to false]
**Currency** | **string** | ISO 4217 currency code (e.g. USD, EUR, CLP, JPY) for all budget amounts in this campaign node. Budgets are NOT normalized to USD. | [optional] 
**Metrics** | [**AdMetrics**](AdMetrics.md) |  | [optional] 
**PlatformAdAccountId** | **string** |  | [optional] 
**AccountId** | **string** |  | [optional] 
**ProfileId** | **string** |  | [optional] 
**PlatformObjective** | **string** | Raw Meta campaign objective (e.g. OUTCOME_SALES, OUTCOME_LEADS, OUTCOME_TRAFFIC) | [optional] 
**OptimizationGoal** | **string** | Meta optimization goal shared across ad sets, or comma-separated values when ad sets differ (e.g. OFFSITE_CONVERSIONS, VALUE, LEAD_GENERATION) | [optional] 
**BidStrategy** | **string** | Campaign-level bid strategy (e.g. LOWEST_COST_WITHOUT_CAP, COST_CAP, LOWEST_COST_WITH_MIN_ROAS) | [optional] 
**PromotedObject** | [**AdTreeCampaignPromotedObject**](AdTreeCampaignPromotedObject.md) |  | [optional] 
**AdSets** | [**List&lt;AdTreeAdSet&gt;**](AdTreeAdSet.md) |  | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

