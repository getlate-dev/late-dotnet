# Zernio.Model.AdMetrics

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Spend** | **decimal** |  | [optional] 
**Impressions** | **int** |  | [optional] 
**Reach** | **int** |  | [optional] 
**Clicks** | **int** |  | [optional] 
**Ctr** | **decimal** | Click-through rate (%) | [optional] 
**Cpc** | **decimal** | Cost per click | [optional] 
**Cpm** | **decimal** | Cost per 1000 impressions | [optional] 
**Engagement** | **int** |  | [optional] 
**Conversions** | **int** | Count of conversion events matching the campaign&#39;s promoted_object.custom_event_type (PURCHASE, LEAD, etc.) over the requested date range. 0 for non-conversion campaigns or when no events have fired. Meta-only at time of writing; other platforms return 0. | [optional] 
**CostPerConversion** | **decimal** | Derived spend / conversions in the same currency as spend. 0 when conversions is 0. | [optional] 
**Actions** | **Dictionary&lt;string, int&gt;** | Raw per-action-type counts from Meta&#39;s Insights actions[] array, summed over the date range. Keys are Meta action_type strings (e.g. link_click, offsite_conversion.fb_pixel_purchase, onsite_conversion.lead_grouped). Use this to extract any conversion event (purchases, leads, add_to_cart, etc.) without relying on the derived conversions field. Empty object when no actions are reported. | [optional] 
**ActionValues** | **Dictionary&lt;string, decimal&gt;** | Monetary mirror of &#x60;actions&#x60;, from Meta&#39;s Insights &#x60;action_values[]&#x60; array. Same keying — values are the revenue attributed to each action_type, in ad-account native currency (same unit as &#x60;spend&#x60;; see the campaign node&#39;s &#x60;currency&#x60; field). Use this to compute revenue-per-event (e.g. avg purchase value). Meta-only; other platforms return {}. | [optional] 
**PurchaseValue** | **decimal** | Convenience sum of purchase-type action values — picked from &#x60;actionValues&#x60; via the same priority list as &#x60;conversions&#x60; so both fields describe the same events. In ad-account native currency. 0 when the campaign has no purchase event configured. Meta-only. | [optional] 
**Roas** | **decimal** | Return on ad spend — derived as &#x60;purchaseValue / spend&#x60;. 0 when &#x60;spend&#x60; is 0. Equivalent to Meta&#39;s &#x60;purchase_roas&#x60; under default attribution. At ad-set and campaign levels this is recomputed from summed purchaseValue + spend (NOT averaged across children) so it&#39;s mathematically correct at every rollup level. | [optional] 
**LastSyncedAt** | **DateTime** | Present on individual ads only, not on campaign aggregations | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

