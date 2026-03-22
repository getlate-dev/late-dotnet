# Late.Api.AnalyticsApi

All URIs are relative to *https://zernio.com/api*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**GetAnalytics**](AnalyticsApi.md#getanalytics) | **GET** /v1/analytics | Get post analytics |
| [**GetBestTimeToPost**](AnalyticsApi.md#getbesttimetopost) | **GET** /v1/analytics/best-time | Get best times to post |
| [**GetContentDecay**](AnalyticsApi.md#getcontentdecay) | **GET** /v1/analytics/content-decay | Get content performance decay |
| [**GetDailyMetrics**](AnalyticsApi.md#getdailymetrics) | **GET** /v1/analytics/daily-metrics | Get daily aggregated metrics |
| [**GetFollowerStats**](AnalyticsApi.md#getfollowerstats) | **GET** /v1/accounts/follower-stats | Get follower stats |
| [**GetInstagramAccountInsights**](AnalyticsApi.md#getinstagramaccountinsights) | **GET** /v1/analytics/instagram/account-insights | Get Instagram account-level insights |
| [**GetInstagramDemographics**](AnalyticsApi.md#getinstagramdemographics) | **GET** /v1/analytics/instagram/demographics | Get Instagram audience demographics |
| [**GetLinkedInAggregateAnalytics**](AnalyticsApi.md#getlinkedinaggregateanalytics) | **GET** /v1/accounts/{accountId}/linkedin-aggregate-analytics | Get LinkedIn aggregate stats |
| [**GetLinkedInPostAnalytics**](AnalyticsApi.md#getlinkedinpostanalytics) | **GET** /v1/accounts/{accountId}/linkedin-post-analytics | Get LinkedIn post stats |
| [**GetLinkedInPostReactions**](AnalyticsApi.md#getlinkedinpostreactions) | **GET** /v1/accounts/{accountId}/linkedin-post-reactions | Get LinkedIn post reactions |
| [**GetPostTimeline**](AnalyticsApi.md#getposttimeline) | **GET** /v1/analytics/post-timeline | Get post analytics timeline |
| [**GetPostingFrequency**](AnalyticsApi.md#getpostingfrequency) | **GET** /v1/analytics/posting-frequency | Get posting frequency vs engagement |
| [**GetYouTubeDailyViews**](AnalyticsApi.md#getyoutubedailyviews) | **GET** /v1/analytics/youtube/daily-views | Get YouTube daily views |

<a id="getanalytics"></a>
# **GetAnalytics**
> GetAnalytics200Response GetAnalytics (string? postId = null, string? platform = null, string? profileId = null, string? source = null, DateOnly? fromDate = null, DateOnly? toDate = null, int? limit = null, int? page = null, string? sortBy = null, string? order = null)

Get post analytics

Returns analytics for posts. With postId, returns a single post. Without it, returns a paginated list with overview stats. Accepts both Zernio Post IDs and External Post IDs (auto-resolved). fromDate defaults to 90 days ago if omitted, max range 366 days. Single post lookups may return 202 (sync pending) or 424 (all platforms failed). For follower stats, use /v1/accounts/follower-stats. 

### Example
```csharp
using System.Collections.Generic;
using System.Diagnostics;
using System.Net.Http;
using Late.Api;
using Late.Client;
using Late.Model;

namespace Example
{
    public class GetAnalyticsExample
    {
        public static void Main()
        {
            Configuration config = new Configuration();
            config.BasePath = "https://zernio.com/api";
            // Configure Bearer token for authorization: bearerAuth
            config.AccessToken = "YOUR_BEARER_TOKEN";

            // create instances of HttpClient, HttpClientHandler to be reused later with different Api classes
            HttpClient httpClient = new HttpClient();
            HttpClientHandler httpClientHandler = new HttpClientHandler();
            var apiInstance = new AnalyticsApi(httpClient, config, httpClientHandler);
            var postId = "postId_example";  // string? | Returns analytics for a single post. Accepts both Zernio Post IDs and External Post IDs. Zernio IDs are auto-resolved to External Post analytics. (optional) 
            var platform = "platform_example";  // string? | Filter by platform (default \"all\") (optional) 
            var profileId = "profileId_example";  // string? | Filter by profile ID (default \"all\") (optional) 
            var source = "all";  // string? | Filter by post source: late (posted via Zernio API), external (synced from platform), all (default) (optional)  (default to all)
            var fromDate = DateOnly.Parse("2013-10-20");  // DateOnly? | Inclusive lower bound (YYYY-MM-DD). Defaults to 90 days ago if omitted. Max range is 366 days. (optional) 
            var toDate = DateOnly.Parse("2013-10-20");  // DateOnly? | Inclusive upper bound (YYYY-MM-DD). Defaults to today if omitted. (optional) 
            var limit = 50;  // int? | Page size (default 50) (optional)  (default to 50)
            var page = 1;  // int? | Page number (default 1) (optional)  (default to 1)
            var sortBy = "date";  // string? | Sort by date, engagement, or a specific metric (optional)  (default to date)
            var order = "asc";  // string? | Sort order (optional)  (default to desc)

            try
            {
                // Get post analytics
                GetAnalytics200Response result = apiInstance.GetAnalytics(postId, platform, profileId, source, fromDate, toDate, limit, page, sortBy, order);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling AnalyticsApi.GetAnalytics: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the GetAnalyticsWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Get post analytics
    ApiResponse<GetAnalytics200Response> response = apiInstance.GetAnalyticsWithHttpInfo(postId, platform, profileId, source, fromDate, toDate, limit, page, sortBy, order);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling AnalyticsApi.GetAnalyticsWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **postId** | **string?** | Returns analytics for a single post. Accepts both Zernio Post IDs and External Post IDs. Zernio IDs are auto-resolved to External Post analytics. | [optional]  |
| **platform** | **string?** | Filter by platform (default \&quot;all\&quot;) | [optional]  |
| **profileId** | **string?** | Filter by profile ID (default \&quot;all\&quot;) | [optional]  |
| **source** | **string?** | Filter by post source: late (posted via Zernio API), external (synced from platform), all (default) | [optional] [default to all] |
| **fromDate** | **DateOnly?** | Inclusive lower bound (YYYY-MM-DD). Defaults to 90 days ago if omitted. Max range is 366 days. | [optional]  |
| **toDate** | **DateOnly?** | Inclusive upper bound (YYYY-MM-DD). Defaults to today if omitted. | [optional]  |
| **limit** | **int?** | Page size (default 50) | [optional] [default to 50] |
| **page** | **int?** | Page number (default 1) | [optional] [default to 1] |
| **sortBy** | **string?** | Sort by date, engagement, or a specific metric | [optional] [default to date] |
| **order** | **string?** | Sort order | [optional] [default to desc] |

### Return type

[**GetAnalytics200Response**](GetAnalytics200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Analytics result |  -  |
| **202** | Analytics are being synced from the platform (single post lookup only). The response body matches AnalyticsSinglePostResponse with syncStatus \&quot;pending\&quot; and a message. |  -  |
| **400** | Validation error |  -  |
| **401** | Unauthorized |  -  |
| **402** | Analytics add-on required |  -  |
| **404** | Resource not found |  -  |
| **424** | Post failed to publish on all platforms. Analytics are unavailable. (single post lookup only) |  -  |
| **500** | Internal server error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="getbesttimetopost"></a>
# **GetBestTimeToPost**
> GetBestTimeToPost200Response GetBestTimeToPost (string? platform = null, string? profileId = null, string? source = null)

Get best times to post

Returns the best times to post based on historical engagement data. Groups all published posts by day of week and hour (UTC), calculating average engagement per slot. Use this to auto-schedule posts at optimal times. Requires the Analytics add-on. 

### Example
```csharp
using System.Collections.Generic;
using System.Diagnostics;
using System.Net.Http;
using Late.Api;
using Late.Client;
using Late.Model;

namespace Example
{
    public class GetBestTimeToPostExample
    {
        public static void Main()
        {
            Configuration config = new Configuration();
            config.BasePath = "https://zernio.com/api";
            // Configure Bearer token for authorization: bearerAuth
            config.AccessToken = "YOUR_BEARER_TOKEN";

            // create instances of HttpClient, HttpClientHandler to be reused later with different Api classes
            HttpClient httpClient = new HttpClient();
            HttpClientHandler httpClientHandler = new HttpClientHandler();
            var apiInstance = new AnalyticsApi(httpClient, config, httpClientHandler);
            var platform = "platform_example";  // string? | Filter by platform (e.g. \"instagram\", \"tiktok\"). Omit for all platforms. (optional) 
            var profileId = "profileId_example";  // string? | Filter by profile ID. Omit for all profiles. (optional) 
            var source = "all";  // string? | Filter by post origin. \"late\" for posts published via Zernio, \"external\" for posts imported from platforms. (optional)  (default to all)

            try
            {
                // Get best times to post
                GetBestTimeToPost200Response result = apiInstance.GetBestTimeToPost(platform, profileId, source);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling AnalyticsApi.GetBestTimeToPost: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the GetBestTimeToPostWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Get best times to post
    ApiResponse<GetBestTimeToPost200Response> response = apiInstance.GetBestTimeToPostWithHttpInfo(platform, profileId, source);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling AnalyticsApi.GetBestTimeToPostWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **platform** | **string?** | Filter by platform (e.g. \&quot;instagram\&quot;, \&quot;tiktok\&quot;). Omit for all platforms. | [optional]  |
| **profileId** | **string?** | Filter by profile ID. Omit for all profiles. | [optional]  |
| **source** | **string?** | Filter by post origin. \&quot;late\&quot; for posts published via Zernio, \&quot;external\&quot; for posts imported from platforms. | [optional] [default to all] |

### Return type

[**GetBestTimeToPost200Response**](GetBestTimeToPost200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Best time slots |  -  |
| **401** | Unauthorized |  -  |
| **403** | Analytics add-on required |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="getcontentdecay"></a>
# **GetContentDecay**
> GetContentDecay200Response GetContentDecay (string? platform = null, string? profileId = null, string? source = null)

Get content performance decay

Returns how engagement accumulates over time after a post is published. Each bucket shows what percentage of the post's total engagement had been reached by that time window. Useful for understanding content lifespan (e.g. \"posts reach 78% of total engagement within 24 hours\"). Requires the Analytics add-on. 

### Example
```csharp
using System.Collections.Generic;
using System.Diagnostics;
using System.Net.Http;
using Late.Api;
using Late.Client;
using Late.Model;

namespace Example
{
    public class GetContentDecayExample
    {
        public static void Main()
        {
            Configuration config = new Configuration();
            config.BasePath = "https://zernio.com/api";
            // Configure Bearer token for authorization: bearerAuth
            config.AccessToken = "YOUR_BEARER_TOKEN";

            // create instances of HttpClient, HttpClientHandler to be reused later with different Api classes
            HttpClient httpClient = new HttpClient();
            HttpClientHandler httpClientHandler = new HttpClientHandler();
            var apiInstance = new AnalyticsApi(httpClient, config, httpClientHandler);
            var platform = "platform_example";  // string? | Filter by platform (e.g. \"instagram\", \"tiktok\"). Omit for all platforms. (optional) 
            var profileId = "profileId_example";  // string? | Filter by profile ID. Omit for all profiles. (optional) 
            var source = "all";  // string? | Filter by post origin. \"late\" for posts published via Zernio, \"external\" for posts imported from platforms. (optional)  (default to all)

            try
            {
                // Get content performance decay
                GetContentDecay200Response result = apiInstance.GetContentDecay(platform, profileId, source);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling AnalyticsApi.GetContentDecay: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the GetContentDecayWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Get content performance decay
    ApiResponse<GetContentDecay200Response> response = apiInstance.GetContentDecayWithHttpInfo(platform, profileId, source);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling AnalyticsApi.GetContentDecayWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **platform** | **string?** | Filter by platform (e.g. \&quot;instagram\&quot;, \&quot;tiktok\&quot;). Omit for all platforms. | [optional]  |
| **profileId** | **string?** | Filter by profile ID. Omit for all profiles. | [optional]  |
| **source** | **string?** | Filter by post origin. \&quot;late\&quot; for posts published via Zernio, \&quot;external\&quot; for posts imported from platforms. | [optional] [default to all] |

### Return type

[**GetContentDecay200Response**](GetContentDecay200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Content decay buckets |  -  |
| **401** | Unauthorized |  -  |
| **403** | Analytics add-on required |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="getdailymetrics"></a>
# **GetDailyMetrics**
> GetDailyMetrics200Response GetDailyMetrics (string? platform = null, string? profileId = null, DateTime? fromDate = null, DateTime? toDate = null, string? source = null)

Get daily aggregated metrics

Returns daily aggregated analytics metrics and a per-platform breakdown. Each day includes post count, platform distribution, and summed metrics (impressions, reach, likes, comments, shares, saves, clicks, views). Defaults to the last 180 days. Requires the Analytics add-on. 

### Example
```csharp
using System.Collections.Generic;
using System.Diagnostics;
using System.Net.Http;
using Late.Api;
using Late.Client;
using Late.Model;

namespace Example
{
    public class GetDailyMetricsExample
    {
        public static void Main()
        {
            Configuration config = new Configuration();
            config.BasePath = "https://zernio.com/api";
            // Configure Bearer token for authorization: bearerAuth
            config.AccessToken = "YOUR_BEARER_TOKEN";

            // create instances of HttpClient, HttpClientHandler to be reused later with different Api classes
            HttpClient httpClient = new HttpClient();
            HttpClientHandler httpClientHandler = new HttpClientHandler();
            var apiInstance = new AnalyticsApi(httpClient, config, httpClientHandler);
            var platform = "platform_example";  // string? | Filter by platform (e.g. \"instagram\", \"tiktok\"). Omit for all platforms. (optional) 
            var profileId = "profileId_example";  // string? | Filter by profile ID. Omit for all profiles. (optional) 
            var fromDate = DateTime.Parse("2013-10-20T19:20:30+01:00");  // DateTime? | Inclusive start date (ISO 8601). Defaults to 180 days ago. (optional) 
            var toDate = DateTime.Parse("2013-10-20T19:20:30+01:00");  // DateTime? | Inclusive end date (ISO 8601). Defaults to now. (optional) 
            var source = "all";  // string? | Filter by post origin. \"late\" for posts published via Zernio, \"external\" for posts imported from platforms. (optional)  (default to all)

            try
            {
                // Get daily aggregated metrics
                GetDailyMetrics200Response result = apiInstance.GetDailyMetrics(platform, profileId, fromDate, toDate, source);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling AnalyticsApi.GetDailyMetrics: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the GetDailyMetricsWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Get daily aggregated metrics
    ApiResponse<GetDailyMetrics200Response> response = apiInstance.GetDailyMetricsWithHttpInfo(platform, profileId, fromDate, toDate, source);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling AnalyticsApi.GetDailyMetricsWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **platform** | **string?** | Filter by platform (e.g. \&quot;instagram\&quot;, \&quot;tiktok\&quot;). Omit for all platforms. | [optional]  |
| **profileId** | **string?** | Filter by profile ID. Omit for all profiles. | [optional]  |
| **fromDate** | **DateTime?** | Inclusive start date (ISO 8601). Defaults to 180 days ago. | [optional]  |
| **toDate** | **DateTime?** | Inclusive end date (ISO 8601). Defaults to now. | [optional]  |
| **source** | **string?** | Filter by post origin. \&quot;late\&quot; for posts published via Zernio, \&quot;external\&quot; for posts imported from platforms. | [optional] [default to all] |

### Return type

[**GetDailyMetrics200Response**](GetDailyMetrics200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Daily metrics and platform breakdown |  -  |
| **401** | Unauthorized |  -  |
| **402** | Analytics add-on required |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="getfollowerstats"></a>
# **GetFollowerStats**
> GetFollowerStats200Response GetFollowerStats (string? accountIds = null, string? profileId = null, DateOnly? fromDate = null, DateOnly? toDate = null, string? granularity = null)

Get follower stats

Returns follower count history and growth metrics for connected social accounts. Requires analytics add-on subscription. Follower counts are refreshed once per day. 

### Example
```csharp
using System.Collections.Generic;
using System.Diagnostics;
using System.Net.Http;
using Late.Api;
using Late.Client;
using Late.Model;

namespace Example
{
    public class GetFollowerStatsExample
    {
        public static void Main()
        {
            Configuration config = new Configuration();
            config.BasePath = "https://zernio.com/api";
            // Configure Bearer token for authorization: bearerAuth
            config.AccessToken = "YOUR_BEARER_TOKEN";

            // create instances of HttpClient, HttpClientHandler to be reused later with different Api classes
            HttpClient httpClient = new HttpClient();
            HttpClientHandler httpClientHandler = new HttpClientHandler();
            var apiInstance = new AnalyticsApi(httpClient, config, httpClientHandler);
            var accountIds = "accountIds_example";  // string? | Comma-separated list of account IDs (optional, defaults to all user's accounts) (optional) 
            var profileId = "profileId_example";  // string? | Filter by profile ID (optional) 
            var fromDate = DateOnly.Parse("2013-10-20");  // DateOnly? | Start date in YYYY-MM-DD format (defaults to 30 days ago) (optional) 
            var toDate = DateOnly.Parse("2013-10-20");  // DateOnly? | End date in YYYY-MM-DD format (defaults to today) (optional) 
            var granularity = "daily";  // string? | Data aggregation level (optional)  (default to daily)

            try
            {
                // Get follower stats
                GetFollowerStats200Response result = apiInstance.GetFollowerStats(accountIds, profileId, fromDate, toDate, granularity);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling AnalyticsApi.GetFollowerStats: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the GetFollowerStatsWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Get follower stats
    ApiResponse<GetFollowerStats200Response> response = apiInstance.GetFollowerStatsWithHttpInfo(accountIds, profileId, fromDate, toDate, granularity);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling AnalyticsApi.GetFollowerStatsWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **accountIds** | **string?** | Comma-separated list of account IDs (optional, defaults to all user&#39;s accounts) | [optional]  |
| **profileId** | **string?** | Filter by profile ID | [optional]  |
| **fromDate** | **DateOnly?** | Start date in YYYY-MM-DD format (defaults to 30 days ago) | [optional]  |
| **toDate** | **DateOnly?** | End date in YYYY-MM-DD format (defaults to today) | [optional]  |
| **granularity** | **string?** | Data aggregation level | [optional] [default to daily] |

### Return type

[**GetFollowerStats200Response**](GetFollowerStats200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Follower stats |  -  |
| **401** | Unauthorized |  -  |
| **403** | Analytics add-on required |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="getinstagramaccountinsights"></a>
# **GetInstagramAccountInsights**
> InstagramAccountInsightsResponse GetInstagramAccountInsights (string accountId, string? metrics = null, DateOnly? since = null, DateOnly? until = null, string? metricType = null, string? breakdown = null)

Get Instagram account-level insights

Returns account-level Instagram insights such as reach, views, accounts engaged, and total interactions. These metrics reflect the entire account's performance across all content surfaces (feed, stories, explore, profile), and are fundamentally different from post-level metrics. Data may be delayed up to 48 hours. Max 90 days, defaults to last 30 days. Requires the Analytics add-on. 

### Example
```csharp
using System.Collections.Generic;
using System.Diagnostics;
using System.Net.Http;
using Late.Api;
using Late.Client;
using Late.Model;

namespace Example
{
    public class GetInstagramAccountInsightsExample
    {
        public static void Main()
        {
            Configuration config = new Configuration();
            config.BasePath = "https://zernio.com/api";
            // Configure Bearer token for authorization: bearerAuth
            config.AccessToken = "YOUR_BEARER_TOKEN";

            // create instances of HttpClient, HttpClientHandler to be reused later with different Api classes
            HttpClient httpClient = new HttpClient();
            HttpClientHandler httpClientHandler = new HttpClientHandler();
            var apiInstance = new AnalyticsApi(httpClient, config, httpClientHandler);
            var accountId = "accountId_example";  // string | The Zernio SocialAccount ID for the Instagram account
            var metrics = "metrics_example";  // string? | Comma-separated list of metrics. Defaults to \"reach,views,accounts_engaged,total_interactions\". Valid metrics: reach, views, accounts_engaged, total_interactions, comments, likes, saves, shares, replies, reposts, follows_and_unfollows, profile_links_taps. Note: only \"reach\" supports metricType=time_series. All other metrics are total_value only.  (optional) 
            var since = DateOnly.Parse("2013-10-20");  // DateOnly? | Start date (YYYY-MM-DD). Defaults to 30 days ago. (optional) 
            var until = DateOnly.Parse("2013-10-20");  // DateOnly? | End date (YYYY-MM-DD). Defaults to today. (optional) 
            var metricType = "time_series";  // string? | \"total_value\" (default) returns aggregated totals and supports breakdowns. \"time_series\" returns daily values but only works with the \"reach\" metric.  (optional)  (default to total_value)
            var breakdown = "breakdown_example";  // string? | Breakdown dimension (only valid with metricType=total_value). Valid values depend on the metric: media_product_type, follow_type, follower_type, contact_button_type.  (optional) 

            try
            {
                // Get Instagram account-level insights
                InstagramAccountInsightsResponse result = apiInstance.GetInstagramAccountInsights(accountId, metrics, since, until, metricType, breakdown);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling AnalyticsApi.GetInstagramAccountInsights: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the GetInstagramAccountInsightsWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Get Instagram account-level insights
    ApiResponse<InstagramAccountInsightsResponse> response = apiInstance.GetInstagramAccountInsightsWithHttpInfo(accountId, metrics, since, until, metricType, breakdown);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling AnalyticsApi.GetInstagramAccountInsightsWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **accountId** | **string** | The Zernio SocialAccount ID for the Instagram account |  |
| **metrics** | **string?** | Comma-separated list of metrics. Defaults to \&quot;reach,views,accounts_engaged,total_interactions\&quot;. Valid metrics: reach, views, accounts_engaged, total_interactions, comments, likes, saves, shares, replies, reposts, follows_and_unfollows, profile_links_taps. Note: only \&quot;reach\&quot; supports metricType&#x3D;time_series. All other metrics are total_value only.  | [optional]  |
| **since** | **DateOnly?** | Start date (YYYY-MM-DD). Defaults to 30 days ago. | [optional]  |
| **until** | **DateOnly?** | End date (YYYY-MM-DD). Defaults to today. | [optional]  |
| **metricType** | **string?** | \&quot;total_value\&quot; (default) returns aggregated totals and supports breakdowns. \&quot;time_series\&quot; returns daily values but only works with the \&quot;reach\&quot; metric.  | [optional] [default to total_value] |
| **breakdown** | **string?** | Breakdown dimension (only valid with metricType&#x3D;total_value). Valid values depend on the metric: media_product_type, follow_type, follower_type, contact_button_type.  | [optional]  |

### Return type

[**InstagramAccountInsightsResponse**](InstagramAccountInsightsResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Account insights data |  -  |
| **400** | Bad request (invalid parameters) |  -  |
| **401** | Unauthorized |  -  |
| **402** | Analytics add-on required |  -  |
| **403** | Access denied to this account |  -  |
| **404** | Account not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="getinstagramdemographics"></a>
# **GetInstagramDemographics**
> InstagramDemographicsResponse GetInstagramDemographics (string accountId, string? metric = null, string? breakdown = null, string? timeframe = null)

Get Instagram audience demographics

Returns audience demographic insights for an Instagram account, broken down by age, city, country, and/or gender. Requires at least 100 followers. Returns top 45 entries per dimension. Data may be delayed up to 48 hours. Requires the Analytics add-on. 

### Example
```csharp
using System.Collections.Generic;
using System.Diagnostics;
using System.Net.Http;
using Late.Api;
using Late.Client;
using Late.Model;

namespace Example
{
    public class GetInstagramDemographicsExample
    {
        public static void Main()
        {
            Configuration config = new Configuration();
            config.BasePath = "https://zernio.com/api";
            // Configure Bearer token for authorization: bearerAuth
            config.AccessToken = "YOUR_BEARER_TOKEN";

            // create instances of HttpClient, HttpClientHandler to be reused later with different Api classes
            HttpClient httpClient = new HttpClient();
            HttpClientHandler httpClientHandler = new HttpClientHandler();
            var apiInstance = new AnalyticsApi(httpClient, config, httpClientHandler);
            var accountId = "accountId_example";  // string | The Zernio SocialAccount ID for the Instagram account
            var metric = "follower_demographics";  // string? | \"follower_demographics\" for follower audience data, or \"engaged_audience_demographics\" for engaged viewers.  (optional)  (default to follower_demographics)
            var breakdown = "breakdown_example";  // string? | Comma-separated list of demographic dimensions: age, city, country, gender. Defaults to all four if omitted.  (optional) 
            var timeframe = "this_week";  // string? | Time period for demographic data. Defaults to \"this_month\".  (optional)  (default to this_month)

            try
            {
                // Get Instagram audience demographics
                InstagramDemographicsResponse result = apiInstance.GetInstagramDemographics(accountId, metric, breakdown, timeframe);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling AnalyticsApi.GetInstagramDemographics: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the GetInstagramDemographicsWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Get Instagram audience demographics
    ApiResponse<InstagramDemographicsResponse> response = apiInstance.GetInstagramDemographicsWithHttpInfo(accountId, metric, breakdown, timeframe);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling AnalyticsApi.GetInstagramDemographicsWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **accountId** | **string** | The Zernio SocialAccount ID for the Instagram account |  |
| **metric** | **string?** | \&quot;follower_demographics\&quot; for follower audience data, or \&quot;engaged_audience_demographics\&quot; for engaged viewers.  | [optional] [default to follower_demographics] |
| **breakdown** | **string?** | Comma-separated list of demographic dimensions: age, city, country, gender. Defaults to all four if omitted.  | [optional]  |
| **timeframe** | **string?** | Time period for demographic data. Defaults to \&quot;this_month\&quot;.  | [optional] [default to this_month] |

### Return type

[**InstagramDemographicsResponse**](InstagramDemographicsResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Demographic insights data |  -  |
| **400** | Bad request (invalid parameters) |  -  |
| **401** | Unauthorized |  -  |
| **402** | Analytics add-on required |  -  |
| **403** | Access denied to this account |  -  |
| **404** | Account not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="getlinkedinaggregateanalytics"></a>
# **GetLinkedInAggregateAnalytics**
> GetLinkedInAggregateAnalytics200Response GetLinkedInAggregateAnalytics (string accountId, string? aggregation = null, DateOnly? startDate = null, DateOnly? endDate = null, string? metrics = null)

Get LinkedIn aggregate stats

Returns aggregate analytics across all posts for a LinkedIn personal account. Org accounts should use /v1/analytics instead. Requires r_member_postAnalytics scope.

### Example
```csharp
using System.Collections.Generic;
using System.Diagnostics;
using System.Net.Http;
using Late.Api;
using Late.Client;
using Late.Model;

namespace Example
{
    public class GetLinkedInAggregateAnalyticsExample
    {
        public static void Main()
        {
            Configuration config = new Configuration();
            config.BasePath = "https://zernio.com/api";
            // Configure Bearer token for authorization: bearerAuth
            config.AccessToken = "YOUR_BEARER_TOKEN";

            // create instances of HttpClient, HttpClientHandler to be reused later with different Api classes
            HttpClient httpClient = new HttpClient();
            HttpClientHandler httpClientHandler = new HttpClientHandler();
            var apiInstance = new AnalyticsApi(httpClient, config, httpClientHandler);
            var accountId = "accountId_example";  // string | The ID of the LinkedIn personal account
            var aggregation = "TOTAL";  // string? | TOTAL (default, lifetime totals) or DAILY (time series). MEMBERS_REACHED not available with DAILY. (optional)  (default to TOTAL)
            var startDate = 2024-01-01;  // DateOnly? | Start date (YYYY-MM-DD). If omitted, returns lifetime analytics. (optional) 
            var endDate = 2024-01-31;  // DateOnly? | End date (YYYY-MM-DD, exclusive). Defaults to today if omitted. (optional) 
            var metrics = IMPRESSION,REACTION,COMMENT;  // string? | Comma-separated metrics: IMPRESSION, MEMBERS_REACHED, REACTION, COMMENT, RESHARE. Omit for all. (optional) 

            try
            {
                // Get LinkedIn aggregate stats
                GetLinkedInAggregateAnalytics200Response result = apiInstance.GetLinkedInAggregateAnalytics(accountId, aggregation, startDate, endDate, metrics);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling AnalyticsApi.GetLinkedInAggregateAnalytics: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the GetLinkedInAggregateAnalyticsWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Get LinkedIn aggregate stats
    ApiResponse<GetLinkedInAggregateAnalytics200Response> response = apiInstance.GetLinkedInAggregateAnalyticsWithHttpInfo(accountId, aggregation, startDate, endDate, metrics);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling AnalyticsApi.GetLinkedInAggregateAnalyticsWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **accountId** | **string** | The ID of the LinkedIn personal account |  |
| **aggregation** | **string?** | TOTAL (default, lifetime totals) or DAILY (time series). MEMBERS_REACHED not available with DAILY. | [optional] [default to TOTAL] |
| **startDate** | **DateOnly?** | Start date (YYYY-MM-DD). If omitted, returns lifetime analytics. | [optional]  |
| **endDate** | **DateOnly?** | End date (YYYY-MM-DD, exclusive). Defaults to today if omitted. | [optional]  |
| **metrics** | **string?** | Comma-separated metrics: IMPRESSION, MEMBERS_REACHED, REACTION, COMMENT, RESHARE. Omit for all. | [optional]  |

### Return type

[**GetLinkedInAggregateAnalytics200Response**](GetLinkedInAggregateAnalytics200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Aggregate analytics data |  -  |
| **400** | Invalid request |  -  |
| **401** | Unauthorized |  -  |
| **402** | Analytics add-on required |  -  |
| **403** | Missing required LinkedIn scope |  -  |
| **404** | Account not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="getlinkedinpostanalytics"></a>
# **GetLinkedInPostAnalytics**
> GetLinkedInPostAnalytics200Response GetLinkedInPostAnalytics (string accountId, string urn)

Get LinkedIn post stats

Returns analytics for a specific LinkedIn post by URN. Works for both personal and organization accounts.

### Example
```csharp
using System.Collections.Generic;
using System.Diagnostics;
using System.Net.Http;
using Late.Api;
using Late.Client;
using Late.Model;

namespace Example
{
    public class GetLinkedInPostAnalyticsExample
    {
        public static void Main()
        {
            Configuration config = new Configuration();
            config.BasePath = "https://zernio.com/api";
            // Configure Bearer token for authorization: bearerAuth
            config.AccessToken = "YOUR_BEARER_TOKEN";

            // create instances of HttpClient, HttpClientHandler to be reused later with different Api classes
            HttpClient httpClient = new HttpClient();
            HttpClientHandler httpClientHandler = new HttpClientHandler();
            var apiInstance = new AnalyticsApi(httpClient, config, httpClientHandler);
            var accountId = "accountId_example";  // string | The ID of the LinkedIn account
            var urn = urn:li:share:7123456789012345678;  // string | The LinkedIn post URN

            try
            {
                // Get LinkedIn post stats
                GetLinkedInPostAnalytics200Response result = apiInstance.GetLinkedInPostAnalytics(accountId, urn);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling AnalyticsApi.GetLinkedInPostAnalytics: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the GetLinkedInPostAnalyticsWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Get LinkedIn post stats
    ApiResponse<GetLinkedInPostAnalytics200Response> response = apiInstance.GetLinkedInPostAnalyticsWithHttpInfo(accountId, urn);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling AnalyticsApi.GetLinkedInPostAnalyticsWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **accountId** | **string** | The ID of the LinkedIn account |  |
| **urn** | **string** | The LinkedIn post URN |  |

### Return type

[**GetLinkedInPostAnalytics200Response**](GetLinkedInPostAnalytics200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Post analytics data |  -  |
| **400** | Invalid request |  -  |
| **401** | Unauthorized |  -  |
| **402** | Analytics add-on required |  -  |
| **403** | Missing required LinkedIn scope |  -  |
| **404** | Account or post not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="getlinkedinpostreactions"></a>
# **GetLinkedInPostReactions**
> GetLinkedInPostReactions200Response GetLinkedInPostReactions (string accountId, string urn, int? limit = null, string? cursor = null)

Get LinkedIn post reactions

Returns individual reactions for a specific LinkedIn post, including reactor profiles (name, headline/job title, profile picture, profile URL, reaction type). Only works for **organization/company page** accounts. LinkedIn restricts reaction data for personal profiles (r_member_social_feed is a closed permission). 

### Example
```csharp
using System.Collections.Generic;
using System.Diagnostics;
using System.Net.Http;
using Late.Api;
using Late.Client;
using Late.Model;

namespace Example
{
    public class GetLinkedInPostReactionsExample
    {
        public static void Main()
        {
            Configuration config = new Configuration();
            config.BasePath = "https://zernio.com/api";
            // Configure Bearer token for authorization: bearerAuth
            config.AccessToken = "YOUR_BEARER_TOKEN";

            // create instances of HttpClient, HttpClientHandler to be reused later with different Api classes
            HttpClient httpClient = new HttpClient();
            HttpClientHandler httpClientHandler = new HttpClientHandler();
            var apiInstance = new AnalyticsApi(httpClient, config, httpClientHandler);
            var accountId = "accountId_example";  // string | The ID of the LinkedIn organization account
            var urn = urn:li:share:7123456789012345678;  // string | The LinkedIn post URN
            var limit = 25;  // int? | Maximum number of reactions to return per page (optional)  (default to 25)
            var cursor = "cursor_example";  // string? | Offset-based pagination start index (optional) 

            try
            {
                // Get LinkedIn post reactions
                GetLinkedInPostReactions200Response result = apiInstance.GetLinkedInPostReactions(accountId, urn, limit, cursor);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling AnalyticsApi.GetLinkedInPostReactions: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the GetLinkedInPostReactionsWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Get LinkedIn post reactions
    ApiResponse<GetLinkedInPostReactions200Response> response = apiInstance.GetLinkedInPostReactionsWithHttpInfo(accountId, urn, limit, cursor);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling AnalyticsApi.GetLinkedInPostReactionsWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **accountId** | **string** | The ID of the LinkedIn organization account |  |
| **urn** | **string** | The LinkedIn post URN |  |
| **limit** | **int?** | Maximum number of reactions to return per page | [optional] [default to 25] |
| **cursor** | **string?** | Offset-based pagination start index | [optional]  |

### Return type

[**GetLinkedInPostReactions200Response**](GetLinkedInPostReactions200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Reactions with reactor profiles |  -  |
| **400** | Invalid request or platform limitation |  -  |
| **401** | Unauthorized |  -  |
| **402** | Analytics add-on required |  -  |
| **403** | Missing required LinkedIn scope |  -  |
| **404** | Account or post not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="getposttimeline"></a>
# **GetPostTimeline**
> GetPostTimeline200Response GetPostTimeline (string postId, DateTime? fromDate = null, DateTime? toDate = null)

Get post analytics timeline

Returns a daily timeline of analytics metrics for a specific post, showing how impressions, likes, and other metrics evolved day-by-day since publishing. Each row represents one day of data per platform. For multi-platform Zernio posts, returns separate rows for each platform. Requires the Analytics add-on. 

### Example
```csharp
using System.Collections.Generic;
using System.Diagnostics;
using System.Net.Http;
using Late.Api;
using Late.Client;
using Late.Model;

namespace Example
{
    public class GetPostTimelineExample
    {
        public static void Main()
        {
            Configuration config = new Configuration();
            config.BasePath = "https://zernio.com/api";
            // Configure Bearer token for authorization: bearerAuth
            config.AccessToken = "YOUR_BEARER_TOKEN";

            // create instances of HttpClient, HttpClientHandler to be reused later with different Api classes
            HttpClient httpClient = new HttpClient();
            HttpClientHandler httpClientHandler = new HttpClientHandler();
            var apiInstance = new AnalyticsApi(httpClient, config, httpClientHandler);
            var postId = "postId_example";  // string | The post to fetch timeline for. Accepts an ExternalPost ID, a platformPostId, or a Zernio Post ID. 
            var fromDate = DateTime.Parse("2013-10-20T19:20:30+01:00");  // DateTime? | Start of date range (ISO 8601). Defaults to 90 days ago. (optional) 
            var toDate = DateTime.Parse("2013-10-20T19:20:30+01:00");  // DateTime? | End of date range (ISO 8601). Defaults to now. (optional) 

            try
            {
                // Get post analytics timeline
                GetPostTimeline200Response result = apiInstance.GetPostTimeline(postId, fromDate, toDate);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling AnalyticsApi.GetPostTimeline: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the GetPostTimelineWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Get post analytics timeline
    ApiResponse<GetPostTimeline200Response> response = apiInstance.GetPostTimelineWithHttpInfo(postId, fromDate, toDate);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling AnalyticsApi.GetPostTimelineWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **postId** | **string** | The post to fetch timeline for. Accepts an ExternalPost ID, a platformPostId, or a Zernio Post ID.  |  |
| **fromDate** | **DateTime?** | Start of date range (ISO 8601). Defaults to 90 days ago. | [optional]  |
| **toDate** | **DateTime?** | End of date range (ISO 8601). Defaults to now. | [optional]  |

### Return type

[**GetPostTimeline200Response**](GetPostTimeline200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Daily analytics timeline |  -  |
| **400** | Missing required postId parameter |  -  |
| **401** | Unauthorized |  -  |
| **402** | Analytics add-on required |  -  |
| **403** | Forbidden (post belongs to another user or API key scope violation) |  -  |
| **404** | Post not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="getpostingfrequency"></a>
# **GetPostingFrequency**
> GetPostingFrequency200Response GetPostingFrequency (string? platform = null, string? profileId = null, string? source = null)

Get posting frequency vs engagement

Returns the correlation between posting frequency (posts per week) and engagement rate, broken down by platform. Helps find the optimal posting cadence for each platform. Each row represents a specific (platform, posts_per_week) combination with the average engagement rate observed across all weeks matching that frequency. Requires the Analytics add-on. 

### Example
```csharp
using System.Collections.Generic;
using System.Diagnostics;
using System.Net.Http;
using Late.Api;
using Late.Client;
using Late.Model;

namespace Example
{
    public class GetPostingFrequencyExample
    {
        public static void Main()
        {
            Configuration config = new Configuration();
            config.BasePath = "https://zernio.com/api";
            // Configure Bearer token for authorization: bearerAuth
            config.AccessToken = "YOUR_BEARER_TOKEN";

            // create instances of HttpClient, HttpClientHandler to be reused later with different Api classes
            HttpClient httpClient = new HttpClient();
            HttpClientHandler httpClientHandler = new HttpClientHandler();
            var apiInstance = new AnalyticsApi(httpClient, config, httpClientHandler);
            var platform = "platform_example";  // string? | Filter by platform (e.g. \"instagram\", \"tiktok\"). Omit for all platforms. (optional) 
            var profileId = "profileId_example";  // string? | Filter by profile ID. Omit for all profiles. (optional) 
            var source = "all";  // string? | Filter by post origin. \"late\" for posts published via Zernio, \"external\" for posts imported from platforms. (optional)  (default to all)

            try
            {
                // Get posting frequency vs engagement
                GetPostingFrequency200Response result = apiInstance.GetPostingFrequency(platform, profileId, source);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling AnalyticsApi.GetPostingFrequency: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the GetPostingFrequencyWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Get posting frequency vs engagement
    ApiResponse<GetPostingFrequency200Response> response = apiInstance.GetPostingFrequencyWithHttpInfo(platform, profileId, source);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling AnalyticsApi.GetPostingFrequencyWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **platform** | **string?** | Filter by platform (e.g. \&quot;instagram\&quot;, \&quot;tiktok\&quot;). Omit for all platforms. | [optional]  |
| **profileId** | **string?** | Filter by profile ID. Omit for all profiles. | [optional]  |
| **source** | **string?** | Filter by post origin. \&quot;late\&quot; for posts published via Zernio, \&quot;external\&quot; for posts imported from platforms. | [optional] [default to all] |

### Return type

[**GetPostingFrequency200Response**](GetPostingFrequency200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Posting frequency data |  -  |
| **401** | Unauthorized |  -  |
| **403** | Analytics add-on required |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="getyoutubedailyviews"></a>
# **GetYouTubeDailyViews**
> YouTubeDailyViewsResponse GetYouTubeDailyViews (string videoId, string accountId, DateOnly? startDate = null, DateOnly? endDate = null)

Get YouTube daily views

Returns daily view counts for a YouTube video including views, watch time, and subscriber changes. Requires yt-analytics.readonly scope (re-authorization may be needed). Data has a 2-3 day delay. Max 90 days, defaults to last 30 days. 

### Example
```csharp
using System.Collections.Generic;
using System.Diagnostics;
using System.Net.Http;
using Late.Api;
using Late.Client;
using Late.Model;

namespace Example
{
    public class GetYouTubeDailyViewsExample
    {
        public static void Main()
        {
            Configuration config = new Configuration();
            config.BasePath = "https://zernio.com/api";
            // Configure Bearer token for authorization: bearerAuth
            config.AccessToken = "YOUR_BEARER_TOKEN";

            // create instances of HttpClient, HttpClientHandler to be reused later with different Api classes
            HttpClient httpClient = new HttpClient();
            HttpClientHandler httpClientHandler = new HttpClientHandler();
            var apiInstance = new AnalyticsApi(httpClient, config, httpClientHandler);
            var videoId = "videoId_example";  // string | The YouTube video ID (e.g., \"dQw4w9WgXcQ\")
            var accountId = "accountId_example";  // string | The Zernio account ID for the YouTube account
            var startDate = DateOnly.Parse("2013-10-20");  // DateOnly? | Start date (YYYY-MM-DD). Defaults to 30 days ago. (optional) 
            var endDate = DateOnly.Parse("2013-10-20");  // DateOnly? | End date (YYYY-MM-DD). Defaults to 3 days ago (YouTube data latency). (optional) 

            try
            {
                // Get YouTube daily views
                YouTubeDailyViewsResponse result = apiInstance.GetYouTubeDailyViews(videoId, accountId, startDate, endDate);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling AnalyticsApi.GetYouTubeDailyViews: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the GetYouTubeDailyViewsWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Get YouTube daily views
    ApiResponse<YouTubeDailyViewsResponse> response = apiInstance.GetYouTubeDailyViewsWithHttpInfo(videoId, accountId, startDate, endDate);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling AnalyticsApi.GetYouTubeDailyViewsWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **videoId** | **string** | The YouTube video ID (e.g., \&quot;dQw4w9WgXcQ\&quot;) |  |
| **accountId** | **string** | The Zernio account ID for the YouTube account |  |
| **startDate** | **DateOnly?** | Start date (YYYY-MM-DD). Defaults to 30 days ago. | [optional]  |
| **endDate** | **DateOnly?** | End date (YYYY-MM-DD). Defaults to 3 days ago (YouTube data latency). | [optional]  |

### Return type

[**YouTubeDailyViewsResponse**](YouTubeDailyViewsResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Daily views breakdown |  -  |
| **400** | Bad request (missing or invalid parameters) |  -  |
| **401** | Unauthorized |  -  |
| **402** | Analytics add-on required |  -  |
| **403** | Access denied to this account |  -  |
| **412** | Missing YouTube Analytics scope |  -  |
| **500** | Internal server error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

