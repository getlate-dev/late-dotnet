# Late.Api.TwitterEngagementApi

All URIs are relative to *https://getlate.dev/api*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**BookmarkPost**](TwitterEngagementApi.md#bookmarkpost) | **POST** /v1/twitter/bookmark | Bookmark a tweet |
| [**FollowUser**](TwitterEngagementApi.md#followuser) | **POST** /v1/twitter/follow | Follow a user |
| [**RemoveBookmark**](TwitterEngagementApi.md#removebookmark) | **DELETE** /v1/twitter/bookmark | Remove bookmark |
| [**RetweetPost**](TwitterEngagementApi.md#retweetpost) | **POST** /v1/twitter/retweet | Retweet a post |
| [**UndoRetweet**](TwitterEngagementApi.md#undoretweet) | **DELETE** /v1/twitter/retweet | Undo retweet |
| [**UnfollowUser**](TwitterEngagementApi.md#unfollowuser) | **DELETE** /v1/twitter/follow | Unfollow a user |

<a id="bookmarkpost"></a>
# **BookmarkPost**
> BookmarkPost200Response BookmarkPost (BookmarkPostRequest bookmarkPostRequest)

Bookmark a tweet

Bookmark a tweet by ID. Requires the bookmark.write OAuth scope. Rate limit: 50 requests per 15-min window. 

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
    public class BookmarkPostExample
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
            var apiInstance = new TwitterEngagementApi(httpClient, config, httpClientHandler);
            var bookmarkPostRequest = new BookmarkPostRequest(); // BookmarkPostRequest | 

            try
            {
                // Bookmark a tweet
                BookmarkPost200Response result = apiInstance.BookmarkPost(bookmarkPostRequest);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling TwitterEngagementApi.BookmarkPost: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the BookmarkPostWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Bookmark a tweet
    ApiResponse<BookmarkPost200Response> response = apiInstance.BookmarkPostWithHttpInfo(bookmarkPostRequest);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling TwitterEngagementApi.BookmarkPostWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **bookmarkPostRequest** | [**BookmarkPostRequest**](BookmarkPostRequest.md) |  |  |

### Return type

[**BookmarkPost200Response**](BookmarkPost200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Tweet bookmarked |  -  |
| **400** | Bad request or platform limitation |  -  |
| **401** | Unauthorized |  -  |
| **404** | Account not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="followuser"></a>
# **FollowUser**
> FollowUser200Response FollowUser (FollowUserRequest followUserRequest)

Follow a user

Follow a user on X/Twitter. Requires the follows.write OAuth scope. For protected accounts, a follow request is sent instead (pending_follow will be true). 

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
    public class FollowUserExample
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
            var apiInstance = new TwitterEngagementApi(httpClient, config, httpClientHandler);
            var followUserRequest = new FollowUserRequest(); // FollowUserRequest | 

            try
            {
                // Follow a user
                FollowUser200Response result = apiInstance.FollowUser(followUserRequest);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling TwitterEngagementApi.FollowUser: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the FollowUserWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Follow a user
    ApiResponse<FollowUser200Response> response = apiInstance.FollowUserWithHttpInfo(followUserRequest);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling TwitterEngagementApi.FollowUserWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **followUserRequest** | [**FollowUserRequest**](FollowUserRequest.md) |  |  |

### Return type

[**FollowUser200Response**](FollowUser200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | User followed or follow request sent |  -  |
| **400** | Bad request or platform limitation |  -  |
| **401** | Unauthorized |  -  |
| **404** | Account not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="removebookmark"></a>
# **RemoveBookmark**
> RemoveBookmark200Response RemoveBookmark (string accountId, string tweetId)

Remove bookmark

Remove a bookmark from a tweet. 

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
    public class RemoveBookmarkExample
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
            var apiInstance = new TwitterEngagementApi(httpClient, config, httpClientHandler);
            var accountId = "accountId_example";  // string | 
            var tweetId = "tweetId_example";  // string | The ID of the tweet to unbookmark

            try
            {
                // Remove bookmark
                RemoveBookmark200Response result = apiInstance.RemoveBookmark(accountId, tweetId);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling TwitterEngagementApi.RemoveBookmark: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the RemoveBookmarkWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Remove bookmark
    ApiResponse<RemoveBookmark200Response> response = apiInstance.RemoveBookmarkWithHttpInfo(accountId, tweetId);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling TwitterEngagementApi.RemoveBookmarkWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **accountId** | **string** |  |  |
| **tweetId** | **string** | The ID of the tweet to unbookmark |  |

### Return type

[**RemoveBookmark200Response**](RemoveBookmark200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Bookmark removed |  -  |
| **400** | Bad request |  -  |
| **401** | Unauthorized |  -  |
| **404** | Account not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="retweetpost"></a>
# **RetweetPost**
> RetweetPost200Response RetweetPost (RetweetPostRequest retweetPostRequest)

Retweet a post

Retweet (repost) a tweet by ID. Rate limit: 50 requests per 15-min window. Shares the 300/3hr creation limit with tweet creation. 

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
    public class RetweetPostExample
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
            var apiInstance = new TwitterEngagementApi(httpClient, config, httpClientHandler);
            var retweetPostRequest = new RetweetPostRequest(); // RetweetPostRequest | 

            try
            {
                // Retweet a post
                RetweetPost200Response result = apiInstance.RetweetPost(retweetPostRequest);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling TwitterEngagementApi.RetweetPost: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the RetweetPostWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Retweet a post
    ApiResponse<RetweetPost200Response> response = apiInstance.RetweetPostWithHttpInfo(retweetPostRequest);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling TwitterEngagementApi.RetweetPostWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **retweetPostRequest** | [**RetweetPostRequest**](RetweetPostRequest.md) |  |  |

### Return type

[**RetweetPost200Response**](RetweetPost200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Tweet retweeted |  -  |
| **400** | Bad request or platform limitation |  -  |
| **401** | Unauthorized |  -  |
| **404** | Account not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="undoretweet"></a>
# **UndoRetweet**
> UndoRetweet200Response UndoRetweet (string accountId, string tweetId)

Undo retweet

Undo a retweet (un-repost a tweet). 

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
    public class UndoRetweetExample
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
            var apiInstance = new TwitterEngagementApi(httpClient, config, httpClientHandler);
            var accountId = "accountId_example";  // string | 
            var tweetId = "tweetId_example";  // string | The ID of the original tweet to un-retweet

            try
            {
                // Undo retweet
                UndoRetweet200Response result = apiInstance.UndoRetweet(accountId, tweetId);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling TwitterEngagementApi.UndoRetweet: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the UndoRetweetWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Undo retweet
    ApiResponse<UndoRetweet200Response> response = apiInstance.UndoRetweetWithHttpInfo(accountId, tweetId);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling TwitterEngagementApi.UndoRetweetWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **accountId** | **string** |  |  |
| **tweetId** | **string** | The ID of the original tweet to un-retweet |  |

### Return type

[**UndoRetweet200Response**](UndoRetweet200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Retweet undone |  -  |
| **400** | Bad request |  -  |
| **401** | Unauthorized |  -  |
| **404** | Account not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="unfollowuser"></a>
# **UnfollowUser**
> UnfollowUser200Response UnfollowUser (string accountId, string targetUserId)

Unfollow a user

Unfollow a user on X/Twitter. 

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
    public class UnfollowUserExample
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
            var apiInstance = new TwitterEngagementApi(httpClient, config, httpClientHandler);
            var accountId = "accountId_example";  // string | 
            var targetUserId = "targetUserId_example";  // string | The Twitter ID of the user to unfollow

            try
            {
                // Unfollow a user
                UnfollowUser200Response result = apiInstance.UnfollowUser(accountId, targetUserId);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling TwitterEngagementApi.UnfollowUser: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the UnfollowUserWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Unfollow a user
    ApiResponse<UnfollowUser200Response> response = apiInstance.UnfollowUserWithHttpInfo(accountId, targetUserId);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling TwitterEngagementApi.UnfollowUserWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **accountId** | **string** |  |  |
| **targetUserId** | **string** | The Twitter ID of the user to unfollow |  |

### Return type

[**UnfollowUser200Response**](UnfollowUser200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | User unfollowed |  -  |
| **400** | Bad request |  -  |
| **401** | Unauthorized |  -  |
| **404** | Account not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

