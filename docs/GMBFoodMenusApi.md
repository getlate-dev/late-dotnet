# Late.Api.GMBFoodMenusApi

All URIs are relative to *https://getlate.dev/api*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**GetGoogleBusinessFoodMenus**](GMBFoodMenusApi.md#getgooglebusinessfoodmenus) | **GET** /v1/accounts/{accountId}/gmb-food-menus | Get Google Business Profile food menus |
| [**UpdateGoogleBusinessFoodMenus**](GMBFoodMenusApi.md#updategooglebusinessfoodmenus) | **PUT** /v1/accounts/{accountId}/gmb-food-menus | Update Google Business Profile food menus |

<a id="getgooglebusinessfoodmenus"></a>
# **GetGoogleBusinessFoodMenus**
> GetGoogleBusinessFoodMenus200Response GetGoogleBusinessFoodMenus (string accountId)

Get Google Business Profile food menus

Fetches food menus for a connected Google Business Profile location.  Returns the full menu structure including: - Menu names and descriptions - Sections (e.g. Appetizers, Entrees, Drinks) - Items with labels, pricing, dietary info, and allergens - Item options/variants  Only available for locations with food menu support (restaurants, cafes, etc.). 

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
    public class GetGoogleBusinessFoodMenusExample
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
            var apiInstance = new GMBFoodMenusApi(httpClient, config, httpClientHandler);
            var accountId = "accountId_example";  // string | The Late account ID (from /v1/accounts)

            try
            {
                // Get Google Business Profile food menus
                GetGoogleBusinessFoodMenus200Response result = apiInstance.GetGoogleBusinessFoodMenus(accountId);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling GMBFoodMenusApi.GetGoogleBusinessFoodMenus: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the GetGoogleBusinessFoodMenusWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Get Google Business Profile food menus
    ApiResponse<GetGoogleBusinessFoodMenus200Response> response = apiInstance.GetGoogleBusinessFoodMenusWithHttpInfo(accountId);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling GMBFoodMenusApi.GetGoogleBusinessFoodMenusWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **accountId** | **string** | The Late account ID (from /v1/accounts) |  |

### Return type

[**GetGoogleBusinessFoodMenus200Response**](GetGoogleBusinessFoodMenus200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Food menus fetched successfully |  -  |
| **400** | Invalid request - not a Google Business account or missing location |  -  |
| **401** | Unauthorized or token expired |  -  |
| **403** | Permission denied for this location |  -  |
| **404** | Resource not found |  -  |
| **500** | Failed to fetch food menus |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="updategooglebusinessfoodmenus"></a>
# **UpdateGoogleBusinessFoodMenus**
> UpdateGoogleBusinessFoodMenus200Response UpdateGoogleBusinessFoodMenus (string accountId, UpdateGoogleBusinessFoodMenusRequest updateGoogleBusinessFoodMenusRequest)

Update Google Business Profile food menus

Updates the food menus for a connected Google Business Profile location.  Send the full menus array. Use `updateMask` for partial updates (e.g. `\"menus\"` to only update the menus field).  Each menu can contain sections, and each section can contain items with pricing, dietary restrictions, allergens, and more. 

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
    public class UpdateGoogleBusinessFoodMenusExample
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
            var apiInstance = new GMBFoodMenusApi(httpClient, config, httpClientHandler);
            var accountId = "accountId_example";  // string | The Late account ID (from /v1/accounts)
            var updateGoogleBusinessFoodMenusRequest = new UpdateGoogleBusinessFoodMenusRequest(); // UpdateGoogleBusinessFoodMenusRequest | 

            try
            {
                // Update Google Business Profile food menus
                UpdateGoogleBusinessFoodMenus200Response result = apiInstance.UpdateGoogleBusinessFoodMenus(accountId, updateGoogleBusinessFoodMenusRequest);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling GMBFoodMenusApi.UpdateGoogleBusinessFoodMenus: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the UpdateGoogleBusinessFoodMenusWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Update Google Business Profile food menus
    ApiResponse<UpdateGoogleBusinessFoodMenus200Response> response = apiInstance.UpdateGoogleBusinessFoodMenusWithHttpInfo(accountId, updateGoogleBusinessFoodMenusRequest);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling GMBFoodMenusApi.UpdateGoogleBusinessFoodMenusWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **accountId** | **string** | The Late account ID (from /v1/accounts) |  |
| **updateGoogleBusinessFoodMenusRequest** | [**UpdateGoogleBusinessFoodMenusRequest**](UpdateGoogleBusinessFoodMenusRequest.md) |  |  |

### Return type

[**UpdateGoogleBusinessFoodMenus200Response**](UpdateGoogleBusinessFoodMenus200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Food menus updated successfully |  -  |
| **400** | Invalid request |  -  |
| **401** | Unauthorized or token expired |  -  |
| **403** | Permission denied for this location |  -  |
| **404** | Resource not found |  -  |
| **500** | Failed to update food menus |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

