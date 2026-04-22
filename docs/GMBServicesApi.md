# Zernio.Api.GMBServicesApi

All URIs are relative to *https://zernio.com/api*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**GetGoogleBusinessServices**](GMBServicesApi.md#getgooglebusinessservices) | **GET** /v1/accounts/{accountId}/gmb-services | Get services |
| [**UpdateGoogleBusinessServices**](GMBServicesApi.md#updategooglebusinessservices) | **PUT** /v1/accounts/{accountId}/gmb-services | Replace services |

<a id="getgooglebusinessservices"></a>
# **GetGoogleBusinessServices**
> GetGoogleBusinessServices200Response GetGoogleBusinessServices (string accountId, string? locationId = null)

Get services

Gets the services offered by a Google Business Profile location. Returns an array of service items (structured or free-form with optional price). 

### Example
```csharp
using System.Collections.Generic;
using System.Diagnostics;
using System.Net.Http;
using Zernio.Api;
using Zernio.Client;
using Zernio.Model;

namespace Example
{
    public class GetGoogleBusinessServicesExample
    {
        public static void Main()
        {
            Configuration config = new Configuration();
            config.BasePath = "https://zernio.com/api";
            // Configure Bearer token for authorization: bearerAuth
            config.AccessToken = "YOUR_BEARER_TOKEN";

            // create instances of HttpClient, HttpClientHandler to be reused later with different Api classes
            HttpClient httpClient = new HttpClient();
            HttpClientHandler httpClientHandler = new HttpClientHandler();
            var apiInstance = new GMBServicesApi(httpClient, config, httpClientHandler);
            var accountId = "accountId_example";  // string | 
            var locationId = "locationId_example";  // string? | Override which location to query. If omitted, uses the account's selected location. (optional) 

            try
            {
                // Get services
                GetGoogleBusinessServices200Response result = apiInstance.GetGoogleBusinessServices(accountId, locationId);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling GMBServicesApi.GetGoogleBusinessServices: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the GetGoogleBusinessServicesWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Get services
    ApiResponse<GetGoogleBusinessServices200Response> response = apiInstance.GetGoogleBusinessServicesWithHttpInfo(accountId, locationId);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling GMBServicesApi.GetGoogleBusinessServicesWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **accountId** | **string** |  |  |
| **locationId** | **string?** | Override which location to query. If omitted, uses the account&#39;s selected location. | [optional]  |

### Return type

[**GetGoogleBusinessServices200Response**](GetGoogleBusinessServices200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Services fetched successfully |  -  |
| **401** | Unauthorized |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="updategooglebusinessservices"></a>
# **UpdateGoogleBusinessServices**
> UpdateGoogleBusinessServices200Response UpdateGoogleBusinessServices (string accountId, UpdateGoogleBusinessServicesRequest updateGoogleBusinessServicesRequest, string? locationId = null)

Replace services

Replaces the entire service list for a location. Google's API requires full replacement; individual item updates are not supported. Each service can be structured (using a predefined serviceTypeId) or free-form (custom label). 

### Example
```csharp
using System.Collections.Generic;
using System.Diagnostics;
using System.Net.Http;
using Zernio.Api;
using Zernio.Client;
using Zernio.Model;

namespace Example
{
    public class UpdateGoogleBusinessServicesExample
    {
        public static void Main()
        {
            Configuration config = new Configuration();
            config.BasePath = "https://zernio.com/api";
            // Configure Bearer token for authorization: bearerAuth
            config.AccessToken = "YOUR_BEARER_TOKEN";

            // create instances of HttpClient, HttpClientHandler to be reused later with different Api classes
            HttpClient httpClient = new HttpClient();
            HttpClientHandler httpClientHandler = new HttpClientHandler();
            var apiInstance = new GMBServicesApi(httpClient, config, httpClientHandler);
            var accountId = "accountId_example";  // string | 
            var updateGoogleBusinessServicesRequest = new UpdateGoogleBusinessServicesRequest(); // UpdateGoogleBusinessServicesRequest | 
            var locationId = "locationId_example";  // string? | Override which location to target. If omitted, uses the account's selected location. (optional) 

            try
            {
                // Replace services
                UpdateGoogleBusinessServices200Response result = apiInstance.UpdateGoogleBusinessServices(accountId, updateGoogleBusinessServicesRequest, locationId);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling GMBServicesApi.UpdateGoogleBusinessServices: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the UpdateGoogleBusinessServicesWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Replace services
    ApiResponse<UpdateGoogleBusinessServices200Response> response = apiInstance.UpdateGoogleBusinessServicesWithHttpInfo(accountId, updateGoogleBusinessServicesRequest, locationId);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling GMBServicesApi.UpdateGoogleBusinessServicesWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **accountId** | **string** |  |  |
| **updateGoogleBusinessServicesRequest** | [**UpdateGoogleBusinessServicesRequest**](UpdateGoogleBusinessServicesRequest.md) |  |  |
| **locationId** | **string?** | Override which location to target. If omitted, uses the account&#39;s selected location. | [optional]  |

### Return type

[**UpdateGoogleBusinessServices200Response**](UpdateGoogleBusinessServices200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Services updated successfully |  -  |
| **400** | Invalid request |  -  |
| **401** | Unauthorized |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

