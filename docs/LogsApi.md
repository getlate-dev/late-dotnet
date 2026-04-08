# Late.Api.LogsApi

All URIs are relative to *https://zernio.com/api*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**GetPostLogs**](LogsApi.md#getpostlogs) | **GET** /v1/posts/{postId}/logs | Get post logs |
| [**ListConnectionLogs**](LogsApi.md#listconnectionlogs) | **GET** /v1/connections/logs | List connection logs |
| [**ListLogs**](LogsApi.md#listlogs) | **GET** /v1/logs | List activity logs |
| [**ListPostsLogs**](LogsApi.md#listpostslogs) | **GET** /v1/posts/logs | List publishing logs |

<a id="getpostlogs"></a>
# **GetPostLogs**
> GetPostLogs200Response GetPostLogs (string postId, int? limit = null)

Get post logs

Retrieve all publishing logs for a specific post. Shows the complete history of publishing attempts for that post across all platforms. 

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
    public class GetPostLogsExample
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
            var apiInstance = new LogsApi(httpClient, config, httpClientHandler);
            var postId = "postId_example";  // string | The post ID
            var limit = 50;  // int? | Maximum number of logs to return (max 100) (optional)  (default to 50)

            try
            {
                // Get post logs
                GetPostLogs200Response result = apiInstance.GetPostLogs(postId, limit);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling LogsApi.GetPostLogs: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the GetPostLogsWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Get post logs
    ApiResponse<GetPostLogs200Response> response = apiInstance.GetPostLogsWithHttpInfo(postId, limit);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling LogsApi.GetPostLogsWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **postId** | **string** | The post ID |  |
| **limit** | **int?** | Maximum number of logs to return (max 100) | [optional] [default to 50] |

### Return type

[**GetPostLogs200Response**](GetPostLogs200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Post logs retrieved successfully |  -  |
| **401** | Unauthorized |  -  |
| **403** | Forbidden - not authorized to view this post |  -  |
| **404** | Resource not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="listconnectionlogs"></a>
# **ListConnectionLogs**
> ListConnectionLogs200Response ListConnectionLogs (string? platform = null, string? eventType = null, string? status = null, int? days = null, int? limit = null, int? skip = null)

List connection logs

**Deprecated.** Use `GET /v1/logs?type=connections` instead. Retrieve connection event logs. Logs are retained for 90 days. 

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
    public class ListConnectionLogsExample
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
            var apiInstance = new LogsApi(httpClient, config, httpClientHandler);
            var platform = "tiktok";  // string? | Filter by platform (optional) 
            var eventType = "connect_success";  // string? | Filter by event type (optional) 
            var status = "success";  // string? | Filter by status (shorthand for event types) (optional) 
            var days = 7;  // int? | Number of days to look back (max 7) (optional)  (default to 7)
            var limit = 50;  // int? | Maximum number of logs to return (max 100) (optional)  (default to 50)
            var skip = 0;  // int? | Number of logs to skip (for pagination) (optional)  (default to 0)

            try
            {
                // List connection logs
                ListConnectionLogs200Response result = apiInstance.ListConnectionLogs(platform, eventType, status, days, limit, skip);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling LogsApi.ListConnectionLogs: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the ListConnectionLogsWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // List connection logs
    ApiResponse<ListConnectionLogs200Response> response = apiInstance.ListConnectionLogsWithHttpInfo(platform, eventType, status, days, limit, skip);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling LogsApi.ListConnectionLogsWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **platform** | **string?** | Filter by platform | [optional]  |
| **eventType** | **string?** | Filter by event type | [optional]  |
| **status** | **string?** | Filter by status (shorthand for event types) | [optional]  |
| **days** | **int?** | Number of days to look back (max 7) | [optional] [default to 7] |
| **limit** | **int?** | Maximum number of logs to return (max 100) | [optional] [default to 50] |
| **skip** | **int?** | Number of logs to skip (for pagination) | [optional] [default to 0] |

### Return type

[**ListConnectionLogs200Response**](ListConnectionLogs200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Connection logs retrieved successfully |  -  |
| **401** | Unauthorized |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="listlogs"></a>
# **ListLogs**
> ListLogs200Response ListLogs (string? type = null, string? status = null, string? platform = null, string? action = null, string? search = null, int? days = null, int? limit = null, int? skip = null)

List activity logs

Unified logs endpoint. Returns logs for publishing, connections, webhooks, and messaging. Filter by type, platform, status, and time range. Logs are retained for 90 days. 

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
    public class ListLogsExample
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
            var apiInstance = new LogsApi(httpClient, config, httpClientHandler);
            var type = "publishing";  // string? | Log category to query (optional)  (default to publishing)
            var status = "success";  // string? | Filter by status (optional) 
            var platform = "tiktok";  // string? | Filter by platform (optional) 
            var action = "action_example";  // string? | Filter by action (e.g., post.published, message.sent, account.connected, webhook.delivered) (optional) 
            var search = "search_example";  // string? | Free-text search across log fields (optional) 
            var days = 90;  // int? | Number of days to look back (max 90) (optional)  (default to 90)
            var limit = 50;  // int? | Maximum number of logs to return (max 100) (optional)  (default to 50)
            var skip = 0;  // int? | Number of logs to skip (for pagination) (optional)  (default to 0)

            try
            {
                // List activity logs
                ListLogs200Response result = apiInstance.ListLogs(type, status, platform, action, search, days, limit, skip);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling LogsApi.ListLogs: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the ListLogsWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // List activity logs
    ApiResponse<ListLogs200Response> response = apiInstance.ListLogsWithHttpInfo(type, status, platform, action, search, days, limit, skip);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling LogsApi.ListLogsWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **type** | **string?** | Log category to query | [optional] [default to publishing] |
| **status** | **string?** | Filter by status | [optional]  |
| **platform** | **string?** | Filter by platform | [optional]  |
| **action** | **string?** | Filter by action (e.g., post.published, message.sent, account.connected, webhook.delivered) | [optional]  |
| **search** | **string?** | Free-text search across log fields | [optional]  |
| **days** | **int?** | Number of days to look back (max 90) | [optional] [default to 90] |
| **limit** | **int?** | Maximum number of logs to return (max 100) | [optional] [default to 50] |
| **skip** | **int?** | Number of logs to skip (for pagination) | [optional] [default to 0] |

### Return type

[**ListLogs200Response**](ListLogs200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Logs retrieved successfully |  -  |
| **401** | Unauthorized |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="listpostslogs"></a>
# **ListPostsLogs**
> ListPostsLogs200Response ListPostsLogs (string? status = null, string? platform = null, string? action = null, int? days = null, int? limit = null, int? skip = null, string? search = null)

List publishing logs

**Deprecated.** Use `GET /v1/logs?type=publishing` instead. Retrieve publishing logs for all posts. Logs are retained for 90 days. 

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
    public class ListPostsLogsExample
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
            var apiInstance = new LogsApi(httpClient, config, httpClientHandler);
            var status = "success";  // string? | Filter by log status (optional) 
            var platform = "tiktok";  // string? | Filter by platform (optional) 
            var action = "publish";  // string? | Filter by action type (optional) 
            var days = 7;  // int? | Number of days to look back (max 7) (optional)  (default to 7)
            var limit = 50;  // int? | Maximum number of logs to return (max 100) (optional)  (default to 50)
            var skip = 0;  // int? | Number of logs to skip (for pagination) (optional)  (default to 0)
            var search = "search_example";  // string? | Search through log entries by text content. (optional) 

            try
            {
                // List publishing logs
                ListPostsLogs200Response result = apiInstance.ListPostsLogs(status, platform, action, days, limit, skip, search);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling LogsApi.ListPostsLogs: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the ListPostsLogsWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // List publishing logs
    ApiResponse<ListPostsLogs200Response> response = apiInstance.ListPostsLogsWithHttpInfo(status, platform, action, days, limit, skip, search);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling LogsApi.ListPostsLogsWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **status** | **string?** | Filter by log status | [optional]  |
| **platform** | **string?** | Filter by platform | [optional]  |
| **action** | **string?** | Filter by action type | [optional]  |
| **days** | **int?** | Number of days to look back (max 7) | [optional] [default to 7] |
| **limit** | **int?** | Maximum number of logs to return (max 100) | [optional] [default to 50] |
| **skip** | **int?** | Number of logs to skip (for pagination) | [optional] [default to 0] |
| **search** | **string?** | Search through log entries by text content. | [optional]  |

### Return type

[**ListPostsLogs200Response**](ListPostsLogs200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Publishing logs retrieved successfully |  -  |
| **401** | Unauthorized |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

