# Zernio.Model.UpdateAdSetRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Platform** | **string** |  | 
**Budget** | [**UpdateAdSetRequestBudget**](UpdateAdSetRequestBudget.md) |  | [optional] 
**Status** | **string** | Omit if not toggling delivery state | [optional] 
**BidStrategy** | **BidStrategy** | Ad-set-level bid strategy. Overrides the campaign-level default. Supported on Meta (facebook, instagram) and TikTok. On TikTok the Meta-style enum is mapped to bid_type / bid_price / deep_bid_type automatically. Other platforms (linkedin, pinterest, google, twitter) return 501 Not Implemented when bidStrategy is set.  | [optional] 
**BidAmount** | **decimal** | Bid cap in WHOLE currency units (USD: 5 &#x3D; $5.00; JPY: 100 &#x3D; ¥100). Required when bidStrategy is LOWEST_COST_WITH_BID_CAP or COST_CAP. Internally converted to Meta&#39;s smallest-denomination integer.  | [optional] 
**RoasAverageFloor** | **decimal** | Minimum ROAS as a decimal multiplier (2.0 &#x3D; 2.0x). Required when bidStrategy is LOWEST_COST_WITH_MIN_ROAS. Sent to Meta as &#x60;bid_constraints.roas_average_floor&#x60; × 10000.  | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

