# Late.Api.GMBAttributesApi

All URIs are relative to *https://getlate.dev/api*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**GetGoogleBusinessAttributes**](GMBAttributesApi.md#getgooglebusinessattributes) | **GET** /v1/accounts/{accountId}/gmb-attributes | Get attributes |
| [**UpdateGoogleBusinessAttributes**](GMBAttributesApi.md#updategooglebusinessattributes) | **PUT** /v1/accounts/{accountId}/gmb-attributes | Update attributes |

<a id="getgooglebusinessattributes"></a>
# **GetGoogleBusinessAttributes**
> GetGoogleBusinessAttributes200Response GetGoogleBusinessAttributes (string accountId)

Get attributes

Returns GBP location attributes (amenities, services, accessibility, payment types). Available attributes vary by business category.

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
    public class GetGoogleBusinessAttributesExample
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
            var apiInstance = new GMBAttributesApi(httpClient, config, httpClientHandler);
            var accountId = "accountId_example";  // string | 

            try
            {
                // Get attributes
                GetGoogleBusinessAttributes200Response result = apiInstance.GetGoogleBusinessAttributes(accountId);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling GMBAttributesApi.GetGoogleBusinessAttributes: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the GetGoogleBusinessAttributesWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Get attributes
    ApiResponse<GetGoogleBusinessAttributes200Response> response = apiInstance.GetGoogleBusinessAttributesWithHttpInfo(accountId);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling GMBAttributesApi.GetGoogleBusinessAttributesWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **accountId** | **string** |  |  |

### Return type

[**GetGoogleBusinessAttributes200Response**](GetGoogleBusinessAttributes200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Attributes fetched successfully |  -  |
| **400** | Invalid request |  -  |
| **401** | Unauthorized |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="updategooglebusinessattributes"></a>
# **UpdateGoogleBusinessAttributes**
> UpdateGoogleBusinessAttributes200Response UpdateGoogleBusinessAttributes (string accountId, UpdateGoogleBusinessAttributesRequest updateGoogleBusinessAttributesRequest)

Update attributes

Updates location attributes (amenities, services, etc.).  The attributeMask specifies which attributes to update (comma-separated). 

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
    public class UpdateGoogleBusinessAttributesExample
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
            var apiInstance = new GMBAttributesApi(httpClient, config, httpClientHandler);
            var accountId = "accountId_example";  // string | 
            var updateGoogleBusinessAttributesRequest = new UpdateGoogleBusinessAttributesRequest(); // UpdateGoogleBusinessAttributesRequest | 

            try
            {
                // Update attributes
                UpdateGoogleBusinessAttributes200Response result = apiInstance.UpdateGoogleBusinessAttributes(accountId, updateGoogleBusinessAttributesRequest);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling GMBAttributesApi.UpdateGoogleBusinessAttributes: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the UpdateGoogleBusinessAttributesWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Update attributes
    ApiResponse<UpdateGoogleBusinessAttributes200Response> response = apiInstance.UpdateGoogleBusinessAttributesWithHttpInfo(accountId, updateGoogleBusinessAttributesRequest);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling GMBAttributesApi.UpdateGoogleBusinessAttributesWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **accountId** | **string** |  |  |
| **updateGoogleBusinessAttributesRequest** | [**UpdateGoogleBusinessAttributesRequest**](UpdateGoogleBusinessAttributesRequest.md) |  |  |

### Return type

[**UpdateGoogleBusinessAttributes200Response**](UpdateGoogleBusinessAttributes200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Attributes updated successfully |  -  |
| **400** | Invalid request |  -  |
| **401** | Unauthorized |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

