# Late.Model.AdTreeAdSet
Ad set (or ad group/line item depending on platform) with rolled-up metrics and child ads

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**PlatformAdSetId** | **string** |  | [optional] 
**AdSetName** | **string** |  | [optional] 
**Status** | **AdStatus** | Derived from child ad statuses | [optional] 
**AdCount** | **int** |  | [optional] 
**Budget** | [**AdBudget**](AdBudget.md) |  | [optional] 
**Metrics** | [**AdMetrics**](AdMetrics.md) |  | [optional] 
**OptimizationGoal** | **string** | Meta ad set optimization goal (e.g. OFFSITE_CONVERSIONS, VALUE, LEAD_GENERATION) | [optional] 
**BidStrategy** | **string** | Bid strategy for this ad set (overrides campaign level when set) | [optional] 
**PromotedObject** | [**AdTreeAdSetPromotedObject**](AdTreeAdSetPromotedObject.md) |  | [optional] 
**Ads** | [**List&lt;Ad&gt;**](Ad.md) | Individual ads within this ad set (capped at 100). Returns a subset of Ad fields from the aggregation (core fields like _id, name, platform, status, budget, metrics, creative, goal are included; targeting and schedule may be absent). | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

