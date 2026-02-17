# Late.Api.GMBMediaApi

All URIs are relative to *https://getlate.dev/api*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**CreateGoogleBusinessMedia**](GMBMediaApi.md#creategooglebusinessmedia) | **POST** /v1/accounts/{accountId}/gmb-media | Upload photo |
| [**DeleteGoogleBusinessMedia**](GMBMediaApi.md#deletegooglebusinessmedia) | **DELETE** /v1/accounts/{accountId}/gmb-media | Delete photo |
| [**ListGoogleBusinessMedia**](GMBMediaApi.md#listgooglebusinessmedia) | **GET** /v1/accounts/{accountId}/gmb-media | List media |

<a id="creategooglebusinessmedia"></a>
# **CreateGoogleBusinessMedia**
> CreateGoogleBusinessMedia200Response CreateGoogleBusinessMedia (string accountId, CreateGoogleBusinessMediaRequest createGoogleBusinessMediaRequest)

Upload photo

Creates a media item (photo) for a location from a publicly accessible URL.  Categories determine where the photo appears: COVER, PROFILE, LOGO, EXTERIOR, INTERIOR, FOOD_AND_DRINK, MENU, PRODUCT, TEAMS, ADDITIONAL. 

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
    public class CreateGoogleBusinessMediaExample
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
            var apiInstance = new GMBMediaApi(httpClient, config, httpClientHandler);
            var accountId = "accountId_example";  // string | 
            var createGoogleBusinessMediaRequest = new CreateGoogleBusinessMediaRequest(); // CreateGoogleBusinessMediaRequest | 

            try
            {
                // Upload photo
                CreateGoogleBusinessMedia200Response result = apiInstance.CreateGoogleBusinessMedia(accountId, createGoogleBusinessMediaRequest);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling GMBMediaApi.CreateGoogleBusinessMedia: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the CreateGoogleBusinessMediaWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Upload photo
    ApiResponse<CreateGoogleBusinessMedia200Response> response = apiInstance.CreateGoogleBusinessMediaWithHttpInfo(accountId, createGoogleBusinessMediaRequest);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling GMBMediaApi.CreateGoogleBusinessMediaWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **accountId** | **string** |  |  |
| **createGoogleBusinessMediaRequest** | [**CreateGoogleBusinessMediaRequest**](CreateGoogleBusinessMediaRequest.md) |  |  |

### Return type

[**CreateGoogleBusinessMedia200Response**](CreateGoogleBusinessMedia200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Media created successfully |  -  |
| **400** | Invalid request or unsupported media format |  -  |
| **401** | Unauthorized |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="deletegooglebusinessmedia"></a>
# **DeleteGoogleBusinessMedia**
> DeleteGoogleBusinessMedia200Response DeleteGoogleBusinessMedia (string accountId, string mediaId)

Delete photo

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
    public class DeleteGoogleBusinessMediaExample
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
            var apiInstance = new GMBMediaApi(httpClient, config, httpClientHandler);
            var accountId = "accountId_example";  // string | 
            var mediaId = "mediaId_example";  // string | The media item ID to delete

            try
            {
                // Delete photo
                DeleteGoogleBusinessMedia200Response result = apiInstance.DeleteGoogleBusinessMedia(accountId, mediaId);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling GMBMediaApi.DeleteGoogleBusinessMedia: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the DeleteGoogleBusinessMediaWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Delete photo
    ApiResponse<DeleteGoogleBusinessMedia200Response> response = apiInstance.DeleteGoogleBusinessMediaWithHttpInfo(accountId, mediaId);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling GMBMediaApi.DeleteGoogleBusinessMediaWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **accountId** | **string** |  |  |
| **mediaId** | **string** | The media item ID to delete |  |

### Return type

[**DeleteGoogleBusinessMedia200Response**](DeleteGoogleBusinessMedia200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Media deleted successfully |  -  |
| **400** | Invalid request |  -  |
| **401** | Unauthorized |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="listgooglebusinessmedia"></a>
# **ListGoogleBusinessMedia**
> ListGoogleBusinessMedia200Response ListGoogleBusinessMedia (string accountId, int? pageSize = null, string? pageToken = null)

List media

Lists media items (photos) for a Google Business Profile location. Returns photo URLs, descriptions, categories, and metadata. 

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
    public class ListGoogleBusinessMediaExample
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
            var apiInstance = new GMBMediaApi(httpClient, config, httpClientHandler);
            var accountId = "accountId_example";  // string | 
            var pageSize = 100;  // int? | Number of items to return (max 100) (optional)  (default to 100)
            var pageToken = "pageToken_example";  // string? | Pagination token from previous response (optional) 

            try
            {
                // List media
                ListGoogleBusinessMedia200Response result = apiInstance.ListGoogleBusinessMedia(accountId, pageSize, pageToken);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling GMBMediaApi.ListGoogleBusinessMedia: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the ListGoogleBusinessMediaWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // List media
    ApiResponse<ListGoogleBusinessMedia200Response> response = apiInstance.ListGoogleBusinessMediaWithHttpInfo(accountId, pageSize, pageToken);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling GMBMediaApi.ListGoogleBusinessMediaWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **accountId** | **string** |  |  |
| **pageSize** | **int?** | Number of items to return (max 100) | [optional] [default to 100] |
| **pageToken** | **string?** | Pagination token from previous response | [optional]  |

### Return type

[**ListGoogleBusinessMedia200Response**](ListGoogleBusinessMedia200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Media items fetched successfully |  -  |
| **400** | Invalid request |  -  |
| **401** | Unauthorized |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

