# Late.Model.AdTreeCampaign
Campaign with nested ad sets and rolled-up metrics

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**PlatformCampaignId** | **string** |  | [optional] 
**Platform** | **string** |  | [optional] 
**CampaignName** | **string** |  | [optional] 
**Status** | **string** | Derived from child ad statuses | [optional] 
**AdCount** | **int** | Total ads across all ad sets | [optional] 
**AdSetCount** | **int** |  | [optional] 
**Budget** | [**AdBudget**](AdBudget.md) |  | [optional] 
**Metrics** | [**AdMetrics**](AdMetrics.md) |  | [optional] 
**PlatformAdAccountId** | **string** |  | [optional] 
**AccountId** | **string** |  | [optional] 
**ProfileId** | **string** |  | [optional] 
**AdSets** | [**List&lt;AdTreeAdSet&gt;**](AdTreeAdSet.md) |  | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

