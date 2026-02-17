# Late.Api.CommentsApi

All URIs are relative to *https://getlate.dev/api*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**DeleteInboxComment**](CommentsApi.md#deleteinboxcomment) | **DELETE** /v1/inbox/comments/{postId} | Delete comment |
| [**GetInboxPostComments**](CommentsApi.md#getinboxpostcomments) | **GET** /v1/inbox/comments/{postId} | Get post comments |
| [**HideInboxComment**](CommentsApi.md#hideinboxcomment) | **POST** /v1/inbox/comments/{postId}/{commentId}/hide | Hide comment |
| [**LikeInboxComment**](CommentsApi.md#likeinboxcomment) | **POST** /v1/inbox/comments/{postId}/{commentId}/like | Like comment |
| [**ListInboxComments**](CommentsApi.md#listinboxcomments) | **GET** /v1/inbox/comments | List commented posts |
| [**ReplyToInboxPost**](CommentsApi.md#replytoinboxpost) | **POST** /v1/inbox/comments/{postId} | Reply to comment |
| [**SendPrivateReplyToComment**](CommentsApi.md#sendprivatereplytocomment) | **POST** /v1/inbox/comments/{postId}/{commentId}/private-reply | Send private reply |
| [**UnhideInboxComment**](CommentsApi.md#unhideinboxcomment) | **DELETE** /v1/inbox/comments/{postId}/{commentId}/hide | Unhide comment |
| [**UnlikeInboxComment**](CommentsApi.md#unlikeinboxcomment) | **DELETE** /v1/inbox/comments/{postId}/{commentId}/like | Unlike comment |

<a id="deleteinboxcomment"></a>
# **DeleteInboxComment**
> DeleteInboxComment200Response DeleteInboxComment (string postId, string accountId, string commentId)

Delete comment

Delete a comment on a post. Supported by Facebook, Instagram, Bluesky, Reddit, YouTube, LinkedIn, and TikTok. Requires accountId and commentId query parameters. 

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
    public class DeleteInboxCommentExample
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
            var apiInstance = new CommentsApi(httpClient, config, httpClientHandler);
            var postId = "postId_example";  // string | Late post ID or platform-specific post ID. LinkedIn third-party posts accept full activity URN or numeric ID.
            var accountId = "accountId_example";  // string | 
            var commentId = "commentId_example";  // string | 

            try
            {
                // Delete comment
                DeleteInboxComment200Response result = apiInstance.DeleteInboxComment(postId, accountId, commentId);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling CommentsApi.DeleteInboxComment: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the DeleteInboxCommentWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Delete comment
    ApiResponse<DeleteInboxComment200Response> response = apiInstance.DeleteInboxCommentWithHttpInfo(postId, accountId, commentId);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling CommentsApi.DeleteInboxCommentWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **postId** | **string** | Late post ID or platform-specific post ID. LinkedIn third-party posts accept full activity URN or numeric ID. |  |
| **accountId** | **string** |  |  |
| **commentId** | **string** |  |  |

### Return type

[**DeleteInboxComment200Response**](DeleteInboxComment200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Comment deleted |  -  |
| **401** | Unauthorized |  -  |
| **403** | Inbox addon required |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="getinboxpostcomments"></a>
# **GetInboxPostComments**
> GetInboxPostComments200Response GetInboxPostComments (string postId, string accountId, string? subreddit = null, int? limit = null, string? cursor = null, string? commentId = null)

Get post comments

Fetch comments for a specific post. Requires accountId query parameter.

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
    public class GetInboxPostCommentsExample
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
            var apiInstance = new CommentsApi(httpClient, config, httpClientHandler);
            var postId = "postId_example";  // string | Late post ID or platform-specific post ID. Late IDs are auto-resolved. LinkedIn third-party posts accept full activity URN or numeric ID.
            var accountId = "accountId_example";  // string | 
            var subreddit = "subreddit_example";  // string? | (Reddit only) Subreddit name (optional) 
            var limit = 25;  // int? | Maximum number of comments to return (optional)  (default to 25)
            var cursor = "cursor_example";  // string? | Pagination cursor (optional) 
            var commentId = "commentId_example";  // string? | (Reddit only) Get replies to a specific comment (optional) 

            try
            {
                // Get post comments
                GetInboxPostComments200Response result = apiInstance.GetInboxPostComments(postId, accountId, subreddit, limit, cursor, commentId);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling CommentsApi.GetInboxPostComments: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the GetInboxPostCommentsWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Get post comments
    ApiResponse<GetInboxPostComments200Response> response = apiInstance.GetInboxPostCommentsWithHttpInfo(postId, accountId, subreddit, limit, cursor, commentId);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling CommentsApi.GetInboxPostCommentsWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **postId** | **string** | Late post ID or platform-specific post ID. Late IDs are auto-resolved. LinkedIn third-party posts accept full activity URN or numeric ID. |  |
| **accountId** | **string** |  |  |
| **subreddit** | **string?** | (Reddit only) Subreddit name | [optional]  |
| **limit** | **int?** | Maximum number of comments to return | [optional] [default to 25] |
| **cursor** | **string?** | Pagination cursor | [optional]  |
| **commentId** | **string?** | (Reddit only) Get replies to a specific comment | [optional]  |

### Return type

[**GetInboxPostComments200Response**](GetInboxPostComments200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Comments for the post |  -  |
| **401** | Unauthorized |  -  |
| **403** | Inbox addon required |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="hideinboxcomment"></a>
# **HideInboxComment**
> HideInboxComment200Response HideInboxComment (string postId, string commentId, HideInboxCommentRequest hideInboxCommentRequest)

Hide comment

Hide a comment on a post. Supported by Facebook, Instagram, and Threads. Hidden comments are only visible to the commenter and page admin. 

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
    public class HideInboxCommentExample
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
            var apiInstance = new CommentsApi(httpClient, config, httpClientHandler);
            var postId = "postId_example";  // string | 
            var commentId = "commentId_example";  // string | 
            var hideInboxCommentRequest = new HideInboxCommentRequest(); // HideInboxCommentRequest | 

            try
            {
                // Hide comment
                HideInboxComment200Response result = apiInstance.HideInboxComment(postId, commentId, hideInboxCommentRequest);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling CommentsApi.HideInboxComment: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the HideInboxCommentWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Hide comment
    ApiResponse<HideInboxComment200Response> response = apiInstance.HideInboxCommentWithHttpInfo(postId, commentId, hideInboxCommentRequest);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling CommentsApi.HideInboxCommentWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **postId** | **string** |  |  |
| **commentId** | **string** |  |  |
| **hideInboxCommentRequest** | [**HideInboxCommentRequest**](HideInboxCommentRequest.md) |  |  |

### Return type

[**HideInboxComment200Response**](HideInboxComment200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Comment hidden |  -  |
| **400** | Platform does not support hiding comments |  -  |
| **401** | Unauthorized |  -  |
| **403** | Inbox addon required |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="likeinboxcomment"></a>
# **LikeInboxComment**
> LikeInboxComment200Response LikeInboxComment (string postId, string commentId, LikeInboxCommentRequest likeInboxCommentRequest)

Like comment

Like or upvote a comment on a post. Supported platforms: Facebook, Twitter/X, Bluesky, Reddit. For Bluesky, the cid (content identifier) is required in the request body. 

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
    public class LikeInboxCommentExample
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
            var apiInstance = new CommentsApi(httpClient, config, httpClientHandler);
            var postId = "postId_example";  // string | 
            var commentId = "commentId_example";  // string | 
            var likeInboxCommentRequest = new LikeInboxCommentRequest(); // LikeInboxCommentRequest | 

            try
            {
                // Like comment
                LikeInboxComment200Response result = apiInstance.LikeInboxComment(postId, commentId, likeInboxCommentRequest);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling CommentsApi.LikeInboxComment: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the LikeInboxCommentWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Like comment
    ApiResponse<LikeInboxComment200Response> response = apiInstance.LikeInboxCommentWithHttpInfo(postId, commentId, likeInboxCommentRequest);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling CommentsApi.LikeInboxCommentWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **postId** | **string** |  |  |
| **commentId** | **string** |  |  |
| **likeInboxCommentRequest** | [**LikeInboxCommentRequest**](LikeInboxCommentRequest.md) |  |  |

### Return type

[**LikeInboxComment200Response**](LikeInboxComment200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Comment liked |  -  |
| **400** | Platform does not support liking comments |  -  |
| **401** | Unauthorized |  -  |
| **403** | Inbox addon required |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="listinboxcomments"></a>
# **ListInboxComments**
> ListInboxComments200Response ListInboxComments (string? profileId = null, string? platform = null, int? minComments = null, DateTime? since = null, string? sortBy = null, string? sortOrder = null, int? limit = null, string? cursor = null, string? accountId = null)

List commented posts

Returns posts with comment counts from all connected accounts. Aggregates data across multiple accounts.

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
    public class ListInboxCommentsExample
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
            var apiInstance = new CommentsApi(httpClient, config, httpClientHandler);
            var profileId = "profileId_example";  // string? | Filter by profile ID (optional) 
            var platform = "facebook";  // string? | Filter by platform (optional) 
            var minComments = 56;  // int? | Minimum comment count (optional) 
            var since = DateTime.Parse("2013-10-20T19:20:30+01:00");  // DateTime? | Posts created after this date (optional) 
            var sortBy = "date";  // string? | Sort field (optional)  (default to date)
            var sortOrder = "asc";  // string? | Sort order (optional)  (default to desc)
            var limit = 50;  // int? |  (optional)  (default to 50)
            var cursor = "cursor_example";  // string? |  (optional) 
            var accountId = "accountId_example";  // string? | Filter by specific social account ID (optional) 

            try
            {
                // List commented posts
                ListInboxComments200Response result = apiInstance.ListInboxComments(profileId, platform, minComments, since, sortBy, sortOrder, limit, cursor, accountId);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling CommentsApi.ListInboxComments: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the ListInboxCommentsWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // List commented posts
    ApiResponse<ListInboxComments200Response> response = apiInstance.ListInboxCommentsWithHttpInfo(profileId, platform, minComments, since, sortBy, sortOrder, limit, cursor, accountId);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling CommentsApi.ListInboxCommentsWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **profileId** | **string?** | Filter by profile ID | [optional]  |
| **platform** | **string?** | Filter by platform | [optional]  |
| **minComments** | **int?** | Minimum comment count | [optional]  |
| **since** | **DateTime?** | Posts created after this date | [optional]  |
| **sortBy** | **string?** | Sort field | [optional] [default to date] |
| **sortOrder** | **string?** | Sort order | [optional] [default to desc] |
| **limit** | **int?** |  | [optional] [default to 50] |
| **cursor** | **string?** |  | [optional]  |
| **accountId** | **string?** | Filter by specific social account ID | [optional]  |

### Return type

[**ListInboxComments200Response**](ListInboxComments200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Aggregated posts with comments |  -  |
| **401** | Unauthorized |  -  |
| **403** | Inbox addon required |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="replytoinboxpost"></a>
# **ReplyToInboxPost**
> ReplyToInboxPost200Response ReplyToInboxPost (string postId, ReplyToInboxPostRequest replyToInboxPostRequest)

Reply to comment

Post a reply to a post or specific comment. Requires accountId in request body.

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
    public class ReplyToInboxPostExample
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
            var apiInstance = new CommentsApi(httpClient, config, httpClientHandler);
            var postId = "postId_example";  // string | Late post ID or platform-specific post ID. LinkedIn third-party posts accept full activity URN or numeric ID.
            var replyToInboxPostRequest = new ReplyToInboxPostRequest(); // ReplyToInboxPostRequest | 

            try
            {
                // Reply to comment
                ReplyToInboxPost200Response result = apiInstance.ReplyToInboxPost(postId, replyToInboxPostRequest);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling CommentsApi.ReplyToInboxPost: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the ReplyToInboxPostWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Reply to comment
    ApiResponse<ReplyToInboxPost200Response> response = apiInstance.ReplyToInboxPostWithHttpInfo(postId, replyToInboxPostRequest);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling CommentsApi.ReplyToInboxPostWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **postId** | **string** | Late post ID or platform-specific post ID. LinkedIn third-party posts accept full activity URN or numeric ID. |  |
| **replyToInboxPostRequest** | [**ReplyToInboxPostRequest**](ReplyToInboxPostRequest.md) |  |  |

### Return type

[**ReplyToInboxPost200Response**](ReplyToInboxPost200Response.md)

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

<a id="sendprivatereplytocomment"></a>
# **SendPrivateReplyToComment**
> SendPrivateReplyToComment200Response SendPrivateReplyToComment (string postId, string commentId, SendPrivateReplyToCommentRequest sendPrivateReplyToCommentRequest)

Send private reply

Send a private message to the author of a comment. Supported on Instagram and Facebook only. One reply per comment, must be sent within 7 days, text only.

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
    public class SendPrivateReplyToCommentExample
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
            var apiInstance = new CommentsApi(httpClient, config, httpClientHandler);
            var postId = "postId_example";  // string | The media/post ID (Instagram media ID or Facebook post ID)
            var commentId = "commentId_example";  // string | The comment ID to send a private reply to
            var sendPrivateReplyToCommentRequest = new SendPrivateReplyToCommentRequest(); // SendPrivateReplyToCommentRequest | 

            try
            {
                // Send private reply
                SendPrivateReplyToComment200Response result = apiInstance.SendPrivateReplyToComment(postId, commentId, sendPrivateReplyToCommentRequest);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling CommentsApi.SendPrivateReplyToComment: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the SendPrivateReplyToCommentWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Send private reply
    ApiResponse<SendPrivateReplyToComment200Response> response = apiInstance.SendPrivateReplyToCommentWithHttpInfo(postId, commentId, sendPrivateReplyToCommentRequest);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling CommentsApi.SendPrivateReplyToCommentWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **postId** | **string** | The media/post ID (Instagram media ID or Facebook post ID) |  |
| **commentId** | **string** | The comment ID to send a private reply to |  |
| **sendPrivateReplyToCommentRequest** | [**SendPrivateReplyToCommentRequest**](SendPrivateReplyToCommentRequest.md) |  |  |

### Return type

[**SendPrivateReplyToComment200Response**](SendPrivateReplyToComment200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Private reply sent successfully |  -  |
| **400** | Bad request |  -  |
| **401** | Unauthorized |  -  |
| **403** | Inbox addon required |  -  |
| **404** | Account not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="unhideinboxcomment"></a>
# **UnhideInboxComment**
> HideInboxComment200Response UnhideInboxComment (string postId, string commentId, string accountId)

Unhide comment

Unhide a previously hidden comment. Supported by Facebook, Instagram, and Threads. 

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
    public class UnhideInboxCommentExample
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
            var apiInstance = new CommentsApi(httpClient, config, httpClientHandler);
            var postId = "postId_example";  // string | 
            var commentId = "commentId_example";  // string | 
            var accountId = "accountId_example";  // string | 

            try
            {
                // Unhide comment
                HideInboxComment200Response result = apiInstance.UnhideInboxComment(postId, commentId, accountId);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling CommentsApi.UnhideInboxComment: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the UnhideInboxCommentWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Unhide comment
    ApiResponse<HideInboxComment200Response> response = apiInstance.UnhideInboxCommentWithHttpInfo(postId, commentId, accountId);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling CommentsApi.UnhideInboxCommentWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **postId** | **string** |  |  |
| **commentId** | **string** |  |  |
| **accountId** | **string** |  |  |

### Return type

[**HideInboxComment200Response**](HideInboxComment200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Comment unhidden |  -  |
| **400** | Platform does not support unhiding comments |  -  |
| **401** | Unauthorized |  -  |
| **403** | Inbox addon required |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="unlikeinboxcomment"></a>
# **UnlikeInboxComment**
> UnlikeInboxComment200Response UnlikeInboxComment (string postId, string commentId, string accountId, string? likeUri = null)

Unlike comment

Remove a like from a comment. Supported platforms: Facebook, Twitter/X, Bluesky, Reddit. For Bluesky, the likeUri query parameter is required. 

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
    public class UnlikeInboxCommentExample
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
            var apiInstance = new CommentsApi(httpClient, config, httpClientHandler);
            var postId = "postId_example";  // string | 
            var commentId = "commentId_example";  // string | 
            var accountId = "accountId_example";  // string | 
            var likeUri = "likeUri_example";  // string? | (Bluesky only) The like URI returned when liking (optional) 

            try
            {
                // Unlike comment
                UnlikeInboxComment200Response result = apiInstance.UnlikeInboxComment(postId, commentId, accountId, likeUri);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling CommentsApi.UnlikeInboxComment: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the UnlikeInboxCommentWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Unlike comment
    ApiResponse<UnlikeInboxComment200Response> response = apiInstance.UnlikeInboxCommentWithHttpInfo(postId, commentId, accountId, likeUri);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling CommentsApi.UnlikeInboxCommentWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **postId** | **string** |  |  |
| **commentId** | **string** |  |  |
| **accountId** | **string** |  |  |
| **likeUri** | **string?** | (Bluesky only) The like URI returned when liking | [optional]  |

### Return type

[**UnlikeInboxComment200Response**](UnlikeInboxComment200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Comment unliked |  -  |
| **400** | Platform does not support unliking comments |  -  |
| **401** | Unauthorized |  -  |
| **403** | Inbox addon required |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

