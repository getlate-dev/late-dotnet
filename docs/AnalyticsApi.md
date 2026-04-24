# Zernio.Api.AnalyticsApi

All URIs are relative to *https://zernio.com/api*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**GetAnalytics**](AnalyticsApi.md#getanalytics) | **GET** /v1/analytics | Get post analytics |
| [**GetBestTimeToPost**](AnalyticsApi.md#getbesttimetopost) | **GET** /v1/analytics/best-time | Get best times to post |
| [**GetContentDecay**](AnalyticsApi.md#getcontentdecay) | **GET** /v1/analytics/content-decay | Get content performance decay |
| [**GetDailyMetrics**](AnalyticsApi.md#getdailymetrics) | **GET** /v1/analytics/daily-metrics | Get daily aggregated metrics |
| [**GetFacebookPageInsights**](AnalyticsApi.md#getfacebookpageinsights) | **GET** /v1/analytics/facebook/page-insights | Get Facebook Page insights |
| [**GetFollowerStats**](AnalyticsApi.md#getfollowerstats) | **GET** /v1/accounts/follower-stats | Get follower stats |
| [**GetGoogleBusinessPerformance**](AnalyticsApi.md#getgooglebusinessperformance) | **GET** /v1/analytics/googlebusiness/performance | Get GBP performance metrics |
| [**GetGoogleBusinessSearchKeywords**](AnalyticsApi.md#getgooglebusinesssearchkeywords) | **GET** /v1/analytics/googlebusiness/search-keywords | Get GBP search keywords |
| [**GetInstagramAccountInsights**](AnalyticsApi.md#getinstagramaccountinsights) | **GET** /v1/analytics/instagram/account-insights | Get Instagram insights |
| [**GetInstagramDemographics**](AnalyticsApi.md#getinstagramdemographics) | **GET** /v1/analytics/instagram/demographics | Get Instagram demographics |
| [**GetInstagramFollowerHistory**](AnalyticsApi.md#getinstagramfollowerhistory) | **GET** /v1/analytics/instagram/follower-history | Get Instagram follower history |
| [**GetLinkedInAggregateAnalytics**](AnalyticsApi.md#getlinkedinaggregateanalytics) | **GET** /v1/accounts/{accountId}/linkedin-aggregate-analytics | Get LinkedIn aggregate stats |
| [**GetLinkedInOrgAggregateAnalytics**](AnalyticsApi.md#getlinkedinorgaggregateanalytics) | **GET** /v1/analytics/linkedin/org-aggregate-analytics | Get LinkedIn organization page aggregate analytics |
| [**GetLinkedInPostAnalytics**](AnalyticsApi.md#getlinkedinpostanalytics) | **GET** /v1/accounts/{accountId}/linkedin-post-analytics | Get LinkedIn post stats |
| [**GetLinkedInPostReactions**](AnalyticsApi.md#getlinkedinpostreactions) | **GET** /v1/accounts/{accountId}/linkedin-post-reactions | Get LinkedIn post reactions |
| [**GetPostTimeline**](AnalyticsApi.md#getposttimeline) | **GET** /v1/analytics/post-timeline | Get post analytics timeline |
| [**GetPostingFrequency**](AnalyticsApi.md#getpostingfrequency) | **GET** /v1/analytics/posting-frequency | Get frequency vs engagement |
| [**GetTikTokAccountInsights**](AnalyticsApi.md#gettiktokaccountinsights) | **GET** /v1/analytics/tiktok/account-insights | Get TikTok account-level insights |
| [**GetYouTubeChannelInsights**](AnalyticsApi.md#getyoutubechannelinsights) | **GET** /v1/analytics/youtube/channel-insights | Get YouTube channel-level insights |
| [**GetYouTubeDailyViews**](AnalyticsApi.md#getyoutubedailyviews) | **GET** /v1/analytics/youtube/daily-views | Get YouTube daily views |
| [**GetYouTubeDemographics**](AnalyticsApi.md#getyoutubedemographics) | **GET** /v1/analytics/youtube/demographics | Get YouTube demographics |

<a id="getanalytics"></a>
# **GetAnalytics**
> GetAnalytics200Response GetAnalytics (string? postId = null, string? platform = null, string? profileId = null, string? accountId = null, string? source = null, DateOnly? fromDate = null, DateOnly? toDate = null, int? limit = null, int? page = null, string? sortBy = null, string? order = null)

Get post analytics

Returns analytics for posts. With postId, returns a single post. Without it, returns a paginated list with overview stats. Accepts both Zernio Post IDs and External Post IDs (auto-resolved). fromDate defaults to 90 days ago if omitted, max range 366 days. Single post lookups may return 202 (sync pending) or 424 (all platforms failed). For follower stats, use /v1/accounts/follower-stats.  LinkedIn personal accounts: Analytics are only available for posts published through Zernio. LinkedIn's API only returns metrics for posts authored by the authenticated user. Organization/company page analytics work for all posts. 

### Example
```csharp
using System.Collections.Generic;
using System.Diagnostics;
using System.Net.Http;
using Zernio.Api;
using Zernio.Client;
using Zernio.Model;

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
            var accountId = "accountId_example";  // string? | Filter by social account ID (optional) 
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
                GetAnalytics200Response result = apiInstance.GetAnalytics(postId, platform, profileId, accountId, source, fromDate, toDate, limit, page, sortBy, order);
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
    ApiResponse<GetAnalytics200Response> response = apiInstance.GetAnalyticsWithHttpInfo(postId, platform, profileId, accountId, source, fromDate, toDate, limit, page, sortBy, order);
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
| **accountId** | **string?** | Filter by social account ID | [optional]  |
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
using Zernio.Api;
using Zernio.Client;
using Zernio.Model;

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
using Zernio.Api;
using Zernio.Client;
using Zernio.Model;

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
> GetDailyMetrics200Response GetDailyMetrics (string? platform = null, string? profileId = null, string? accountId = null, DateTime? fromDate = null, DateTime? toDate = null, string? source = null)

Get daily aggregated metrics

Returns daily aggregated analytics metrics and a per-platform breakdown. Each day includes post count, platform distribution, and summed metrics (impressions, reach, likes, comments, shares, saves, clicks, views). Defaults to the last 180 days. Requires the Analytics add-on. 

### Example
```csharp
using System.Collections.Generic;
using System.Diagnostics;
using System.Net.Http;
using Zernio.Api;
using Zernio.Client;
using Zernio.Model;

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
            var accountId = "accountId_example";  // string? | Filter by social account ID (optional) 
            var fromDate = DateTime.Parse("2013-10-20T19:20:30+01:00");  // DateTime? | Inclusive start date (ISO 8601). Defaults to 180 days ago. (optional) 
            var toDate = DateTime.Parse("2013-10-20T19:20:30+01:00");  // DateTime? | Inclusive end date (ISO 8601). Defaults to now. (optional) 
            var source = "all";  // string? | Filter by post origin. \"late\" for posts published via Zernio, \"external\" for posts imported from platforms. (optional)  (default to all)

            try
            {
                // Get daily aggregated metrics
                GetDailyMetrics200Response result = apiInstance.GetDailyMetrics(platform, profileId, accountId, fromDate, toDate, source);
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
    ApiResponse<GetDailyMetrics200Response> response = apiInstance.GetDailyMetricsWithHttpInfo(platform, profileId, accountId, fromDate, toDate, source);
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
| **accountId** | **string?** | Filter by social account ID | [optional]  |
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

<a id="getfacebookpageinsights"></a>
# **GetFacebookPageInsights**
> InstagramAccountInsightsResponse GetFacebookPageInsights (string accountId, string? metrics = null, DateOnly? since = null, DateOnly? until = null, string? metricType = null)

Get Facebook Page insights

Returns page-level Facebook insights (media views, views, post engagements, video metrics, follower counts). Response shape matches /v1/analytics/instagram/account-insights so the same client handling works across platforms.  Metric names track the current (post-November 2025) Meta Graph API. The legacy page_impressions / page_fans / page_fan_adds / page_fan_removes metrics were deprecated by Meta on November 15, 2025 and are NOT accepted by this endpoint. Use the replacements below. Because Meta did not provide direct adds/removes replacements, Zernio synthesizes followers_gained / followers_lost from the daily follower snapshotter.  Max 89 days, defaults to last 30 days. Requires the Analytics add-on. 

### Example
```csharp
using System.Collections.Generic;
using System.Diagnostics;
using System.Net.Http;
using Zernio.Api;
using Zernio.Client;
using Zernio.Model;

namespace Example
{
    public class GetFacebookPageInsightsExample
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
            var accountId = "accountId_example";  // string | The Zernio SocialAccount ID for the connected Facebook Page.
            var metrics = "metrics_example";  // string? | Comma-separated list of metrics. Defaults to \"page_media_view,page_post_engagements,page_follows,followers_gained,followers_lost\".  Live Meta metrics (current names, post-Nov-2025):   - page_media_view       (replaces deprecated page_impressions)   - page_views_total   - page_post_engagements   - page_video_views   - page_video_view_time   - page_follows          (replaces deprecated page_fans)  Zernio-synthesized from daily follower snapshots (filling the Nov-2025 gap left by the page_fan_adds / page_fan_removes deprecation):   - followers_gained   - followers_lost  (optional) 
            var since = DateOnly.Parse("2013-10-20");  // DateOnly? | Start date (YYYY-MM-DD). Defaults to 30 days ago. (optional) 
            var until = DateOnly.Parse("2013-10-20");  // DateOnly? | End date (YYYY-MM-DD). Defaults to today. (optional) 
            var metricType = "time_series";  // string? | \"total_value\" (default) returns aggregated totals only. \"time_series\" returns daily values in the \"values\" array.  (optional)  (default to total_value)

            try
            {
                // Get Facebook Page insights
                InstagramAccountInsightsResponse result = apiInstance.GetFacebookPageInsights(accountId, metrics, since, until, metricType);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling AnalyticsApi.GetFacebookPageInsights: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the GetFacebookPageInsightsWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Get Facebook Page insights
    ApiResponse<InstagramAccountInsightsResponse> response = apiInstance.GetFacebookPageInsightsWithHttpInfo(accountId, metrics, since, until, metricType);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling AnalyticsApi.GetFacebookPageInsightsWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **accountId** | **string** | The Zernio SocialAccount ID for the connected Facebook Page. |  |
| **metrics** | **string?** | Comma-separated list of metrics. Defaults to \&quot;page_media_view,page_post_engagements,page_follows,followers_gained,followers_lost\&quot;.  Live Meta metrics (current names, post-Nov-2025):   - page_media_view       (replaces deprecated page_impressions)   - page_views_total   - page_post_engagements   - page_video_views   - page_video_view_time   - page_follows          (replaces deprecated page_fans)  Zernio-synthesized from daily follower snapshots (filling the Nov-2025 gap left by the page_fan_adds / page_fan_removes deprecation):   - followers_gained   - followers_lost  | [optional]  |
| **since** | **DateOnly?** | Start date (YYYY-MM-DD). Defaults to 30 days ago. | [optional]  |
| **until** | **DateOnly?** | End date (YYYY-MM-DD). Defaults to today. | [optional]  |
| **metricType** | **string?** | \&quot;total_value\&quot; (default) returns aggregated totals only. \&quot;time_series\&quot; returns daily values in the \&quot;values\&quot; array.  | [optional] [default to total_value] |

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
| **200** | Page insights data |  -  |
| **400** | Bad request. Common cases:   - Requested a deprecated metric (page_impressions, page_fans, page_fan_adds, page_fan_removes) - use current names instead   - Account has no Page selected (metadata.pageAccessToken missing)   - Invalid accountId / metrics / metricType / date range   - Account is not a Facebook account  |  -  |
| **401** | Unauthorized |  -  |
| **402** | Analytics add-on required |  -  |
| **404** | Account not found |  -  |

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
using Zernio.Api;
using Zernio.Client;
using Zernio.Model;

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

<a id="getgooglebusinessperformance"></a>
# **GetGoogleBusinessPerformance**
> GetGoogleBusinessPerformance200Response GetGoogleBusinessPerformance (string accountId, string? metrics = null, DateOnly? startDate = null, DateOnly? endDate = null)

Get GBP performance metrics

Returns daily performance metrics for a Google Business Profile location. Metrics include impressions (Maps/Search, desktop/mobile), website clicks, call clicks, direction requests, conversations, bookings, and food orders. Data may be delayed 2-3 days. Max 18 months of historical data. Requires the Analytics add-on. 

### Example
```csharp
using System.Collections.Generic;
using System.Diagnostics;
using System.Net.Http;
using Zernio.Api;
using Zernio.Client;
using Zernio.Model;

namespace Example
{
    public class GetGoogleBusinessPerformanceExample
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
            var accountId = "accountId_example";  // string | The Zernio SocialAccount ID for the Google Business Profile account.
            var metrics = "metrics_example";  // string? | Comma-separated metric names. Defaults to all available metrics. Valid values: BUSINESS_IMPRESSIONS_DESKTOP_MAPS, BUSINESS_IMPRESSIONS_DESKTOP_SEARCH, BUSINESS_IMPRESSIONS_MOBILE_MAPS, BUSINESS_IMPRESSIONS_MOBILE_SEARCH, BUSINESS_CONVERSATIONS, BUSINESS_DIRECTION_REQUESTS, CALL_CLICKS, WEBSITE_CLICKS, BUSINESS_BOOKINGS, BUSINESS_FOOD_ORDERS, BUSINESS_FOOD_MENU_CLICKS  (optional) 
            var startDate = DateOnly.Parse("2013-10-20");  // DateOnly? | Start date (YYYY-MM-DD). Defaults to 30 days ago. Max 18 months back. (optional) 
            var endDate = DateOnly.Parse("2013-10-20");  // DateOnly? | End date (YYYY-MM-DD). Defaults to today. (optional) 

            try
            {
                // Get GBP performance metrics
                GetGoogleBusinessPerformance200Response result = apiInstance.GetGoogleBusinessPerformance(accountId, metrics, startDate, endDate);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling AnalyticsApi.GetGoogleBusinessPerformance: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the GetGoogleBusinessPerformanceWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Get GBP performance metrics
    ApiResponse<GetGoogleBusinessPerformance200Response> response = apiInstance.GetGoogleBusinessPerformanceWithHttpInfo(accountId, metrics, startDate, endDate);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling AnalyticsApi.GetGoogleBusinessPerformanceWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **accountId** | **string** | The Zernio SocialAccount ID for the Google Business Profile account. |  |
| **metrics** | **string?** | Comma-separated metric names. Defaults to all available metrics. Valid values: BUSINESS_IMPRESSIONS_DESKTOP_MAPS, BUSINESS_IMPRESSIONS_DESKTOP_SEARCH, BUSINESS_IMPRESSIONS_MOBILE_MAPS, BUSINESS_IMPRESSIONS_MOBILE_SEARCH, BUSINESS_CONVERSATIONS, BUSINESS_DIRECTION_REQUESTS, CALL_CLICKS, WEBSITE_CLICKS, BUSINESS_BOOKINGS, BUSINESS_FOOD_ORDERS, BUSINESS_FOOD_MENU_CLICKS  | [optional]  |
| **startDate** | **DateOnly?** | Start date (YYYY-MM-DD). Defaults to 30 days ago. Max 18 months back. | [optional]  |
| **endDate** | **DateOnly?** | End date (YYYY-MM-DD). Defaults to today. | [optional]  |

### Return type

[**GetGoogleBusinessPerformance200Response**](GetGoogleBusinessPerformance200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Performance metrics with daily time series |  -  |
| **400** | Invalid parameters |  -  |
| **401** | Unauthorized |  -  |
| **402** | Analytics add-on required |  -  |
| **403** | Access denied |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="getgooglebusinesssearchkeywords"></a>
# **GetGoogleBusinessSearchKeywords**
> GetGoogleBusinessSearchKeywords200Response GetGoogleBusinessSearchKeywords (string accountId, string? startMonth = null, string? endMonth = null)

Get GBP search keywords

Returns search keywords that triggered impressions for a Google Business Profile location. Data is aggregated monthly. Keywords below a minimum impression threshold set by Google are excluded. Max 18 months of historical data. Requires the Analytics add-on. 

### Example
```csharp
using System.Collections.Generic;
using System.Diagnostics;
using System.Net.Http;
using Zernio.Api;
using Zernio.Client;
using Zernio.Model;

namespace Example
{
    public class GetGoogleBusinessSearchKeywordsExample
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
            var accountId = "accountId_example";  // string | The Zernio SocialAccount ID for the Google Business Profile account.
            var startMonth = "startMonth_example";  // string? | Start month (YYYY-MM). Defaults to 3 months ago. (optional) 
            var endMonth = "endMonth_example";  // string? | End month (YYYY-MM). Defaults to current month. (optional) 

            try
            {
                // Get GBP search keywords
                GetGoogleBusinessSearchKeywords200Response result = apiInstance.GetGoogleBusinessSearchKeywords(accountId, startMonth, endMonth);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling AnalyticsApi.GetGoogleBusinessSearchKeywords: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the GetGoogleBusinessSearchKeywordsWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Get GBP search keywords
    ApiResponse<GetGoogleBusinessSearchKeywords200Response> response = apiInstance.GetGoogleBusinessSearchKeywordsWithHttpInfo(accountId, startMonth, endMonth);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling AnalyticsApi.GetGoogleBusinessSearchKeywordsWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **accountId** | **string** | The Zernio SocialAccount ID for the Google Business Profile account. |  |
| **startMonth** | **string?** | Start month (YYYY-MM). Defaults to 3 months ago. | [optional]  |
| **endMonth** | **string?** | End month (YYYY-MM). Defaults to current month. | [optional]  |

### Return type

[**GetGoogleBusinessSearchKeywords200Response**](GetGoogleBusinessSearchKeywords200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Search keywords with impression counts |  -  |
| **400** | Invalid parameters |  -  |
| **401** | Unauthorized |  -  |
| **402** | Analytics add-on required |  -  |
| **403** | Access denied |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="getinstagramaccountinsights"></a>
# **GetInstagramAccountInsights**
> InstagramAccountInsightsResponse GetInstagramAccountInsights (string accountId, string? metrics = null, DateOnly? since = null, DateOnly? until = null, string? metricType = null, string? breakdown = null)

Get Instagram insights

Returns account-level Instagram insights such as reach, views, accounts engaged, and total interactions. These metrics reflect the entire account's performance across all content surfaces (feed, stories, explore, profile), and are fundamentally different from post-level metrics. Data may be delayed up to 48 hours. Max 90 days, defaults to last 30 days. Requires the Analytics add-on. 

### Example
```csharp
using System.Collections.Generic;
using System.Diagnostics;
using System.Net.Http;
using Zernio.Api;
using Zernio.Client;
using Zernio.Model;

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
            var metrics = "metrics_example";  // string? | Comma-separated list of metrics. Defaults to \"reach,views,accounts_engaged,total_interactions\". Valid metrics: reach, views, accounts_engaged, total_interactions, comments, likes, saves, shares, replies, reposts, follows_and_unfollows, profile_links_taps. Note: only \"reach\" supports metricType=time_series. All other metrics (including follows_and_unfollows) are total_value only. This is an Instagram Graph API limitation, not a Zernio limitation - the IG API does not return time-series data for these metrics. For a daily running follower count, use /v1/analytics/instagram/follower-history instead.  (optional) 
            var since = DateOnly.Parse("2013-10-20");  // DateOnly? | Start date (YYYY-MM-DD). Defaults to 30 days ago. (optional) 
            var until = DateOnly.Parse("2013-10-20");  // DateOnly? | End date (YYYY-MM-DD). Defaults to today. (optional) 
            var metricType = "time_series";  // string? | \"total_value\" (default) returns aggregated totals and supports breakdowns. \"time_series\" returns daily values but only works with the \"reach\" metric.  (optional)  (default to total_value)
            var breakdown = "breakdown_example";  // string? | Breakdown dimension (only valid with metricType=total_value). Valid values depend on the metric: media_product_type, follow_type, follower_type, contact_button_type.  (optional) 

            try
            {
                // Get Instagram insights
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
    // Get Instagram insights
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
| **metrics** | **string?** | Comma-separated list of metrics. Defaults to \&quot;reach,views,accounts_engaged,total_interactions\&quot;. Valid metrics: reach, views, accounts_engaged, total_interactions, comments, likes, saves, shares, replies, reposts, follows_and_unfollows, profile_links_taps. Note: only \&quot;reach\&quot; supports metricType&#x3D;time_series. All other metrics (including follows_and_unfollows) are total_value only. This is an Instagram Graph API limitation, not a Zernio limitation - the IG API does not return time-series data for these metrics. For a daily running follower count, use /v1/analytics/instagram/follower-history instead.  | [optional]  |
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

Get Instagram demographics

Returns audience demographic insights for an Instagram account, broken down by age, city, country, and/or gender. Requires at least 100 followers. Returns top 45 entries per dimension. Data may be delayed up to 48 hours. Requires the Analytics add-on. 

### Example
```csharp
using System.Collections.Generic;
using System.Diagnostics;
using System.Net.Http;
using Zernio.Api;
using Zernio.Client;
using Zernio.Model;

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
                // Get Instagram demographics
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
    // Get Instagram demographics
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

<a id="getinstagramfollowerhistory"></a>
# **GetInstagramFollowerHistory**
> InstagramAccountInsightsResponse GetInstagramFollowerHistory (string accountId, string? metrics = null, DateOnly? since = null, DateOnly? until = null, string? metricType = null)

Get Instagram follower history

Returns a daily running Instagram follower count time series, served from Zernio's cross-platform daily snapshotter. Exists because Meta removed follower_count from the /insights endpoint in Graph API v22+ and never exposed a historical daily series via any public API.  Response envelope matches /v1/analytics/instagram/account-insights so the same client handling works. Max 89 days, defaults to last 30 days. Requires the Analytics add-on. 

### Example
```csharp
using System.Collections.Generic;
using System.Diagnostics;
using System.Net.Http;
using Zernio.Api;
using Zernio.Client;
using Zernio.Model;

namespace Example
{
    public class GetInstagramFollowerHistoryExample
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
            var accountId = "accountId_example";  // string | The Zernio SocialAccount ID for the Instagram account.
            var metrics = "metrics_example";  // string? | Comma-separated list. Defaults to \"follower_count,followers_gained,followers_lost\".   - follower_count   : per-day raw follower count   - followers_gained : sum of positive daily deltas   - followers_lost   : sum of absolute negative daily deltas  (optional) 
            var since = DateOnly.Parse("2013-10-20");  // DateOnly? | Start date (YYYY-MM-DD). Defaults to 30 days ago. (optional) 
            var until = DateOnly.Parse("2013-10-20");  // DateOnly? | End date (YYYY-MM-DD). Defaults to today. (optional) 
            var metricType = "time_series";  // string? | \"total_value\" returns aggregated totals (latest for follower_count, sum for gained/lost). \"time_series\" returns per-day values in the \"values\" array.  (optional)  (default to total_value)

            try
            {
                // Get Instagram follower history
                InstagramAccountInsightsResponse result = apiInstance.GetInstagramFollowerHistory(accountId, metrics, since, until, metricType);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling AnalyticsApi.GetInstagramFollowerHistory: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the GetInstagramFollowerHistoryWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Get Instagram follower history
    ApiResponse<InstagramAccountInsightsResponse> response = apiInstance.GetInstagramFollowerHistoryWithHttpInfo(accountId, metrics, since, until, metricType);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling AnalyticsApi.GetInstagramFollowerHistoryWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **accountId** | **string** | The Zernio SocialAccount ID for the Instagram account. |  |
| **metrics** | **string?** | Comma-separated list. Defaults to \&quot;follower_count,followers_gained,followers_lost\&quot;.   - follower_count   : per-day raw follower count   - followers_gained : sum of positive daily deltas   - followers_lost   : sum of absolute negative daily deltas  | [optional]  |
| **since** | **DateOnly?** | Start date (YYYY-MM-DD). Defaults to 30 days ago. | [optional]  |
| **until** | **DateOnly?** | End date (YYYY-MM-DD). Defaults to today. | [optional]  |
| **metricType** | **string?** | \&quot;total_value\&quot; returns aggregated totals (latest for follower_count, sum for gained/lost). \&quot;time_series\&quot; returns per-day values in the \&quot;values\&quot; array.  | [optional] [default to total_value] |

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
| **200** | Follower history data |  -  |
| **400** | Bad request (invalid accountId / metrics / date range, or account is not an Instagram account) |  -  |
| **401** | Unauthorized |  -  |
| **402** | Analytics add-on required |  -  |
| **404** | Account not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="getlinkedinaggregateanalytics"></a>
# **GetLinkedInAggregateAnalytics**
> GetLinkedInAggregateAnalytics200Response GetLinkedInAggregateAnalytics (string accountId, string? aggregation = null, DateOnly? startDate = null, DateOnly? endDate = null, string? metrics = null)

Get LinkedIn aggregate stats

Returns aggregate analytics across all posts for a LinkedIn personal account. Only includes posts published through Zernio (LinkedIn API limitation). Org accounts should use /v1/analytics instead. Requires r_member_postAnalytics scope. Saves (POST_SAVE) and sends (POST_SEND) are available for personal accounts; organization pages always return 0 for these two metrics because LinkedIn does not expose them on the organization analytics endpoint.

### Example
```csharp
using System.Collections.Generic;
using System.Diagnostics;
using System.Net.Http;
using Zernio.Api;
using Zernio.Client;
using Zernio.Model;

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
            var metrics = IMPRESSION,REACTION,COMMENT,POST_SAVE,POST_SEND;  // string? | Comma-separated metrics: IMPRESSION, MEMBERS_REACHED, REACTION, COMMENT, RESHARE, POST_SAVE, POST_SEND. Omit for all. (optional) 

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
| **metrics** | **string?** | Comma-separated metrics: IMPRESSION, MEMBERS_REACHED, REACTION, COMMENT, RESHARE, POST_SAVE, POST_SEND. Omit for all. | [optional]  |

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

<a id="getlinkedinorgaggregateanalytics"></a>
# **GetLinkedInOrgAggregateAnalytics**
> InstagramAccountInsightsResponse GetLinkedInOrgAggregateAnalytics (string accountId, string? metrics = null, DateOnly? since = null, DateOnly? until = null, string? metricType = null)

Get LinkedIn organization page aggregate analytics

Returns aggregate analytics for a LinkedIn organization page. Parallel to /v1/accounts/{id}/linkedin-aggregate-analytics (which handles personal accounts only). Backed by LinkedIn's organizationalEntityShareStatistics, organizationalEntityFollowerStatistics, and organizationPageStatistics endpoints.  Response shape matches /v1/analytics/instagram/account-insights. Max 89 days, defaults to last 30 days. Requires the Analytics add-on.  Scope requirements: r_organization_social, r_organization_followers, and r_organization_admin must all be present on the account. Accounts connected before these scopes were included in the OAuth flow will return 412 with a reauth hint.  Enforced by this endpoint:   - Page-view metrics accept only metricType=total_value (LinkedIn omits per-day     segmentation even when the API is called with DAY granularity, so a time-series     response would be meaningless).   - Date range capped at 89 days.  LinkedIn-side platform limits (not re-enforced here, but worth knowing for larger ranges in a future release):   - Follower stats: rolling 12-month window, end must be no later than 2 days ago.   - Share stats: rolling 12-month window. 

### Example
```csharp
using System.Collections.Generic;
using System.Diagnostics;
using System.Net.Http;
using Zernio.Api;
using Zernio.Client;
using Zernio.Model;

namespace Example
{
    public class GetLinkedInOrgAggregateAnalyticsExample
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
            var accountId = "accountId_example";  // string | The Zernio SocialAccount ID for the LinkedIn organization account.
            var metrics = "metrics_example";  // string? | Comma-separated list. Defaults to \"impressions,clicks,engagement_rate,organic_followers_gained,followers_gained,followers_lost\".  Share statistics (support both total_value and time_series):   - impressions   - unique_impressions   - clicks   - likes   - comments   - shares   - engagement_rate       (0..1, LinkedIn-computed)  Follower-gain statistics (support total_value and time_series):   - organic_followers_gained   (per-day organic gains for time_series; sum of organic gains over the range for total_value)   - paid_followers_gained      (per-day paid gains for time_series; sum of paid gains over the range for total_value)  Page-view statistics (total_value ONLY - LinkedIn platform limit):   - page_views_total   - page_views_overview   - page_views_careers   - page_views_jobs   - page_views_life  Zernio-synthesized from daily follower snapshots:   - followers_gained   - followers_lost  (optional) 
            var since = DateOnly.Parse("2013-10-20");  // DateOnly? | Start date (YYYY-MM-DD). Defaults to 30 days ago. (optional) 
            var until = DateOnly.Parse("2013-10-20");  // DateOnly? | End date (YYYY-MM-DD). Defaults to today. (optional) 
            var metricType = "time_series";  // string? |  (optional)  (default to total_value)

            try
            {
                // Get LinkedIn organization page aggregate analytics
                InstagramAccountInsightsResponse result = apiInstance.GetLinkedInOrgAggregateAnalytics(accountId, metrics, since, until, metricType);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling AnalyticsApi.GetLinkedInOrgAggregateAnalytics: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the GetLinkedInOrgAggregateAnalyticsWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Get LinkedIn organization page aggregate analytics
    ApiResponse<InstagramAccountInsightsResponse> response = apiInstance.GetLinkedInOrgAggregateAnalyticsWithHttpInfo(accountId, metrics, since, until, metricType);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling AnalyticsApi.GetLinkedInOrgAggregateAnalyticsWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **accountId** | **string** | The Zernio SocialAccount ID for the LinkedIn organization account. |  |
| **metrics** | **string?** | Comma-separated list. Defaults to \&quot;impressions,clicks,engagement_rate,organic_followers_gained,followers_gained,followers_lost\&quot;.  Share statistics (support both total_value and time_series):   - impressions   - unique_impressions   - clicks   - likes   - comments   - shares   - engagement_rate       (0..1, LinkedIn-computed)  Follower-gain statistics (support total_value and time_series):   - organic_followers_gained   (per-day organic gains for time_series; sum of organic gains over the range for total_value)   - paid_followers_gained      (per-day paid gains for time_series; sum of paid gains over the range for total_value)  Page-view statistics (total_value ONLY - LinkedIn platform limit):   - page_views_total   - page_views_overview   - page_views_careers   - page_views_jobs   - page_views_life  Zernio-synthesized from daily follower snapshots:   - followers_gained   - followers_lost  | [optional]  |
| **since** | **DateOnly?** | Start date (YYYY-MM-DD). Defaults to 30 days ago. | [optional]  |
| **until** | **DateOnly?** | End date (YYYY-MM-DD). Defaults to today. | [optional]  |
| **metricType** | **string?** |  | [optional] [default to total_value] |

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
| **200** | Organization analytics data |  -  |
| **400** | Bad request. Common cases:   - Account is a personal LinkedIn account, not organization (code personal_account_not_supported, use /v1/accounts/{id}/linkedin-aggregate-analytics instead)   - Invalid metric name, metricType, or date range  |  -  |
| **401** | Unauthorized |  -  |
| **402** | Analytics add-on required |  -  |
| **403** | Platform error. The authenticated member lacks the required ADMINISTRATOR role on the organization. LinkedIn enforces admin-only access for all three org statistics endpoints. The error envelope is type platform_error, and the raw LinkedIn error is echoed in the platformError field.  |  -  |
| **404** | Account not found |  -  |
| **412** | Missing LinkedIn organization analytics scopes (r_organization_social + r_organization_followers + r_organization_admin) |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="getlinkedinpostanalytics"></a>
# **GetLinkedInPostAnalytics**
> GetLinkedInPostAnalytics200Response GetLinkedInPostAnalytics (string accountId, string urn)

Get LinkedIn post stats

Returns analytics for a specific LinkedIn post by URN. Works for both personal and organization accounts. Saves and sends are only populated for personal accounts (LinkedIn does not expose these metrics on the organization analytics endpoint).

### Example
```csharp
using System.Collections.Generic;
using System.Diagnostics;
using System.Net.Http;
using Zernio.Api;
using Zernio.Client;
using Zernio.Model;

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

Returns individual reactions for a specific LinkedIn post, including reactor profiles (name, headline/job title, profile picture, profile URL, reaction type). Only works for organization/company page accounts. LinkedIn restricts reaction data for personal profiles (r_member_social_feed is a closed permission). 

### Example
```csharp
using System.Collections.Generic;
using System.Diagnostics;
using System.Net.Http;
using Zernio.Api;
using Zernio.Client;
using Zernio.Model;

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
using Zernio.Api;
using Zernio.Client;
using Zernio.Model;

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

Get frequency vs engagement

Returns the correlation between posting frequency (posts per week) and engagement rate, broken down by platform. Helps find the optimal posting cadence for each platform. Each row represents a specific (platform, posts_per_week) combination with the average engagement rate observed across all weeks matching that frequency. Requires the Analytics add-on. 

### Example
```csharp
using System.Collections.Generic;
using System.Diagnostics;
using System.Net.Http;
using Zernio.Api;
using Zernio.Client;
using Zernio.Model;

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
                // Get frequency vs engagement
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
    // Get frequency vs engagement
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

<a id="gettiktokaccountinsights"></a>
# **GetTikTokAccountInsights**
> InstagramAccountInsightsResponse GetTikTokAccountInsights (string accountId, string? metrics = null, DateOnly? since = null, DateOnly? until = null, string? metricType = null)

Get TikTok account-level insights

Returns account-level TikTok insights from /v2/user/info/ (live) plus historical time series joined from Zernio's daily snapshotter (AccountStats).  Response shape matches /v1/analytics/instagram/account-insights. Max 89 days, defaults to last 30 days. Requires the Analytics add-on and the user.info.stats scope on the account (412 if missing).  Scope intentionally narrow. TikTok's public API exposes only the four counter metrics below. The deep metrics that live in TikTok Studio are NOT available on any public TikTok API, even for Business accounts:   - profile_views   - account-level impressions / reach   - follower inflow / outflow breakdown   - video watch time, average watch time, full-watched rate   - impression_sources (FYP / Following / Hashtag / Search / Personal profile)  TikTok's Research API doesn't expose those fields either, and is restricted to non-commercial academic use per TikTok's eligibility policy. There is no public API workaround. Post-level metrics (views, likes, comments, shares per video) are available via /v1/analytics?postId=... from TikTok's /v2/video/query/. 

### Example
```csharp
using System.Collections.Generic;
using System.Diagnostics;
using System.Net.Http;
using Zernio.Api;
using Zernio.Client;
using Zernio.Model;

namespace Example
{
    public class GetTikTokAccountInsightsExample
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
            var accountId = "accountId_example";  // string | The Zernio SocialAccount ID for the TikTok account.
            var metrics = "metrics_example";  // string? | Comma-separated list. Defaults to \"follower_count,likes_count,video_count,followers_gained,followers_lost\".  Live from /v2/user/info/ (requires user.info.stats scope):   - follower_count  (cumulative; time series joined from AccountStats)   - following_count (cumulative; time series joined from AccountStats.metadata)   - likes_count     (cumulative; time series joined from AccountStats.metadata)   - video_count     (cumulative; time series joined from AccountStats.metadata)  Zernio-synthesized:   - followers_gained  (sum of positive daily follower deltas)   - followers_lost    (sum of absolute negative daily deltas)  (optional) 
            var since = DateOnly.Parse("2013-10-20");  // DateOnly? | Start date (YYYY-MM-DD). Defaults to 30 days ago. (optional) 
            var until = DateOnly.Parse("2013-10-20");  // DateOnly? | End date (YYYY-MM-DD). Defaults to today. (optional) 
            var metricType = "time_series";  // string? | \"total_value\" returns the latest cumulative counter value. \"time_series\" returns daily values joined from AccountStats snapshots.  (optional)  (default to total_value)

            try
            {
                // Get TikTok account-level insights
                InstagramAccountInsightsResponse result = apiInstance.GetTikTokAccountInsights(accountId, metrics, since, until, metricType);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling AnalyticsApi.GetTikTokAccountInsights: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the GetTikTokAccountInsightsWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Get TikTok account-level insights
    ApiResponse<InstagramAccountInsightsResponse> response = apiInstance.GetTikTokAccountInsightsWithHttpInfo(accountId, metrics, since, until, metricType);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling AnalyticsApi.GetTikTokAccountInsightsWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **accountId** | **string** | The Zernio SocialAccount ID for the TikTok account. |  |
| **metrics** | **string?** | Comma-separated list. Defaults to \&quot;follower_count,likes_count,video_count,followers_gained,followers_lost\&quot;.  Live from /v2/user/info/ (requires user.info.stats scope):   - follower_count  (cumulative; time series joined from AccountStats)   - following_count (cumulative; time series joined from AccountStats.metadata)   - likes_count     (cumulative; time series joined from AccountStats.metadata)   - video_count     (cumulative; time series joined from AccountStats.metadata)  Zernio-synthesized:   - followers_gained  (sum of positive daily follower deltas)   - followers_lost    (sum of absolute negative daily deltas)  | [optional]  |
| **since** | **DateOnly?** | Start date (YYYY-MM-DD). Defaults to 30 days ago. | [optional]  |
| **until** | **DateOnly?** | End date (YYYY-MM-DD). Defaults to today. | [optional]  |
| **metricType** | **string?** | \&quot;total_value\&quot; returns the latest cumulative counter value. \&quot;time_series\&quot; returns daily values joined from AccountStats snapshots.  | [optional] [default to total_value] |

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
| **400** | Bad request (invalid accountId / metrics / metricType / date range, or account is not a TikTok account) |  -  |
| **401** | Unauthorized |  -  |
| **402** | Analytics add-on required |  -  |
| **404** | Account not found |  -  |
| **412** | Missing user.info.stats scope |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="getyoutubechannelinsights"></a>
# **GetYouTubeChannelInsights**
> InstagramAccountInsightsResponse GetYouTubeChannelInsights (string accountId, string? metrics = null, DateOnly? since = null, DateOnly? until = null, string? metricType = null)

Get YouTube channel-level insights

Returns channel-scoped aggregate metrics from YouTube Analytics API v2. Saves you from looping /v1/analytics/youtube/daily-views over every video when you only need channel totals.  Response shape matches /v1/analytics/instagram/account-insights so the same client handling works. Requires yt-analytics.readonly scope (412 with reauthorizeUrl if missing). Data has a 2-3 day delay (endDate is clamped accordingly). Max 89 days, defaults to last 30 days. Requires the Analytics add-on.  NOT exposed: impressions (Studio thumbnail impressions) and impressionsClickThroughRate. YouTube Analytics API v2 does not expose these for any principal type, not channel owners, not Partner Program channels, not content owners with CMS access. The only way to get them is Studio CSV export. This is a Google-side limitation. 

### Example
```csharp
using System.Collections.Generic;
using System.Diagnostics;
using System.Net.Http;
using Zernio.Api;
using Zernio.Client;
using Zernio.Model;

namespace Example
{
    public class GetYouTubeChannelInsightsExample
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
            var accountId = "accountId_example";  // string | The Zernio SocialAccount ID for the YouTube account.
            var metrics = "metrics_example";  // string? | Comma-separated list. Defaults to \"views,estimatedMinutesWatched,subscribersGained,subscribersLost\".  Live YouTube Analytics v2 metrics:   - views   - estimatedMinutesWatched   - averageViewDuration          (ratio - weighted mean computed across days)   - subscribersGained   - subscribersLost  Zernio-synthesized from daily follower snapshots (cross-platform parity):   - followers_gained   - followers_lost  (optional) 
            var since = DateOnly.Parse("2013-10-20");  // DateOnly? | Start date (YYYY-MM-DD). Defaults to 30 days ago. (optional) 
            var until = DateOnly.Parse("2013-10-20");  // DateOnly? | End date (YYYY-MM-DD). Defaults to today. YouTube Analytics has a 2-3 day delay, so the fetch is internally clamped to 3 days ago; any requested range extending beyond that returns zero values for the tail days. The response's dateRange.until field reflects your requested value.  (optional) 
            var metricType = "time_series";  // string? | \"total_value\" (default) returns aggregated totals. \"time_series\" returns per-day values in the \"values\" array.  (optional)  (default to total_value)

            try
            {
                // Get YouTube channel-level insights
                InstagramAccountInsightsResponse result = apiInstance.GetYouTubeChannelInsights(accountId, metrics, since, until, metricType);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling AnalyticsApi.GetYouTubeChannelInsights: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the GetYouTubeChannelInsightsWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Get YouTube channel-level insights
    ApiResponse<InstagramAccountInsightsResponse> response = apiInstance.GetYouTubeChannelInsightsWithHttpInfo(accountId, metrics, since, until, metricType);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling AnalyticsApi.GetYouTubeChannelInsightsWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **accountId** | **string** | The Zernio SocialAccount ID for the YouTube account. |  |
| **metrics** | **string?** | Comma-separated list. Defaults to \&quot;views,estimatedMinutesWatched,subscribersGained,subscribersLost\&quot;.  Live YouTube Analytics v2 metrics:   - views   - estimatedMinutesWatched   - averageViewDuration          (ratio - weighted mean computed across days)   - subscribersGained   - subscribersLost  Zernio-synthesized from daily follower snapshots (cross-platform parity):   - followers_gained   - followers_lost  | [optional]  |
| **since** | **DateOnly?** | Start date (YYYY-MM-DD). Defaults to 30 days ago. | [optional]  |
| **until** | **DateOnly?** | End date (YYYY-MM-DD). Defaults to today. YouTube Analytics has a 2-3 day delay, so the fetch is internally clamped to 3 days ago; any requested range extending beyond that returns zero values for the tail days. The response&#39;s dateRange.until field reflects your requested value.  | [optional]  |
| **metricType** | **string?** | \&quot;total_value\&quot; (default) returns aggregated totals. \&quot;time_series\&quot; returns per-day values in the \&quot;values\&quot; array.  | [optional] [default to total_value] |

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
| **200** | Channel insights data |  -  |
| **400** | Bad request (invalid accountId / metrics / metricType / date range, or account is not a YouTube account) |  -  |
| **401** | Unauthorized |  -  |
| **402** | Analytics add-on required |  -  |
| **404** | Account not found |  -  |
| **412** | Missing YouTube Analytics scope |  -  |

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
using Zernio.Api;
using Zernio.Client;
using Zernio.Model;

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

<a id="getyoutubedemographics"></a>
# **GetYouTubeDemographics**
> YouTubeDemographicsResponse GetYouTubeDemographics (string accountId, string? breakdown = null, DateOnly? startDate = null, DateOnly? endDate = null)

Get YouTube demographics

Returns audience demographic insights for a YouTube channel, broken down by age, gender, and/or country. Age and gender values are viewer percentages (0-100). Country values are view counts. Data is based on signed-in viewers only, with a 2-3 day delay. Requires the Analytics add-on. 

### Example
```csharp
using System.Collections.Generic;
using System.Diagnostics;
using System.Net.Http;
using Zernio.Api;
using Zernio.Client;
using Zernio.Model;

namespace Example
{
    public class GetYouTubeDemographicsExample
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
            var accountId = "accountId_example";  // string | The Zernio SocialAccount ID for the YouTube account
            var breakdown = "breakdown_example";  // string? | Comma-separated list of demographic dimensions: age, gender, country. Defaults to all three if omitted.  (optional) 
            var startDate = DateOnly.Parse("2013-10-20");  // DateOnly? | Start date in YYYY-MM-DD format. Defaults to 90 days ago.  (optional) 
            var endDate = DateOnly.Parse("2013-10-20");  // DateOnly? | End date in YYYY-MM-DD format. Defaults to 3 days ago (YouTube data latency).  (optional) 

            try
            {
                // Get YouTube demographics
                YouTubeDemographicsResponse result = apiInstance.GetYouTubeDemographics(accountId, breakdown, startDate, endDate);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling AnalyticsApi.GetYouTubeDemographics: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the GetYouTubeDemographicsWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Get YouTube demographics
    ApiResponse<YouTubeDemographicsResponse> response = apiInstance.GetYouTubeDemographicsWithHttpInfo(accountId, breakdown, startDate, endDate);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling AnalyticsApi.GetYouTubeDemographicsWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **accountId** | **string** | The Zernio SocialAccount ID for the YouTube account |  |
| **breakdown** | **string?** | Comma-separated list of demographic dimensions: age, gender, country. Defaults to all three if omitted.  | [optional]  |
| **startDate** | **DateOnly?** | Start date in YYYY-MM-DD format. Defaults to 90 days ago.  | [optional]  |
| **endDate** | **DateOnly?** | End date in YYYY-MM-DD format. Defaults to 3 days ago (YouTube data latency).  | [optional]  |

### Return type

[**YouTubeDemographicsResponse**](YouTubeDemographicsResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Demographic insights data |  -  |
| **400** | Bad request (invalid parameters or not a YouTube account) |  -  |
| **401** | Unauthorized |  -  |
| **402** | Analytics add-on required |  -  |
| **403** | Access denied to this account |  -  |
| **404** | Account not found |  -  |
| **412** | YouTube Analytics scope not granted |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

