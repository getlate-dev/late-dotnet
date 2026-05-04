# Zernio.Model.UsageStatsUsage
Per-period usage counts. Fields present depend on `billingSystem`: Stripe returns `uploads` / `profiles` / `lastReset`; Metronome returns `connectedAccounts` / `xApiCalls` / `xApiCallsByOperation`. 

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Uploads** | **int** | Stripe users only. Uploads consumed in the current period. | [optional] 
**Profiles** | **int** | Stripe users only. Profiles currently owned. | [optional] 
**LastReset** | **DateTime** | Stripe users only. | [optional] 
**ConnectedAccounts** | **int** | Metronome users only. Accounts currently connected across the team. | [optional] 
**XApiCalls** | [**UsageStatsUsageXApiCalls**](UsageStatsUsageXApiCalls.md) |  | [optional] 
**XApiCallsByOperation** | **Dictionary&lt;string, int&gt;** | Metronome users only. Per-operation X API call counts keyed by operation (e.g. &#x60;posts_read&#x60;, &#x60;content_create&#x60;). Resolve each key to price and metadata via &#x60;GET /v1/billing/x-pricing&#x60;.  | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

