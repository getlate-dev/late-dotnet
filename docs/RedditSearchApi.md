# Late.Api.RedditSearchApi

All URIs are relative to *https://getlate.dev/api*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**GetRedditFeed**](RedditSearchApi.md#getredditfeed) | **GET** /v1/reddit/feed | Fetch subreddit feed via a connected account |
| [**SearchReddit**](RedditSearchApi.md#searchreddit) | **GET** /v1/reddit/search | Search Reddit posts via a connected account |

<a id="getredditfeed"></a>
# **GetRedditFeed**
> GetRedditFeed200Response GetRedditFeed (string accountId, string? subreddit = null, string? sort = null, int? limit = null, string? after = null, string? t = null)

Fetch subreddit feed via a connected account

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
    public class GetRedditFeedExample
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
            var apiInstance = new RedditSearchApi(httpClient, config, httpClientHandler);
            var accountId = "accountId_example";  // string | 
            var subreddit = "subreddit_example";  // string? |  (optional) 
            var sort = "hot";  // string? |  (optional)  (default to hot)
            var limit = 25;  // int? |  (optional)  (default to 25)
            var after = "after_example";  // string? |  (optional) 
            var t = "hour";  // string? |  (optional) 

            try
            {
                // Fetch subreddit feed via a connected account
                GetRedditFeed200Response result = apiInstance.GetRedditFeed(accountId, subreddit, sort, limit, after, t);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling RedditSearchApi.GetRedditFeed: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the GetRedditFeedWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Fetch subreddit feed via a connected account
    ApiResponse<GetRedditFeed200Response> response = apiInstance.GetRedditFeedWithHttpInfo(accountId, subreddit, sort, limit, after, t);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling RedditSearchApi.GetRedditFeedWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **accountId** | **string** |  |  |
| **subreddit** | **string?** |  | [optional]  |
| **sort** | **string?** |  | [optional] [default to hot] |
| **limit** | **int?** |  | [optional] [default to 25] |
| **after** | **string?** |  | [optional]  |
| **t** | **string?** |  | [optional]  |

### Return type

[**GetRedditFeed200Response**](GetRedditFeed200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Feed items |  -  |
| **400** | Missing params |  -  |
| **401** | Unauthorized |  -  |
| **404** | Account not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="searchreddit"></a>
# **SearchReddit**
> SearchReddit200Response SearchReddit (string accountId, string q, string? subreddit = null, string? restrictSr = null, string? sort = null, int? limit = null, string? after = null)

Search Reddit posts via a connected account

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
    public class SearchRedditExample
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
            var apiInstance = new RedditSearchApi(httpClient, config, httpClientHandler);
            var accountId = "accountId_example";  // string | 
            var q = "q_example";  // string | 
            var subreddit = "subreddit_example";  // string? |  (optional) 
            var restrictSr = "0";  // string? |  (optional) 
            var sort = "relevance";  // string? |  (optional)  (default to new)
            var limit = 25;  // int? |  (optional)  (default to 25)
            var after = "after_example";  // string? |  (optional) 

            try
            {
                // Search Reddit posts via a connected account
                SearchReddit200Response result = apiInstance.SearchReddit(accountId, q, subreddit, restrictSr, sort, limit, after);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling RedditSearchApi.SearchReddit: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the SearchRedditWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Search Reddit posts via a connected account
    ApiResponse<SearchReddit200Response> response = apiInstance.SearchRedditWithHttpInfo(accountId, q, subreddit, restrictSr, sort, limit, after);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling RedditSearchApi.SearchRedditWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **accountId** | **string** |  |  |
| **q** | **string** |  |  |
| **subreddit** | **string?** |  | [optional]  |
| **restrictSr** | **string?** |  | [optional]  |
| **sort** | **string?** |  | [optional] [default to new] |
| **limit** | **int?** |  | [optional] [default to 25] |
| **after** | **string?** |  | [optional]  |

### Return type

[**SearchReddit200Response**](SearchReddit200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Search results |  -  |
| **400** | Missing params |  -  |
| **401** | Unauthorized |  -  |
| **404** | Account not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

