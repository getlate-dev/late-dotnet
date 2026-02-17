# Late.Api.AnalyticsApi

All URIs are relative to *https://getlate.dev/api*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**GetAnalytics**](AnalyticsApi.md#getanalytics) | **GET** /v1/analytics | Get post analytics |
| [**GetFollowerStats**](AnalyticsApi.md#getfollowerstats) | **GET** /v1/accounts/follower-stats | Get follower stats |
| [**GetLinkedInAggregateAnalytics**](AnalyticsApi.md#getlinkedinaggregateanalytics) | **GET** /v1/accounts/{accountId}/linkedin-aggregate-analytics | Get LinkedIn aggregate stats |
| [**GetLinkedInPostAnalytics**](AnalyticsApi.md#getlinkedinpostanalytics) | **GET** /v1/accounts/{accountId}/linkedin-post-analytics | Get LinkedIn post stats |
| [**GetYouTubeDailyViews**](AnalyticsApi.md#getyoutubedailyviews) | **GET** /v1/analytics/youtube/daily-views | Get YouTube daily views |

<a id="getanalytics"></a>
# **GetAnalytics**
> GetAnalytics200Response GetAnalytics (string? postId = null, string? platform = null, string? profileId = null, string? source = null, DateOnly? fromDate = null, DateOnly? toDate = null, int? limit = null, int? page = null, string? sortBy = null, string? order = null)

Get post analytics

Returns analytics for posts. With postId, returns a single post. Without it, returns a paginated list with overview stats. Accepts both Late Post IDs and External Post IDs (auto-resolved). Data is cached and refreshed at most once per hour. For follower stats, use /v1/accounts/follower-stats. 

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
            config.BasePath = "https://getlate.dev/api";
            // Configure Bearer token for authorization: bearerAuth
            config.AccessToken = "YOUR_BEARER_TOKEN";

            // create instances of HttpClient, HttpClientHandler to be reused later with different Api classes
            HttpClient httpClient = new HttpClient();
            HttpClientHandler httpClientHandler = new HttpClientHandler();
            var apiInstance = new AnalyticsApi(httpClient, config, httpClientHandler);
            var postId = "postId_example";  // string? | Returns analytics for a single post. Accepts both Late Post IDs and External Post IDs. Late IDs are auto-resolved to External Post analytics. (optional) 
            var platform = "platform_example";  // string? | Filter by platform (default \"all\") (optional) 
            var profileId = "profileId_example";  // string? | Filter by profile ID (default \"all\") (optional) 
            var source = "all";  // string? | Filter by post source: late (posted via Late API), external (synced from platform), all (default) (optional)  (default to all)
            var fromDate = DateOnly.Parse("2013-10-20");  // DateOnly? | Inclusive lower bound (optional) 
            var toDate = DateOnly.Parse("2013-10-20");  // DateOnly? | Inclusive upper bound (optional) 
            var limit = 50;  // int? | Page size (default 50) (optional)  (default to 50)
            var page = 1;  // int? | Page number (default 1) (optional)  (default to 1)
            var sortBy = "date";  // string? | Sort by date or engagement (optional)  (default to date)
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
| **postId** | **string?** | Returns analytics for a single post. Accepts both Late Post IDs and External Post IDs. Late IDs are auto-resolved to External Post analytics. | [optional]  |
| **platform** | **string?** | Filter by platform (default \&quot;all\&quot;) | [optional]  |
| **profileId** | **string?** | Filter by profile ID (default \&quot;all\&quot;) | [optional]  |
| **source** | **string?** | Filter by post source: late (posted via Late API), external (synced from platform), all (default) | [optional] [default to all] |
| **fromDate** | **DateOnly?** | Inclusive lower bound | [optional]  |
| **toDate** | **DateOnly?** | Inclusive upper bound | [optional]  |
| **limit** | **int?** | Page size (default 50) | [optional] [default to 50] |
| **page** | **int?** | Page number (default 1) | [optional] [default to 1] |
| **sortBy** | **string?** | Sort by date or engagement | [optional] [default to date] |
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
| **401** | Unauthorized |  -  |
| **402** | Analytics add-on required |  -  |
| **404** | Resource not found |  -  |
| **500** | Internal server error |  -  |

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
            config.BasePath = "https://getlate.dev/api";
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
            config.BasePath = "https://getlate.dev/api";
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
            config.BasePath = "https://getlate.dev/api";
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
            config.BasePath = "https://getlate.dev/api";
            // Configure Bearer token for authorization: bearerAuth
            config.AccessToken = "YOUR_BEARER_TOKEN";

            // create instances of HttpClient, HttpClientHandler to be reused later with different Api classes
            HttpClient httpClient = new HttpClient();
            HttpClientHandler httpClientHandler = new HttpClientHandler();
            var apiInstance = new AnalyticsApi(httpClient, config, httpClientHandler);
            var videoId = "videoId_example";  // string | The YouTube video ID (e.g., \"dQw4w9WgXcQ\")
            var accountId = "accountId_example";  // string | The Late account ID for the YouTube account
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
| **accountId** | **string** | The Late account ID for the YouTube account |  |
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

