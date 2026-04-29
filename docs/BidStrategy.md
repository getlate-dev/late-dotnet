# Zernio.Model.BidStrategy
Meta bid strategy. Same enum applies at campaign and ad-set level; ad-set value (when set) overrides campaign-level. Cross-field rules:   - `LOWEST_COST_WITHOUT_CAP` (default): auto-bid, forbids `bidAmount` and `roasAverageFloor`.   - `LOWEST_COST_WITH_BID_CAP` / `COST_CAP`: require `bidAmount` (whole currency units).   - `LOWEST_COST_WITH_MIN_ROAS`: requires `roasAverageFloor` (decimal multiplier, 2.0 = 2.0x). Source: facebook-business-sdk-codegen api_specs/specs/enum_types.json (`AdSet_bid_strategy`, `Campaign_bid_strategy`). 

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

