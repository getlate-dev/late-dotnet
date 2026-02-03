# Late.Api.AnalyticsApi

All URIs are relative to *https://getlate.dev/api*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**GetAnalytics**](AnalyticsApi.md#getanalytics) | **GET** /v1/analytics | Unified analytics for posts |
| [**GetFollowerStats**](AnalyticsApi.md#getfollowerstats) | **GET** /v1/accounts/follower-stats | Get follower stats and growth metrics |
| [**GetLinkedInAggregateAnalytics**](AnalyticsApi.md#getlinkedinaggregateanalytics) | **GET** /v1/accounts/{accountId}/linkedin-aggregate-analytics | Get aggregate analytics for a LinkedIn personal account |
| [**GetLinkedInPostAnalytics**](AnalyticsApi.md#getlinkedinpostanalytics) | **GET** /v1/accounts/{accountId}/linkedin-post-analytics | Get analytics for a specific LinkedIn post by URN |
| [**GetYouTubeDailyViews**](AnalyticsApi.md#getyoutubedailyviews) | **GET** /v1/analytics/youtube/daily-views | YouTube daily views breakdown |

<a id="getanalytics"></a>
# **GetAnalytics**
> GetAnalytics200Response GetAnalytics (string? postId = null, string? platform = null, string? profileId = null, string? source = null, DateOnly? fromDate = null, DateOnly? toDate = null, int? limit = null, int? page = null, string? sortBy = null, string? order = null)

Unified analytics for posts

Returns analytics for posts. If postId is provided, returns analytics for a single post. Otherwise returns a paginated list of posts with overview stats.  **Important: Understanding Post IDs**  This endpoint uses two types of posts: - **Late Posts** - Posts scheduled/created via the Late API (e.g., via `POST /v1/posts`) - **External Posts** - Posts synced from social platforms for analytics tracking  When you schedule a post via Late and it gets published, **both** records exist: 1. The original Late Post (returned when you created the post) 2. An External Post (created when we sync analytics from the platform)  **List endpoint behavior:** - Returns External Post IDs (`_id` field) - Use the `isExternal` field to identify post origin:   - `isExternal: true` - Synced from platform (may have been originally scheduled via Late)   - `isExternal: false` - Late-scheduled post (shown when querying by Late post ID)  **Single post behavior (`postId` parameter):** - Accepts **both** Late Post IDs and External Post IDs - If you pass a Late Post ID, the API automatically resolves it to the corresponding External Post analytics - Both return the same analytics data for the same underlying social media post  **Correlating posts:** Use `latePostId` to link analytics entries back to the original post created via `POST /v1/posts`. This field contains the Late Post ID when the external post originated from Late. Alternatively, use `platformPostUrl` (e.g., `https://www.instagram.com/reel/ABC123/`) as a stable identifier.  **Note:** For follower count history and growth metrics, use the dedicated `/v1/accounts/follower-stats` endpoint.  **LinkedIn Analytics:** - **Personal Accounts:** Per-post analytics available for posts published through Late. External posts cannot be synced due to LinkedIn API restrictions. - **Organization Accounts:** Full analytics support including external post syncing.  **Telegram Analytics:** - **Not available.** The Telegram Bot API does not provide message view counts, forwards, or engagement metrics. This is a Telegram platform limitation, not a Late limitation. View counts are only visible to channel admins in the Telegram app.  **Data Freshness:** Analytics data is cached and refreshed at most once per hour. When you call this endpoint, if the cache is older than 60 minutes, a background refresh is triggered and you'll see updated data on subsequent requests. There is no rate limit on API requests. 

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
            var postId = "postId_example";  // string? | Returns analytics for a single post. Accepts both Late Post IDs (from `POST /v1/posts`)  and External Post IDs (from this endpoint's list response). The API automatically  resolves Late Post IDs to their corresponding External Post analytics.  (optional) 
            var platform = "platform_example";  // string? | Filter by platform (default \"all\") (optional) 
            var profileId = "profileId_example";  // string? | Filter by profile ID (default \"all\") (optional) 
            var source = "all";  // string? | Filter by post source: - `late` - Only posts scheduled/published via Late API - `external` - Only posts synced from the platform (not posted via Late) - `all` - All posts (default)  (optional)  (default to all)
            var fromDate = DateOnly.Parse("2013-10-20");  // DateOnly? | Inclusive lower bound (optional) 
            var toDate = DateOnly.Parse("2013-10-20");  // DateOnly? | Inclusive upper bound (optional) 
            var limit = 50;  // int? | Page size (default 50) (optional)  (default to 50)
            var page = 1;  // int? | Page number (default 1) (optional)  (default to 1)
            var sortBy = "date";  // string? | Sort by date or engagement (optional)  (default to date)
            var order = "asc";  // string? | Sort order (optional)  (default to desc)

            try
            {
                // Unified analytics for posts
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
    // Unified analytics for posts
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
| **postId** | **string?** | Returns analytics for a single post. Accepts both Late Post IDs (from &#x60;POST /v1/posts&#x60;)  and External Post IDs (from this endpoint&#39;s list response). The API automatically  resolves Late Post IDs to their corresponding External Post analytics.  | [optional]  |
| **platform** | **string?** | Filter by platform (default \&quot;all\&quot;) | [optional]  |
| **profileId** | **string?** | Filter by profile ID (default \&quot;all\&quot;) | [optional]  |
| **source** | **string?** | Filter by post source: - &#x60;late&#x60; - Only posts scheduled/published via Late API - &#x60;external&#x60; - Only posts synced from the platform (not posted via Late) - &#x60;all&#x60; - All posts (default)  | [optional] [default to all] |
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

Get follower stats and growth metrics

Returns follower count history and growth metrics for connected social accounts. **Requires analytics add-on subscription.**  **Data Freshness:** Follower counts are automatically refreshed once per day. 

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
                // Get follower stats and growth metrics
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
    // Get follower stats and growth metrics
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

Get aggregate analytics for a LinkedIn personal account

Returns aggregate analytics across ALL posts for a LinkedIn personal account. Uses LinkedIn's `memberCreatorPostAnalytics` API with `q=me` finder.  **Important:** This endpoint only works for LinkedIn **personal** accounts. Organization accounts should use the standard `/v1/analytics` endpoint for per-post analytics.  **Required Scope:** `r_member_postAnalytics`  If the connected account doesn't have this scope, you'll receive a 403 error with instructions to reconnect.  **Aggregation Options:** - `TOTAL` (default): Returns lifetime totals for all metrics - `DAILY`: Returns daily breakdown of metrics over time  **Available Metrics:** - `IMPRESSION`: Number of times posts were displayed - `MEMBERS_REACHED`: Unique members who saw posts (NOT available with DAILY aggregation) - `REACTION`: Total reactions (likes, celebrates, etc.) - `COMMENT`: Total comments - `RESHARE`: Total reshares/reposts  **Date Range Filtering:** Use `startDate` and `endDate` parameters to filter analytics to a specific time period. If omitted, returns lifetime analytics.  **LinkedIn API Limitation:** The combination of `MEMBERS_REACHED` + `DAILY` aggregation is not supported by LinkedIn's API. 

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
            var aggregation = "TOTAL";  // string? | Type of aggregation for the analytics data. - `TOTAL` (default): Returns single totals for each metric - `DAILY`: Returns daily breakdown of metrics  Note: `MEMBERS_REACHED` metric is not available with `DAILY` aggregation.  (optional)  (default to TOTAL)
            var startDate = 2024-01-01;  // DateOnly? | Start date for analytics data in YYYY-MM-DD format. If provided without endDate, endDate defaults to today. If omitted entirely, returns lifetime analytics.  (optional) 
            var endDate = 2024-01-31;  // DateOnly? | End date for analytics data in YYYY-MM-DD format (exclusive). If provided without startDate, startDate defaults to 30 days before endDate.  (optional) 
            var metrics = IMPRESSION,REACTION,COMMENT;  // string? | Comma-separated list of metrics to fetch. If omitted, fetches all available metrics. Valid values: IMPRESSION, MEMBERS_REACHED, REACTION, COMMENT, RESHARE  (optional) 

            try
            {
                // Get aggregate analytics for a LinkedIn personal account
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
    // Get aggregate analytics for a LinkedIn personal account
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
| **aggregation** | **string?** | Type of aggregation for the analytics data. - &#x60;TOTAL&#x60; (default): Returns single totals for each metric - &#x60;DAILY&#x60;: Returns daily breakdown of metrics  Note: &#x60;MEMBERS_REACHED&#x60; metric is not available with &#x60;DAILY&#x60; aggregation.  | [optional] [default to TOTAL] |
| **startDate** | **DateOnly?** | Start date for analytics data in YYYY-MM-DD format. If provided without endDate, endDate defaults to today. If omitted entirely, returns lifetime analytics.  | [optional]  |
| **endDate** | **DateOnly?** | End date for analytics data in YYYY-MM-DD format (exclusive). If provided without startDate, startDate defaults to 30 days before endDate.  | [optional]  |
| **metrics** | **string?** | Comma-separated list of metrics to fetch. If omitted, fetches all available metrics. Valid values: IMPRESSION, MEMBERS_REACHED, REACTION, COMMENT, RESHARE  | [optional]  |

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

Get analytics for a specific LinkedIn post by URN

Returns analytics for a specific LinkedIn post using its URN. Works for both personal and organization accounts.  This is useful for fetching analytics of posts that weren't published through Late, as long as you have the post URN.  **For Personal Accounts:** - Uses `memberCreatorPostAnalytics` API + `memberCreatorVideoAnalytics` for video posts - Requires `r_member_postAnalytics` scope - Available metrics: impressions, reach, likes, comments, shares, video views (video posts only) - **Clicks are NOT available** for personal accounts  **For Organization Accounts:** - Uses `organizationalEntityShareStatistics` API + `videoAnalytics` for video posts - Requires `r_organization_social` scope - Available metrics: impressions, reach, clicks, likes, comments, shares, video views (video posts only), engagement rate 

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
                // Get analytics for a specific LinkedIn post by URN
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
    // Get analytics for a specific LinkedIn post by URN
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

YouTube daily views breakdown

Returns historical daily view counts for a specific YouTube video. Uses YouTube Analytics API v2 to fetch daily breakdowns including views, watch time, and subscriber changes.  **Required Scope:** This endpoint requires the `yt-analytics.readonly` OAuth scope. Existing YouTube accounts may need to re-authorize to grant this permission. If the scope is missing, the response will include a `reauthorizeUrl`.  **Data Latency:** YouTube Analytics data has a 2-3 day delay. The `endDate` is automatically capped to 3 days ago.  **Date Range:** Maximum 90 days of historical data available. Defaults to last 30 days. 

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
                // YouTube daily views breakdown
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
    // YouTube daily views breakdown
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

