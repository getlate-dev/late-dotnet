# Zernio.Model.XApiPricing
Canonical X/Twitter API pricing table. Zernio passes X API costs through at exact rates with zero markup, so every call you make has a known per-unit price. Use this payload alongside `/v1/usage-stats` (which returns per-operation call counts via `xApiCallsByOperation`) to compute exact cost attribution by X action. 

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Currency** | **string** |  | [optional] 
**Markup** | **string** | Always 0% — Zernio does not mark up X API rates. | [optional] 
**Source** | **string** |  | [optional] 
**LastVerified** | **DateOnly** | Date the prices were last verified against X&#39;s published rates. | [optional] 
**Tiers** | [**List&lt;XApiPricingTiersInner&gt;**](XApiPricingTiersInner.md) | Rollup of operations grouped by their per-call price. | [optional] 
**Operations** | [**List&lt;XApiOperation&gt;**](XApiOperation.md) | Flat list of every X operation Zernio can perform, with its rate. | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

