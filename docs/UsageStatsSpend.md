# Zernio.Model.UsageStatsSpend
Metronome users only. Current-period spend summary.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**CurrentPeriodCents** | **int** | Total current-period spend in cents (all products combined). | [optional] 
**CreditsRemainingCents** | **int** | Free-tier credit remaining in cents. Applied before any charge. | [optional] 
**XSpendCents** | **int** | Current-period X/Twitter API spend in cents, derived from the per-tier call counts. Rounded up for conservative enforcement against &#x60;xSpendLimitCents&#x60;.  | [optional] 
**XSpendLimitCents** | **int** | Monthly X spend cap set by the account owner, or null if no cap. When current X spend hits this cap, analytics and inbox sync are auto-paused for X accounts. Publishing is never blocked by this cap.  | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

