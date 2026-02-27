# Late.Api.ValidateApi

All URIs are relative to *https://getlate.dev/api*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**ValidateMedia**](ValidateApi.md#validatemedia) | **POST** /v1/tools/validate/media | Validate media URL |
| [**ValidatePost**](ValidateApi.md#validatepost) | **POST** /v1/tools/validate/post | Validate post content |
| [**ValidatePostLength**](ValidateApi.md#validatepostlength) | **POST** /v1/tools/validate/post-length | Validate post character count |
| [**ValidateSubreddit**](ValidateApi.md#validatesubreddit) | **GET** /v1/tools/validate/subreddit | Check subreddit existence |

<a id="validatemedia"></a>
# **ValidateMedia**
> ValidateMedia200Response ValidateMedia (ValidateMediaRequest validateMediaRequest)

Validate media URL

Check if a media URL is accessible and return metadata (content type, file size) plus per-platform size limit comparisons.  Performs a HEAD request (with GET fallback) to detect content type and size. Rejects private/localhost URLs for SSRF protection.  Platform limits are sourced from each platform's actual upload constraints. 

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
    public class ValidateMediaExample
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
            var apiInstance = new ValidateApi(httpClient, config, httpClientHandler);
            var validateMediaRequest = new ValidateMediaRequest(); // ValidateMediaRequest | 

            try
            {
                // Validate media URL
                ValidateMedia200Response result = apiInstance.ValidateMedia(validateMediaRequest);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling ValidateApi.ValidateMedia: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the ValidateMediaWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Validate media URL
    ApiResponse<ValidateMedia200Response> response = apiInstance.ValidateMediaWithHttpInfo(validateMediaRequest);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling ValidateApi.ValidateMediaWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **validateMediaRequest** | [**ValidateMediaRequest**](ValidateMediaRequest.md) |  |  |

### Return type

[**ValidateMedia200Response**](ValidateMedia200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Media validation result |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="validatepost"></a>
# **ValidatePost**
> ValidatePost200Response ValidatePost (ValidatePostRequest validatePostRequest)

Validate post content

Dry-run the full post validation pipeline without publishing. Catches issues like missing media for Instagram/TikTok/YouTube, hashtag limits, invalid thread formats, Facebook Reel requirements, and character limit violations.  Accepts the same body as `POST /v1/posts`. Does NOT validate accounts, process media, or track usage. This is content-only validation.  Returns errors for failures and warnings for near-limit content (>90% of character limit). 

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
    public class ValidatePostExample
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
            var apiInstance = new ValidateApi(httpClient, config, httpClientHandler);
            var validatePostRequest = new ValidatePostRequest(); // ValidatePostRequest | 

            try
            {
                // Validate post content
                ValidatePost200Response result = apiInstance.ValidatePost(validatePostRequest);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling ValidateApi.ValidatePost: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the ValidatePostWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Validate post content
    ApiResponse<ValidatePost200Response> response = apiInstance.ValidatePostWithHttpInfo(validatePostRequest);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling ValidateApi.ValidatePostWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **validatePostRequest** | [**ValidatePostRequest**](ValidatePostRequest.md) |  |  |

### Return type

[**ValidatePost200Response**](ValidatePost200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Validation result |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="validatepostlength"></a>
# **ValidatePostLength**
> ValidatePostLength200Response ValidatePostLength (ValidatePostLengthRequest validatePostLengthRequest)

Validate post character count

Check weighted character count per platform and whether the text is within each platform's limit.  Twitter/X uses weighted counting (URLs = 23 chars via t.co, emojis = 2 chars). All other platforms use plain character length.  Returns counts and limits for all 15 supported platform variants. 

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
    public class ValidatePostLengthExample
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
            var apiInstance = new ValidateApi(httpClient, config, httpClientHandler);
            var validatePostLengthRequest = new ValidatePostLengthRequest(); // ValidatePostLengthRequest | 

            try
            {
                // Validate post character count
                ValidatePostLength200Response result = apiInstance.ValidatePostLength(validatePostLengthRequest);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling ValidateApi.ValidatePostLength: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the ValidatePostLengthWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Validate post character count
    ApiResponse<ValidatePostLength200Response> response = apiInstance.ValidatePostLengthWithHttpInfo(validatePostLengthRequest);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling ValidateApi.ValidatePostLengthWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **validatePostLengthRequest** | [**ValidatePostLengthRequest**](ValidatePostLengthRequest.md) |  |  |

### Return type

[**ValidatePostLength200Response**](ValidatePostLength200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Character counts per platform |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="validatesubreddit"></a>
# **ValidateSubreddit**
> ValidateSubreddit200Response ValidateSubreddit (string name)

Check subreddit existence

Check if a subreddit exists and return basic info (title, subscriber count, NSFW status, post types allowed).  Uses Reddit's public JSON API (no Reddit auth needed). Returns `exists: false` for private, banned, or nonexistent subreddits. 

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
    public class ValidateSubredditExample
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
            var apiInstance = new ValidateApi(httpClient, config, httpClientHandler);
            var name = programming;  // string | Subreddit name (with or without \"r/\" prefix)

            try
            {
                // Check subreddit existence
                ValidateSubreddit200Response result = apiInstance.ValidateSubreddit(name);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling ValidateApi.ValidateSubreddit: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the ValidateSubredditWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Check subreddit existence
    ApiResponse<ValidateSubreddit200Response> response = apiInstance.ValidateSubredditWithHttpInfo(name);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling ValidateApi.ValidateSubredditWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **name** | **string** | Subreddit name (with or without \&quot;r/\&quot; prefix) |  |

### Return type

[**ValidateSubreddit200Response**](ValidateSubreddit200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Subreddit lookup result |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

