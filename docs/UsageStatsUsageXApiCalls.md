# Zernio.Model.UsageStatsUsageXApiCalls
Metronome users only. Aggregated X API call counts bucketed by price tier (backward-compat). For per-operation breakdown use `xApiCallsByOperation`. 

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**XApi005** | **int** | Calls at $0.005 per call (reads, list mgmt, bookmarks, etc.) | [optional] 
**XApi010** | **int** | Calls at $0.010 per call (publish/delete, DM reads, follows) | [optional] 
**XApi015** | **int** | Calls at $0.015 per call (sending DMs, follow actions) | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

