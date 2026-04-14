# Late.Api.LogsApi

All URIs are relative to *https://zernio.com/api*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**ListLogs**](LogsApi.md#listlogs) | **GET** /v1/logs | List activity logs |

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

