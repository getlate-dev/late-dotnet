# Zernio.Model.UsageStats
Plan and usage stats. The response shape depends on `billingSystem`:   * Stripe users (default): per-period counters like `usage.uploads` and     `usage.profiles` are returned, scoped by the plan's `limits`.   * Metronome users (usage-based): `limits` are unlimited (-1). The     `usage` block carries connected-account and per-X-operation counts,     and the `spend` block carries current-period costs plus the X cap. 

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**BillingSystem** | **string** | Which billing system the account is on. Shape of &#x60;usage&#x60;/&#x60;spend&#x60; differs. | [optional] 
**PlanName** | **string** |  | [optional] 
**BillingPeriod** | **string** |  | [optional] 
**SignupDate** | **DateTime** |  | [optional] 
**BillingAnchorDay** | **int** | Day of month (1-31) when the billing cycle resets | [optional] 
**HasAccess** | **bool** | True if the account is in good standing. False for past-due/unpaid/paused subscriptions. | [optional] 
**CustomerId** | **string** | Stripe customer ID, when present. | [optional] 
**IsInvitedUser** | **bool** | True if this is a team member; limits/usage reflect the account owner. | [optional] 
**AutoUpgradeEnabled** | **bool** | Stripe-only. Always false for Metronome users. | [optional] 
**Limits** | [**UsageStatsLimits**](UsageStatsLimits.md) |  | [optional] 
**Usage** | [**UsageStatsUsage**](UsageStatsUsage.md) |  | [optional] 
**Spend** | [**UsageStatsSpend**](UsageStatsSpend.md) |  | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

