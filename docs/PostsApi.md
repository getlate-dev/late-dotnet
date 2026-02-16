# Late.Api.PostsApi

All URIs are relative to *https://getlate.dev/api*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**BulkUploadPosts**](PostsApi.md#bulkuploadposts) | **POST** /v1/posts/bulk-upload | Validate and schedule multiple posts from CSV |
| [**CreatePost**](PostsApi.md#createpost) | **POST** /v1/posts | Create a draft, scheduled, or immediate post |
| [**DeletePost**](PostsApi.md#deletepost) | **DELETE** /v1/posts/{postId} | Delete a post |
| [**GetPost**](PostsApi.md#getpost) | **GET** /v1/posts/{postId} | Get a single post |
| [**ListPosts**](PostsApi.md#listposts) | **GET** /v1/posts | List posts visible to the authenticated user |
| [**RetryPost**](PostsApi.md#retrypost) | **POST** /v1/posts/{postId}/retry | Retry publishing a failed or partial post |
| [**UnpublishPost**](PostsApi.md#unpublishpost) | **POST** /v1/posts/{postId}/unpublish | Delete a published post from a social media platform |
| [**UpdatePost**](PostsApi.md#updatepost) | **PUT** /v1/posts/{postId} | Update a post |

<a id="bulkuploadposts"></a>
# **BulkUploadPosts**
> BulkUploadPosts200Response BulkUploadPosts (bool? dryRun = null, FileParameter? file = null)

Validate and schedule multiple posts from CSV

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
                // Validate and schedule multiple posts from CSV
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
    // Validate and schedule multiple posts from CSV
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
| **429** | Rate limit exceeded. Can be triggered by: - **API rate limit**: Requests per minute exceeded - **Account cooldown**: One or more accounts are temporarily rate-limited  |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="createpost"></a>
# **CreatePost**
> PostCreateResponse CreatePost (CreatePostRequest createPostRequest)

Create a draft, scheduled, or immediate post

**Getting Post URLs:** - For immediate posts (`publishNow: true`): The response includes `platformPostUrl` in each platform entry under `post.platforms[]`. - For scheduled posts: Fetch the post via `GET /v1/posts/{postId}` after the scheduled time; `platformPostUrl` will be populated once published.  **Content/Caption requirements:** - `content` (caption/description) is optional when:   - Media is attached (`mediaItems` or per-platform `customMedia`)   - All platforms have `customContent` set   - Posting only to YouTube (title is used instead) - Text-only posts (no media) require `content` - Stories do not use captions (content is ignored) - Reels, feed posts, and other media posts can have optional captions  Platform constraints: - YouTube requires a video in mediaItems; optional custom thumbnail via MediaItem.thumbnail. - Instagram and TikTok require media; do not mix videos and images for TikTok. - Instagram carousels support up to 10 items; Stories publish as 'story'. - Threads carousels support up to 10 images (no videos in carousels); single posts support one image or video. - Facebook Stories require media (single image or video); set contentType to 'story' in platformSpecificData. - LinkedIn multi-image supports up to 20 images; single PDF documents supported (max 100MB, ~300 pages, cannot mix with other media). - Pinterest supports single image via image_url or a single video per Pin; boardId is required. - Bluesky supports up to 4 images per post. Images may be automatically recompressed to ≤ ~1MB to satisfy Bluesky's blob limit. When no media is attached, a link preview may be generated for URLs in the text. - Snapchat requires media (single image or video); set contentType to 'story', 'saved_story', or 'spotlight' in platformSpecificData. Stories are ephemeral (24h), Saved Stories are permanent, Spotlight is for video content.  **Multi-page/multi-location posting:** Some platforms allow posting to multiple pages, organizations, or locations from a single account connection. Use the same accountId multiple times with different targets in platformSpecificData: - Facebook: `pageId` - post to multiple Facebook Pages (list via GET /v1/accounts/{id}/facebook-page) - LinkedIn: `organizationUrn` - post to multiple organizations (list via GET /v1/accounts/{id}/linkedin-organizations) - Google Business: `locationId` - post to multiple locations (list via GET /v1/accounts/{id}/gmb-locations) - Reddit: `subreddit` - post to multiple subreddits from the same account 

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
                // Create a draft, scheduled, or immediate post
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
    // Create a draft, scheduled, or immediate post
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
| **429** | Rate limit exceeded. Can be triggered by: - **API rate limit**: Requests per minute exceeded (Free: 60, Build: 120, Accelerate: 600, Unlimited: 1,200) - **Velocity limit**: 15 posts per hour per account exceeded - **Account cooldown**: Account temporarily rate-limited due to repeated errors (escalating: 10min, 20min, 40min, up to 24h) - **Daily post limit**: Platform daily limits exceeded (X: 20, Pinterest: 25, Instagram/Facebook: 100, Threads: 250, others: 50)  |  * Retry-After - Seconds until the rate limit resets (for API rate limits) <br>  * X-RateLimit-Limit - The rate limit ceiling <br>  * X-RateLimit-Remaining - Requests remaining in current window <br>  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="deletepost"></a>
# **DeletePost**
> PostDeleteResponse DeletePost (string postId)

Delete a post

Delete a post. Published posts cannot be deleted.  When deleting a scheduled or draft post that consumed upload quota, the quota will be automatically refunded. 

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
                // Delete a post
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
    // Delete a post
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

Get a single post

Fetch a single post by ID. For published posts, this returns `platformPostUrl`  for each platform - useful for retrieving post URLs after scheduled posts publish. 

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
                // Get a single post
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
    // Get a single post
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

List posts visible to the authenticated user

**Getting Post URLs:** For published posts, each platform entry includes `platformPostUrl` with the public URL. Use `status=published` filter to fetch only published posts with their URLs.  Notes and constraints by platform when interpreting the response: - YouTube: posts always include at least one video in mediaItems. - Instagram/TikTok: posts always include media; drafts may omit media until finalized in client. - TikTok: mediaItems will not mix photos and videos in the same post. 

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
                // List posts visible to the authenticated user
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
    // List posts visible to the authenticated user
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

Retry publishing a failed or partial post

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
                // Retry publishing a failed or partial post
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
    // Retry publishing a failed or partial post
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
| **429** | Rate limit exceeded. Can be triggered by: - **API rate limit**: Requests per minute exceeded - **Velocity limit**: 15 posts per hour per account exceeded - **Account cooldown**: Account temporarily rate-limited due to repeated errors  |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="unpublishpost"></a>
# **UnpublishPost**
> UnpublishPost200Response UnpublishPost (string postId, UnpublishPostRequest unpublishPostRequest)

Delete a published post from a social media platform

Permanently deletes a published post from the specified social media platform. The post record in Late is kept but its platform status is set to \"cancelled\".  **Supported platforms:** Threads, Facebook, Twitter/X, LinkedIn, YouTube, Pinterest, Reddit, Bluesky, Google Business, Telegram.  **Not supported:** - **Instagram:** No deletion API available. Posts must be deleted manually. - **TikTok:** No deletion API available. Posts must be deleted manually. - **Snapchat:** No deletion API available. Posts must be deleted manually.  **Platform notes:** - **Telegram:** Messages older than 48 hours may fail to delete (Telegram Bot API limitation). - **YouTube:** This permanently deletes the video from YouTube. 

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
                // Delete a published post from a social media platform
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
    // Delete a published post from a social media platform
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
| **400** | Invalid request. Possible reasons: - Platform not recognized or not supported for deletion - Post does not have the specified platform - Post is not in \&quot;published\&quot; status on that platform - No platform post ID found (post may not have been published correctly) - No access token (account needs to be reconnected)  |  -  |
| **401** | Unauthorized |  -  |
| **403** | Forbidden |  -  |
| **404** | Resource not found |  -  |
| **500** | Platform API deletion failed |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="updatepost"></a>
# **UpdatePost**
> PostUpdateResponse UpdatePost (string postId, UpdatePostRequest updatePostRequest)

Update a post

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
                // Update a post
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
    // Update a post
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

