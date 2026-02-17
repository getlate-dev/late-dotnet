# Late.Api.MediaApi

All URIs are relative to *https://getlate.dev/api*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**GetMediaPresignedUrl**](MediaApi.md#getmediapresignedurl) | **POST** /v1/media/presign | Get presigned upload URL |

<a id="getmediapresignedurl"></a>
# **GetMediaPresignedUrl**
> GetMediaPresignedUrl200Response GetMediaPresignedUrl (GetMediaPresignedUrlRequest getMediaPresignedUrlRequest)

Get presigned upload URL

Get a presigned URL to upload files directly to cloud storage. Supports files up to 5GB.  **How it works:** 1. Call this endpoint with the filename and content type 2. Receive an `uploadUrl` (presigned) and `publicUrl` 3. PUT your file directly to the `uploadUrl` 4. Use the `publicUrl` in your posts 

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
    public class GetMediaPresignedUrlExample
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
            var apiInstance = new MediaApi(httpClient, config, httpClientHandler);
            var getMediaPresignedUrlRequest = new GetMediaPresignedUrlRequest(); // GetMediaPresignedUrlRequest | 

            try
            {
                // Get presigned upload URL
                GetMediaPresignedUrl200Response result = apiInstance.GetMediaPresignedUrl(getMediaPresignedUrlRequest);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling MediaApi.GetMediaPresignedUrl: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the GetMediaPresignedUrlWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Get presigned upload URL
    ApiResponse<GetMediaPresignedUrl200Response> response = apiInstance.GetMediaPresignedUrlWithHttpInfo(getMediaPresignedUrlRequest);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling MediaApi.GetMediaPresignedUrlWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **getMediaPresignedUrlRequest** | [**GetMediaPresignedUrlRequest**](GetMediaPresignedUrlRequest.md) |  |  |

### Return type

[**GetMediaPresignedUrl200Response**](GetMediaPresignedUrl200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Presigned URL generated successfully |  -  |
| **400** | Invalid request (missing filename, contentType, or unsupported content type) |  -  |
| **401** | Unauthorized |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

