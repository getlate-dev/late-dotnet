# Zernio.Model.InstagramAccountInsightsResponse
Shared account-insights response envelope used by every platform-level analytics endpoint (/v1/analytics/{facebook|instagram|youtube|linkedin|tiktok}/_*). The name is historical - the shape was first shipped for Instagram and every new platform endpoint reuses it for response-shape consistency. The platform field echoes back which platform served the response. 

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Success** | **bool** |  | [optional] 
**AccountId** | **string** | The Zernio SocialAccount ID | [optional] 
**Platform** | **string** | Platform that served this response. | [optional] 
**DateRange** | [**InstagramAccountInsightsResponseDateRange**](InstagramAccountInsightsResponseDateRange.md) |  | [optional] 
**MetricType** | **string** |  | [optional] 
**Breakdown** | **string** | Breakdown dimension used (only present when breakdown was requested) | [optional] 
**Metrics** | [**Dictionary&lt;string, InstagramAccountInsightsResponseMetricsValue&gt;**](InstagramAccountInsightsResponseMetricsValue.md) | Object keyed by metric name. For time_series: each metric has \&quot;total\&quot; (number) and \&quot;values\&quot; (array of {date, value}). For total_value: each metric has \&quot;total\&quot; (number) and optionally \&quot;breakdowns\&quot; (array of {dimension, value}).  | [optional] 
**DataDelay** | **string** |  | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

