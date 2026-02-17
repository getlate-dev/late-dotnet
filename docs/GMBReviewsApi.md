# Late.Api.GMBReviewsApi

All URIs are relative to *https://getlate.dev/api*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**GetGoogleBusinessReviews**](GMBReviewsApi.md#getgooglebusinessreviews) | **GET** /v1/accounts/{accountId}/gmb-reviews | Get reviews |

<a id="getgooglebusinessreviews"></a>
# **GetGoogleBusinessReviews**
> GetGoogleBusinessReviews200Response GetGoogleBusinessReviews (string accountId, int? pageSize = null, string? pageToken = null)

Get reviews

Returns reviews for a GBP account including ratings, comments, and owner replies. Use nextPageToken for pagination.

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
    public class GetGoogleBusinessReviewsExample
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
            var apiInstance = new GMBReviewsApi(httpClient, config, httpClientHandler);
            var accountId = "accountId_example";  // string | The Late account ID (from /v1/accounts)
            var pageSize = 50;  // int? | Number of reviews to fetch per page (max 50) (optional)  (default to 50)
            var pageToken = "pageToken_example";  // string? | Pagination token from previous response (optional) 

            try
            {
                // Get reviews
                GetGoogleBusinessReviews200Response result = apiInstance.GetGoogleBusinessReviews(accountId, pageSize, pageToken);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling GMBReviewsApi.GetGoogleBusinessReviews: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the GetGoogleBusinessReviewsWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Get reviews
    ApiResponse<GetGoogleBusinessReviews200Response> response = apiInstance.GetGoogleBusinessReviewsWithHttpInfo(accountId, pageSize, pageToken);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling GMBReviewsApi.GetGoogleBusinessReviewsWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **accountId** | **string** | The Late account ID (from /v1/accounts) |  |
| **pageSize** | **int?** | Number of reviews to fetch per page (max 50) | [optional] [default to 50] |
| **pageToken** | **string?** | Pagination token from previous response | [optional]  |

### Return type

[**GetGoogleBusinessReviews200Response**](GetGoogleBusinessReviews200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Reviews fetched successfully |  -  |
| **400** | Invalid request - not a Google Business account or missing location |  -  |
| **401** | Unauthorized or token expired |  -  |
| **403** | Permission denied for this location |  -  |
| **404** | Resource not found |  -  |
| **500** | Failed to fetch reviews |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

