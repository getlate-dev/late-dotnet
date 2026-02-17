# Late.Api.ReviewsApi

All URIs are relative to *https://getlate.dev/api*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**DeleteInboxReviewReply**](ReviewsApi.md#deleteinboxreviewreply) | **DELETE** /v1/inbox/reviews/{reviewId}/reply | Delete review reply |
| [**ListInboxReviews**](ReviewsApi.md#listinboxreviews) | **GET** /v1/inbox/reviews | List reviews |
| [**ReplyToInboxReview**](ReviewsApi.md#replytoinboxreview) | **POST** /v1/inbox/reviews/{reviewId}/reply | Reply to review |

<a id="deleteinboxreviewreply"></a>
# **DeleteInboxReviewReply**
> DeleteInboxReviewReply200Response DeleteInboxReviewReply (string reviewId, DeleteInboxReviewReplyRequest deleteInboxReviewReplyRequest)

Delete review reply

Delete a reply to a review (Google Business only). Requires accountId in request body.

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
    public class DeleteInboxReviewReplyExample
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
            var apiInstance = new ReviewsApi(httpClient, config, httpClientHandler);
            var reviewId = "reviewId_example";  // string | 
            var deleteInboxReviewReplyRequest = new DeleteInboxReviewReplyRequest(); // DeleteInboxReviewReplyRequest | 

            try
            {
                // Delete review reply
                DeleteInboxReviewReply200Response result = apiInstance.DeleteInboxReviewReply(reviewId, deleteInboxReviewReplyRequest);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling ReviewsApi.DeleteInboxReviewReply: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the DeleteInboxReviewReplyWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Delete review reply
    ApiResponse<DeleteInboxReviewReply200Response> response = apiInstance.DeleteInboxReviewReplyWithHttpInfo(reviewId, deleteInboxReviewReplyRequest);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling ReviewsApi.DeleteInboxReviewReplyWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **reviewId** | **string** |  |  |
| **deleteInboxReviewReplyRequest** | [**DeleteInboxReviewReplyRequest**](DeleteInboxReviewReplyRequest.md) |  |  |

### Return type

[**DeleteInboxReviewReply200Response**](DeleteInboxReviewReply200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Reply deleted |  -  |
| **401** | Unauthorized |  -  |
| **403** | Inbox addon required |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="listinboxreviews"></a>
# **ListInboxReviews**
> ListInboxReviews200Response ListInboxReviews (string? profileId = null, string? platform = null, int? minRating = null, int? maxRating = null, bool? hasReply = null, string? sortBy = null, string? sortOrder = null, int? limit = null, string? cursor = null, string? accountId = null)

List reviews

Fetch reviews from all connected Facebook Pages and Google Business accounts. Aggregates data with filtering and sorting options.  **Supported platforms:** Facebook, Google Business 

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
    public class ListInboxReviewsExample
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
            var apiInstance = new ReviewsApi(httpClient, config, httpClientHandler);
            var profileId = "profileId_example";  // string? |  (optional) 
            var platform = "facebook";  // string? |  (optional) 
            var minRating = 56;  // int? |  (optional) 
            var maxRating = 56;  // int? |  (optional) 
            var hasReply = true;  // bool? | Filter by reply status (optional) 
            var sortBy = "date";  // string? |  (optional)  (default to date)
            var sortOrder = "asc";  // string? |  (optional)  (default to desc)
            var limit = 25;  // int? |  (optional)  (default to 25)
            var cursor = "cursor_example";  // string? |  (optional) 
            var accountId = "accountId_example";  // string? | Filter by specific social account ID (optional) 

            try
            {
                // List reviews
                ListInboxReviews200Response result = apiInstance.ListInboxReviews(profileId, platform, minRating, maxRating, hasReply, sortBy, sortOrder, limit, cursor, accountId);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling ReviewsApi.ListInboxReviews: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the ListInboxReviewsWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // List reviews
    ApiResponse<ListInboxReviews200Response> response = apiInstance.ListInboxReviewsWithHttpInfo(profileId, platform, minRating, maxRating, hasReply, sortBy, sortOrder, limit, cursor, accountId);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling ReviewsApi.ListInboxReviewsWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **profileId** | **string?** |  | [optional]  |
| **platform** | **string?** |  | [optional]  |
| **minRating** | **int?** |  | [optional]  |
| **maxRating** | **int?** |  | [optional]  |
| **hasReply** | **bool?** | Filter by reply status | [optional]  |
| **sortBy** | **string?** |  | [optional] [default to date] |
| **sortOrder** | **string?** |  | [optional] [default to desc] |
| **limit** | **int?** |  | [optional] [default to 25] |
| **cursor** | **string?** |  | [optional]  |
| **accountId** | **string?** | Filter by specific social account ID | [optional]  |

### Return type

[**ListInboxReviews200Response**](ListInboxReviews200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Aggregated reviews |  -  |
| **401** | Unauthorized |  -  |
| **403** | Inbox addon required |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="replytoinboxreview"></a>
# **ReplyToInboxReview**
> ReplyToInboxReview200Response ReplyToInboxReview (string reviewId, ReplyToInboxReviewRequest replyToInboxReviewRequest)

Reply to review

Post a reply to a review. Requires accountId in request body.

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
    public class ReplyToInboxReviewExample
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
            var apiInstance = new ReviewsApi(httpClient, config, httpClientHandler);
            var reviewId = "reviewId_example";  // string | Review ID (URL-encoded for Google Business)
            var replyToInboxReviewRequest = new ReplyToInboxReviewRequest(); // ReplyToInboxReviewRequest | 

            try
            {
                // Reply to review
                ReplyToInboxReview200Response result = apiInstance.ReplyToInboxReview(reviewId, replyToInboxReviewRequest);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling ReviewsApi.ReplyToInboxReview: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the ReplyToInboxReviewWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Reply to review
    ApiResponse<ReplyToInboxReview200Response> response = apiInstance.ReplyToInboxReviewWithHttpInfo(reviewId, replyToInboxReviewRequest);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling ReviewsApi.ReplyToInboxReviewWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **reviewId** | **string** | Review ID (URL-encoded for Google Business) |  |
| **replyToInboxReviewRequest** | [**ReplyToInboxReviewRequest**](ReplyToInboxReviewRequest.md) |  |  |

### Return type

[**ReplyToInboxReview200Response**](ReplyToInboxReview200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Reply posted |  -  |
| **401** | Unauthorized |  -  |
| **403** | Inbox addon required |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

