# Late.Api.PostsApi

All URIs are relative to *https://getlate.dev/api*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**BulkUploadPosts**](PostsApi.md#bulkuploadposts) | **POST** /v1/posts/bulk-upload | Bulk upload from CSV |
| [**CreatePost**](PostsApi.md#createpost) | **POST** /v1/posts | Create post |
| [**DeletePost**](PostsApi.md#deletepost) | **DELETE** /v1/posts/{postId} | Delete post |
| [**GetPost**](PostsApi.md#getpost) | **GET** /v1/posts/{postId} | Get post |
| [**ListPosts**](PostsApi.md#listposts) | **GET** /v1/posts | List posts |
| [**RetryPost**](PostsApi.md#retrypost) | **POST** /v1/posts/{postId}/retry | Retry failed post |
| [**UnpublishPost**](PostsApi.md#unpublishpost) | **POST** /v1/posts/{postId}/unpublish | Unpublish post |
| [**UpdatePost**](PostsApi.md#updatepost) | **PUT** /v1/posts/{postId} | Update post |

<a id="bulkuploadposts"></a>
# **BulkUploadPosts**
> BulkUploadPosts200Response BulkUploadPosts (bool? dryRun = null, FileParameter? file = null)

Bulk upload from CSV

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
    public class BulkUploadPostsExample
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
            var apiInstance = new PostsApi(httpClient, config, httpClientHandler);
            var dryRun = false;  // bool? |  (optional)  (default to false)
            var file = new System.IO.MemoryStream(System.IO.File.ReadAllBytes("/path/to/file.txt"));  // FileParameter? |  (optional) 

            try
            {
                // Bulk upload from CSV
                BulkUploadPosts200Response result = apiInstance.BulkUploadPosts(dryRun, file);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling PostsApi.BulkUploadPosts: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the BulkUploadPostsWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Bulk upload from CSV
    ApiResponse<BulkUploadPosts200Response> response = apiInstance.BulkUploadPostsWithHttpInfo(dryRun, file);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling PostsApi.BulkUploadPostsWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **dryRun** | **bool?** |  | [optional] [default to false] |
| **file** | **FileParameter?****FileParameter?** |  | [optional]  |

### Return type

[**BulkUploadPosts200Response**](BulkUploadPosts200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: multipart/form-data
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Bulk upload results |  -  |
| **207** | Partial success |  -  |
| **400** | Invalid CSV or validation errors |  -  |
| **401** | Unauthorized |  -  |
| **429** | Rate limit exceeded. Possible causes: API rate limit (requests per minute) or account cooldown (one or more accounts temporarily rate-limited).  |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="createpost"></a>
# **CreatePost**
> PostCreateResponse CreatePost (CreatePostRequest createPostRequest)

Create post

Immediate posts (publishNow: true) include platformPostUrl in the response. Scheduled posts: fetch via GET /v1/posts/{postId} after publish time. content is optional when media is attached, all platforms have customContent, or posting to YouTube only. Text-only posts require content. Stories ignore captions. Platform constraints: YouTube requires video. Instagram/TikTok require media (TikTok cannot mix videos and images). Instagram carousels up to 10 items, Threads up to 10 images. Facebook Stories need single image/video with contentType story. LinkedIn up to 20 images or single PDF. Pinterest single image/video with boardId. Bluesky up to 4 images. Snapchat single image/video. 

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
    public class CreatePostExample
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
            var apiInstance = new PostsApi(httpClient, config, httpClientHandler);
            var createPostRequest = new CreatePostRequest(); // CreatePostRequest | 

            try
            {
                // Create post
                PostCreateResponse result = apiInstance.CreatePost(createPostRequest);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling PostsApi.CreatePost: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the CreatePostWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Create post
    ApiResponse<PostCreateResponse> response = apiInstance.CreatePostWithHttpInfo(createPostRequest);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling PostsApi.CreatePostWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **createPostRequest** | [**CreatePostRequest**](CreatePostRequest.md) |  |  |

### Return type

[**PostCreateResponse**](PostCreateResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Post created |  -  |
| **400** | Validation error |  -  |
| **401** | Unauthorized |  -  |
| **403** | Forbidden |  -  |
| **409** | Duplicate content detected |  -  |
| **429** | Rate limit exceeded. Possible causes: API rate limit (requests per minute), velocity limit (15 posts/hour per account), account cooldown (escalating from 10min to 24h due to repeated errors), or daily platform post limits.  |  * Retry-After - Seconds until the rate limit resets (for API rate limits) <br>  * X-RateLimit-Limit - The rate limit ceiling <br>  * X-RateLimit-Remaining - Requests remaining in current window <br>  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="deletepost"></a>
# **DeletePost**
> PostDeleteResponse DeletePost (string postId)

Delete post

Delete a draft or scheduled post from Late. Only posts that have not been published can be deleted. To remove a published post from a social media platform, use the [Unpublish endpoint](#tag/Posts/operation/unpublishPost) instead. When deleting a scheduled or draft post that consumed upload quota, the quota will be automatically refunded. 

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
    public class DeletePostExample
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
            var apiInstance = new PostsApi(httpClient, config, httpClientHandler);
            var postId = "postId_example";  // string | 

            try
            {
                // Delete post
                PostDeleteResponse result = apiInstance.DeletePost(postId);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling PostsApi.DeletePost: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the DeletePostWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Delete post
    ApiResponse<PostDeleteResponse> response = apiInstance.DeletePostWithHttpInfo(postId);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling PostsApi.DeletePostWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **postId** | **string** |  |  |

### Return type

[**PostDeleteResponse**](PostDeleteResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Deleted |  -  |
| **400** | Cannot delete published posts |  -  |
| **401** | Unauthorized |  -  |
| **403** | Forbidden |  -  |
| **404** | Resource not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="getpost"></a>
# **GetPost**
> PostGetResponse GetPost (string postId)

Get post

Fetch a single post by ID. For published posts, this returns platformPostUrl for each platform. 

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
    public class GetPostExample
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
            var apiInstance = new PostsApi(httpClient, config, httpClientHandler);
            var postId = "postId_example";  // string | 

            try
            {
                // Get post
                PostGetResponse result = apiInstance.GetPost(postId);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling PostsApi.GetPost: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the GetPostWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Get post
    ApiResponse<PostGetResponse> response = apiInstance.GetPostWithHttpInfo(postId);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling PostsApi.GetPostWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **postId** | **string** |  |  |

### Return type

[**PostGetResponse**](PostGetResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Post |  -  |
| **401** | Unauthorized |  -  |
| **403** | Forbidden |  -  |
| **404** | Resource not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="listposts"></a>
# **ListPosts**
> PostsListResponse ListPosts (int? page = null, int? limit = null, string? status = null, string? platform = null, string? profileId = null, string? createdBy = null, DateOnly? dateFrom = null, DateOnly? dateTo = null, bool? includeHidden = null)

List posts

For published posts, each platform entry includes platformPostUrl with the public URL. Use status=published to fetch only published posts with their URLs.  Platform notes: YouTube posts always include at least one video. Instagram/TikTok posts always include media (drafts may omit media). TikTok does not mix photos and videos in the same post. 

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
    public class ListPostsExample
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
            var apiInstance = new PostsApi(httpClient, config, httpClientHandler);
            var page = 1;  // int? | Page number (1-based) (optional)  (default to 1)
            var limit = 10;  // int? | Page size (optional)  (default to 10)
            var status = "draft";  // string? |  (optional) 
            var platform = twitter;  // string? |  (optional) 
            var profileId = "profileId_example";  // string? |  (optional) 
            var createdBy = "createdBy_example";  // string? |  (optional) 
            var dateFrom = DateOnly.Parse("2013-10-20");  // DateOnly? |  (optional) 
            var dateTo = DateOnly.Parse("2013-10-20");  // DateOnly? |  (optional) 
            var includeHidden = false;  // bool? |  (optional)  (default to false)

            try
            {
                // List posts
                PostsListResponse result = apiInstance.ListPosts(page, limit, status, platform, profileId, createdBy, dateFrom, dateTo, includeHidden);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling PostsApi.ListPosts: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the ListPostsWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // List posts
    ApiResponse<PostsListResponse> response = apiInstance.ListPostsWithHttpInfo(page, limit, status, platform, profileId, createdBy, dateFrom, dateTo, includeHidden);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling PostsApi.ListPostsWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **page** | **int?** | Page number (1-based) | [optional] [default to 1] |
| **limit** | **int?** | Page size | [optional] [default to 10] |
| **status** | **string?** |  | [optional]  |
| **platform** | **string?** |  | [optional]  |
| **profileId** | **string?** |  | [optional]  |
| **createdBy** | **string?** |  | [optional]  |
| **dateFrom** | **DateOnly?** |  | [optional]  |
| **dateTo** | **DateOnly?** |  | [optional]  |
| **includeHidden** | **bool?** |  | [optional] [default to false] |

### Return type

[**PostsListResponse**](PostsListResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Paginated posts |  -  |
| **401** | Unauthorized |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="retrypost"></a>
# **RetryPost**
> PostRetryResponse RetryPost (string postId)

Retry failed post

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
    public class RetryPostExample
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
            var apiInstance = new PostsApi(httpClient, config, httpClientHandler);
            var postId = "postId_example";  // string | 

            try
            {
                // Retry failed post
                PostRetryResponse result = apiInstance.RetryPost(postId);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling PostsApi.RetryPost: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the RetryPostWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Retry failed post
    ApiResponse<PostRetryResponse> response = apiInstance.RetryPostWithHttpInfo(postId);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling PostsApi.RetryPostWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **postId** | **string** |  |  |

### Return type

[**PostRetryResponse**](PostRetryResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Retry successful |  -  |
| **207** | Partial success |  -  |
| **400** | Invalid state |  -  |
| **401** | Unauthorized |  -  |
| **403** | Forbidden |  -  |
| **404** | Resource not found |  -  |
| **409** | Post is currently publishing |  -  |
| **429** | Rate limit exceeded. Possible causes: API rate limit (requests per minute), velocity limit (15 posts/hour per account), or account cooldown (temporarily rate-limited due to repeated errors).  |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="unpublishpost"></a>
# **UnpublishPost**
> UnpublishPost200Response UnpublishPost (string postId, UnpublishPostRequest unpublishPostRequest)

Unpublish post

Deletes a published post from the specified platform. The post record in Late is kept but its platform status is updated to cancelled. Supported: Threads, Facebook, Twitter/X, LinkedIn, YouTube, Pinterest, Reddit, Bluesky, Google Business, Telegram. Not supported: Instagram, TikTok, Snapchat (must be deleted manually). Threaded posts (Twitter, Threads, Bluesky) delete all items in the thread. Telegram messages older than 48h may fail to delete. YouTube deletion is permanent. 

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
    public class UnpublishPostExample
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
            var apiInstance = new PostsApi(httpClient, config, httpClientHandler);
            var postId = "postId_example";  // string | 
            var unpublishPostRequest = new UnpublishPostRequest(); // UnpublishPostRequest | 

            try
            {
                // Unpublish post
                UnpublishPost200Response result = apiInstance.UnpublishPost(postId, unpublishPostRequest);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling PostsApi.UnpublishPost: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the UnpublishPostWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Unpublish post
    ApiResponse<UnpublishPost200Response> response = apiInstance.UnpublishPostWithHttpInfo(postId, unpublishPostRequest);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling PostsApi.UnpublishPostWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **postId** | **string** |  |  |
| **unpublishPostRequest** | [**UnpublishPostRequest**](UnpublishPostRequest.md) |  |  |

### Return type

[**UnpublishPost200Response**](UnpublishPost200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Post deleted from platform |  -  |
| **400** | Invalid request: platform not supported for deletion, post not on that platform, not published, no platform post ID, or no access token. |  -  |
| **401** | Unauthorized |  -  |
| **403** | Forbidden |  -  |
| **404** | Resource not found |  -  |
| **500** | Platform API deletion failed |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="updatepost"></a>
# **UpdatePost**
> PostUpdateResponse UpdatePost (string postId, UpdatePostRequest updatePostRequest)

Update post

Update an existing post. Only draft, scheduled, failed, and partial posts can be edited. Published, publishing, and cancelled posts cannot be modified. 

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
    public class UpdatePostExample
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
            var apiInstance = new PostsApi(httpClient, config, httpClientHandler);
            var postId = "postId_example";  // string | 
            var updatePostRequest = new UpdatePostRequest(); // UpdatePostRequest | 

            try
            {
                // Update post
                PostUpdateResponse result = apiInstance.UpdatePost(postId, updatePostRequest);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling PostsApi.UpdatePost: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the UpdatePostWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Update post
    ApiResponse<PostUpdateResponse> response = apiInstance.UpdatePostWithHttpInfo(postId, updatePostRequest);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling PostsApi.UpdatePostWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **postId** | **string** |  |  |
| **updatePostRequest** | [**UpdatePostRequest**](UpdatePostRequest.md) |  |  |

### Return type

[**PostUpdateResponse**](PostUpdateResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Post updated |  -  |
| **207** | Partial publish success |  -  |
| **400** | Invalid request |  -  |
| **401** | Unauthorized |  -  |
| **403** | Forbidden |  -  |
| **404** | Resource not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

