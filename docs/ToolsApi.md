# Late.Api.ToolsApi

All URIs are relative to *https://getlate.dev/api*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**CheckInstagramHashtags**](ToolsApi.md#checkinstagramhashtags) | **POST** /v1/tools/instagram/hashtag-checker | Check Instagram hashtag bans |
| [**DownloadBlueskyMedia**](ToolsApi.md#downloadblueskymedia) | **GET** /v1/tools/bluesky/download | Download Bluesky media |
| [**DownloadFacebookVideo**](ToolsApi.md#downloadfacebookvideo) | **GET** /v1/tools/facebook/download | Download Facebook video |
| [**DownloadInstagramMedia**](ToolsApi.md#downloadinstagrammedia) | **GET** /v1/tools/instagram/download | Download Instagram media |
| [**DownloadLinkedInVideo**](ToolsApi.md#downloadlinkedinvideo) | **GET** /v1/tools/linkedin/download | Download LinkedIn video |
| [**DownloadTikTokVideo**](ToolsApi.md#downloadtiktokvideo) | **GET** /v1/tools/tiktok/download | Download TikTok video |
| [**DownloadTwitterMedia**](ToolsApi.md#downloadtwittermedia) | **GET** /v1/tools/twitter/download | Download Twitter/X media |
| [**DownloadYouTubeVideo**](ToolsApi.md#downloadyoutubevideo) | **GET** /v1/tools/youtube/download | Download YouTube video |
| [**GetYouTubeTranscript**](ToolsApi.md#getyoutubetranscript) | **GET** /v1/tools/youtube/transcript | Get YouTube transcript |

<a id="checkinstagramhashtags"></a>
# **CheckInstagramHashtags**
> CheckInstagramHashtags200Response CheckInstagramHashtags (CheckInstagramHashtagsRequest checkInstagramHashtagsRequest)

Check Instagram hashtag bans

Check if Instagram hashtags are banned, restricted, or safe to use.  **Rate Limits:** Build (50/day), Accelerate (500/day), Unlimited (unlimited) 

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
    public class CheckInstagramHashtagsExample
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
            var apiInstance = new ToolsApi(httpClient, config, httpClientHandler);
            var checkInstagramHashtagsRequest = new CheckInstagramHashtagsRequest(); // CheckInstagramHashtagsRequest | 

            try
            {
                // Check Instagram hashtag bans
                CheckInstagramHashtags200Response result = apiInstance.CheckInstagramHashtags(checkInstagramHashtagsRequest);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling ToolsApi.CheckInstagramHashtags: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the CheckInstagramHashtagsWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Check Instagram hashtag bans
    ApiResponse<CheckInstagramHashtags200Response> response = apiInstance.CheckInstagramHashtagsWithHttpInfo(checkInstagramHashtagsRequest);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling ToolsApi.CheckInstagramHashtagsWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **checkInstagramHashtagsRequest** | [**CheckInstagramHashtagsRequest**](CheckInstagramHashtagsRequest.md) |  |  |

### Return type

[**CheckInstagramHashtags200Response**](CheckInstagramHashtags200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Success |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="downloadblueskymedia"></a>
# **DownloadBlueskyMedia**
> DownloadBlueskyMedia200Response DownloadBlueskyMedia (string url)

Download Bluesky media

Download videos from Bluesky posts.  **Rate Limits:** Build (50/day), Accelerate (500/day), Unlimited (unlimited) 

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
    public class DownloadBlueskyMediaExample
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
            var apiInstance = new ToolsApi(httpClient, config, httpClientHandler);
            var url = https://bsky.app/profile/user.bsky.social/post/abc123;  // string | Bluesky post URL

            try
            {
                // Download Bluesky media
                DownloadBlueskyMedia200Response result = apiInstance.DownloadBlueskyMedia(url);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling ToolsApi.DownloadBlueskyMedia: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the DownloadBlueskyMediaWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Download Bluesky media
    ApiResponse<DownloadBlueskyMedia200Response> response = apiInstance.DownloadBlueskyMediaWithHttpInfo(url);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling ToolsApi.DownloadBlueskyMediaWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **url** | **string** | Bluesky post URL |  |

### Return type

[**DownloadBlueskyMedia200Response**](DownloadBlueskyMedia200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Success |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="downloadfacebookvideo"></a>
# **DownloadFacebookVideo**
> DownloadFacebookVideo200Response DownloadFacebookVideo (string url)

Download Facebook video

Download videos and reels from Facebook.  **Rate Limits:** Build (50/day), Accelerate (500/day), Unlimited (unlimited) 

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
    public class DownloadFacebookVideoExample
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
            var apiInstance = new ToolsApi(httpClient, config, httpClientHandler);
            var url = "url_example";  // string | Facebook video or reel URL

            try
            {
                // Download Facebook video
                DownloadFacebookVideo200Response result = apiInstance.DownloadFacebookVideo(url);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling ToolsApi.DownloadFacebookVideo: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the DownloadFacebookVideoWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Download Facebook video
    ApiResponse<DownloadFacebookVideo200Response> response = apiInstance.DownloadFacebookVideoWithHttpInfo(url);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling ToolsApi.DownloadFacebookVideoWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **url** | **string** | Facebook video or reel URL |  |

### Return type

[**DownloadFacebookVideo200Response**](DownloadFacebookVideo200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Success |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="downloadinstagrammedia"></a>
# **DownloadInstagramMedia**
> DownloadInstagramMedia200Response DownloadInstagramMedia (string url)

Download Instagram media

Download Instagram reels, posts, or photos.  **Rate Limits:** Build (50/day), Accelerate (500/day), Unlimited (unlimited) 

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
    public class DownloadInstagramMediaExample
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
            var apiInstance = new ToolsApi(httpClient, config, httpClientHandler);
            var url = https://www.instagram.com/reel/ABC123/;  // string | Instagram reel or post URL

            try
            {
                // Download Instagram media
                DownloadInstagramMedia200Response result = apiInstance.DownloadInstagramMedia(url);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling ToolsApi.DownloadInstagramMedia: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the DownloadInstagramMediaWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Download Instagram media
    ApiResponse<DownloadInstagramMedia200Response> response = apiInstance.DownloadInstagramMediaWithHttpInfo(url);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling ToolsApi.DownloadInstagramMediaWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **url** | **string** | Instagram reel or post URL |  |

### Return type

[**DownloadInstagramMedia200Response**](DownloadInstagramMedia200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Success |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="downloadlinkedinvideo"></a>
# **DownloadLinkedInVideo**
> DownloadInstagramMedia200Response DownloadLinkedInVideo (string url)

Download LinkedIn video

Download videos from LinkedIn posts.  **Rate Limits:** Build (50/day), Accelerate (500/day), Unlimited (unlimited) 

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
    public class DownloadLinkedInVideoExample
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
            var apiInstance = new ToolsApi(httpClient, config, httpClientHandler);
            var url = "url_example";  // string | LinkedIn post URL

            try
            {
                // Download LinkedIn video
                DownloadInstagramMedia200Response result = apiInstance.DownloadLinkedInVideo(url);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling ToolsApi.DownloadLinkedInVideo: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the DownloadLinkedInVideoWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Download LinkedIn video
    ApiResponse<DownloadInstagramMedia200Response> response = apiInstance.DownloadLinkedInVideoWithHttpInfo(url);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling ToolsApi.DownloadLinkedInVideoWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **url** | **string** | LinkedIn post URL |  |

### Return type

[**DownloadInstagramMedia200Response**](DownloadInstagramMedia200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Success |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="downloadtiktokvideo"></a>
# **DownloadTikTokVideo**
> DownloadTikTokVideo200Response DownloadTikTokVideo (string url, string? action = null, string? formatId = null)

Download TikTok video

Download TikTok videos with or without watermark.  **Rate Limits:** Build (50/day), Accelerate (500/day), Unlimited (unlimited) 

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
    public class DownloadTikTokVideoExample
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
            var apiInstance = new ToolsApi(httpClient, config, httpClientHandler);
            var url = "url_example";  // string | TikTok video URL or ID
            var action = "download";  // string? | 'formats' to list available formats (optional)  (default to download)
            var formatId = "formatId_example";  // string? | Specific format ID (0 = no watermark, etc.) (optional) 

            try
            {
                // Download TikTok video
                DownloadTikTokVideo200Response result = apiInstance.DownloadTikTokVideo(url, action, formatId);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling ToolsApi.DownloadTikTokVideo: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the DownloadTikTokVideoWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Download TikTok video
    ApiResponse<DownloadTikTokVideo200Response> response = apiInstance.DownloadTikTokVideoWithHttpInfo(url, action, formatId);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling ToolsApi.DownloadTikTokVideoWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **url** | **string** | TikTok video URL or ID |  |
| **action** | **string?** | &#39;formats&#39; to list available formats | [optional] [default to download] |
| **formatId** | **string?** | Specific format ID (0 &#x3D; no watermark, etc.) | [optional]  |

### Return type

[**DownloadTikTokVideo200Response**](DownloadTikTokVideo200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Success |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="downloadtwittermedia"></a>
# **DownloadTwitterMedia**
> DownloadInstagramMedia200Response DownloadTwitterMedia (string url, string? action = null, string? formatId = null)

Download Twitter/X media

Download videos from Twitter/X posts.  **Rate Limits:** Build (50/day), Accelerate (500/day), Unlimited (unlimited) 

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
    public class DownloadTwitterMediaExample
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
            var apiInstance = new ToolsApi(httpClient, config, httpClientHandler);
            var url = https://x.com/user/status/123456789;  // string | Twitter/X post URL
            var action = "download";  // string? |  (optional)  (default to download)
            var formatId = "formatId_example";  // string? |  (optional) 

            try
            {
                // Download Twitter/X media
                DownloadInstagramMedia200Response result = apiInstance.DownloadTwitterMedia(url, action, formatId);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling ToolsApi.DownloadTwitterMedia: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the DownloadTwitterMediaWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Download Twitter/X media
    ApiResponse<DownloadInstagramMedia200Response> response = apiInstance.DownloadTwitterMediaWithHttpInfo(url, action, formatId);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling ToolsApi.DownloadTwitterMediaWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **url** | **string** | Twitter/X post URL |  |
| **action** | **string?** |  | [optional] [default to download] |
| **formatId** | **string?** |  | [optional]  |

### Return type

[**DownloadInstagramMedia200Response**](DownloadInstagramMedia200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Success |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="downloadyoutubevideo"></a>
# **DownloadYouTubeVideo**
> DownloadYouTubeVideo200Response DownloadYouTubeVideo (string url, string? action = null, string? format = null, string? quality = null, string? formatId = null)

Download YouTube video

Download YouTube videos or audio. Returns available formats or direct download URL.  **Rate Limits:** Build (50/day), Accelerate (500/day), Unlimited (unlimited) 

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
    public class DownloadYouTubeVideoExample
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
            var apiInstance = new ToolsApi(httpClient, config, httpClientHandler);
            var url = https://www.youtube.com/watch?v=dQw4w9WgXcQ;  // string | YouTube video URL or video ID
            var action = "download";  // string? | Action to perform: 'download' returns download URL, 'formats' lists available formats (optional)  (default to download)
            var format = "video";  // string? | Desired format (when action=download) (optional)  (default to video)
            var quality = "hd";  // string? | Desired quality (when action=download) (optional)  (default to hd)
            var formatId = "formatId_example";  // string? | Specific format ID from formats list (optional) 

            try
            {
                // Download YouTube video
                DownloadYouTubeVideo200Response result = apiInstance.DownloadYouTubeVideo(url, action, format, quality, formatId);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling ToolsApi.DownloadYouTubeVideo: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the DownloadYouTubeVideoWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Download YouTube video
    ApiResponse<DownloadYouTubeVideo200Response> response = apiInstance.DownloadYouTubeVideoWithHttpInfo(url, action, format, quality, formatId);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling ToolsApi.DownloadYouTubeVideoWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **url** | **string** | YouTube video URL or video ID |  |
| **action** | **string?** | Action to perform: &#39;download&#39; returns download URL, &#39;formats&#39; lists available formats | [optional] [default to download] |
| **format** | **string?** | Desired format (when action&#x3D;download) | [optional] [default to video] |
| **quality** | **string?** | Desired quality (when action&#x3D;download) | [optional] [default to hd] |
| **formatId** | **string?** | Specific format ID from formats list | [optional]  |

### Return type

[**DownloadYouTubeVideo200Response**](DownloadYouTubeVideo200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Success |  * X-RateLimit-Limit - Daily rate limit <br>  * X-RateLimit-Remaining - Remaining calls today <br>  * X-RateLimit-Reset - Unix timestamp when limit resets <br>  |
| **401** | Unauthorized |  -  |
| **403** | Tools API not available on free plan |  -  |
| **429** | Daily rate limit exceeded |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="getyoutubetranscript"></a>
# **GetYouTubeTranscript**
> GetYouTubeTranscript200Response GetYouTubeTranscript (string url, string? lang = null)

Get YouTube transcript

Extract transcript/captions from a YouTube video.  **Rate Limits:** Build (50/day), Accelerate (500/day), Unlimited (unlimited) 

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
    public class GetYouTubeTranscriptExample
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
            var apiInstance = new ToolsApi(httpClient, config, httpClientHandler);
            var url = "url_example";  // string | YouTube video URL or video ID
            var lang = "\"en\"";  // string? | Language code for transcript (optional)  (default to "en")

            try
            {
                // Get YouTube transcript
                GetYouTubeTranscript200Response result = apiInstance.GetYouTubeTranscript(url, lang);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling ToolsApi.GetYouTubeTranscript: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the GetYouTubeTranscriptWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Get YouTube transcript
    ApiResponse<GetYouTubeTranscript200Response> response = apiInstance.GetYouTubeTranscriptWithHttpInfo(url, lang);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling ToolsApi.GetYouTubeTranscriptWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **url** | **string** | YouTube video URL or video ID |  |
| **lang** | **string?** | Language code for transcript | [optional] [default to &quot;en&quot;] |

### Return type

[**GetYouTubeTranscript200Response**](GetYouTubeTranscript200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Success |  -  |
| **404** | No transcript available |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

