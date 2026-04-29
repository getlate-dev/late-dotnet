# Zernio.Api.GMBLocationDetailsApi

All URIs are relative to *https://zernio.com/api*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**GetGoogleBusinessLocationDetails**](GMBLocationDetailsApi.md#getgooglebusinesslocationdetails) | **GET** /v1/accounts/{accountId}/gmb-location-details | Get location details |
| [**UpdateGoogleBusinessLocationDetails**](GMBLocationDetailsApi.md#updategooglebusinesslocationdetails) | **PUT** /v1/accounts/{accountId}/gmb-location-details | Update location details |

<a id="getgooglebusinesslocationdetails"></a>
# **GetGoogleBusinessLocationDetails**
> GetGoogleBusinessLocationDetails200Response GetGoogleBusinessLocationDetails (string accountId, string? locationId = null, string? readMask = null)

Get location details

Returns detailed GBP location info (hours, description, phone, website, categories, services). Use readMask to request specific fields.

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
    public class GetGoogleBusinessLocationDetailsExample
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
            var apiInstance = new GMBLocationDetailsApi(httpClient, config, httpClientHandler);
            var accountId = "accountId_example";  // string | The Zernio account ID (from /v1/accounts)
            var locationId = "locationId_example";  // string? | Override which location to query. If omitted, uses the account's selected location. Use GET /gmb-locations to list valid IDs. (optional) 
            var readMask = "readMask_example";  // string? | Comma-separated fields to return. Available: name, title, phoneNumbers, categories, storefrontAddress, websiteUri, regularHours, specialHours, serviceArea, serviceItems, profile, openInfo, metadata, moreHours. `title` and `metadata` are always included in the response so the `location` summary block can be populated, even if you omit them here. Note: `location` is a derived response field, not a Google readMask value, passing it returns 400.  (optional) 

            try
            {
                // Get location details
                GetGoogleBusinessLocationDetails200Response result = apiInstance.GetGoogleBusinessLocationDetails(accountId, locationId, readMask);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling GMBLocationDetailsApi.GetGoogleBusinessLocationDetails: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the GetGoogleBusinessLocationDetailsWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Get location details
    ApiResponse<GetGoogleBusinessLocationDetails200Response> response = apiInstance.GetGoogleBusinessLocationDetailsWithHttpInfo(accountId, locationId, readMask);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling GMBLocationDetailsApi.GetGoogleBusinessLocationDetailsWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **accountId** | **string** | The Zernio account ID (from /v1/accounts) |  |
| **locationId** | **string?** | Override which location to query. If omitted, uses the account&#39;s selected location. Use GET /gmb-locations to list valid IDs. | [optional]  |
| **readMask** | **string?** | Comma-separated fields to return. Available: name, title, phoneNumbers, categories, storefrontAddress, websiteUri, regularHours, specialHours, serviceArea, serviceItems, profile, openInfo, metadata, moreHours. &#x60;title&#x60; and &#x60;metadata&#x60; are always included in the response so the &#x60;location&#x60; summary block can be populated, even if you omit them here. Note: &#x60;location&#x60; is a derived response field, not a Google readMask value, passing it returns 400.  | [optional]  |

### Return type

[**GetGoogleBusinessLocationDetails200Response**](GetGoogleBusinessLocationDetails200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Location details fetched successfully |  -  |
| **400** | Invalid request. Most commonly raised when the readMask query includes a value that is not a valid Google Business Information field (e.g. &#x60;location&#x60;, which is a response-only derived field).  |  -  |
| **401** | Unauthorized or token expired |  -  |
| **404** | Resource not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="updategooglebusinesslocationdetails"></a>
# **UpdateGoogleBusinessLocationDetails**
> UpdateGoogleBusinessLocationDetails200Response UpdateGoogleBusinessLocationDetails (string accountId, UpdateGoogleBusinessLocationDetailsRequest updateGoogleBusinessLocationDetailsRequest, string? locationId = null)

Update location details

Updates GBP location details. The updateMask field is required and specifies which fields to update. This endpoint proxies Google's Business Information API locations.patch, so any valid updateMask field is supported. Common fields: regularHours, specialHours, profile.description, websiteUri, phoneNumbers, categories, serviceItems. 

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
    public class UpdateGoogleBusinessLocationDetailsExample
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
            var apiInstance = new GMBLocationDetailsApi(httpClient, config, httpClientHandler);
            var accountId = "accountId_example";  // string | The Zernio account ID (from /v1/accounts)
            var updateGoogleBusinessLocationDetailsRequest = new UpdateGoogleBusinessLocationDetailsRequest(); // UpdateGoogleBusinessLocationDetailsRequest | 
            var locationId = "locationId_example";  // string? | Override which location to target. If omitted, uses the account's selected location. Use GET /gmb-locations to list valid IDs. (optional) 

            try
            {
                // Update location details
                UpdateGoogleBusinessLocationDetails200Response result = apiInstance.UpdateGoogleBusinessLocationDetails(accountId, updateGoogleBusinessLocationDetailsRequest, locationId);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling GMBLocationDetailsApi.UpdateGoogleBusinessLocationDetails: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the UpdateGoogleBusinessLocationDetailsWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Update location details
    ApiResponse<UpdateGoogleBusinessLocationDetails200Response> response = apiInstance.UpdateGoogleBusinessLocationDetailsWithHttpInfo(accountId, updateGoogleBusinessLocationDetailsRequest, locationId);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling GMBLocationDetailsApi.UpdateGoogleBusinessLocationDetailsWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **accountId** | **string** | The Zernio account ID (from /v1/accounts) |  |
| **updateGoogleBusinessLocationDetailsRequest** | [**UpdateGoogleBusinessLocationDetailsRequest**](UpdateGoogleBusinessLocationDetailsRequest.md) |  |  |
| **locationId** | **string?** | Override which location to target. If omitted, uses the account&#39;s selected location. Use GET /gmb-locations to list valid IDs. | [optional]  |

### Return type

[**UpdateGoogleBusinessLocationDetails200Response**](UpdateGoogleBusinessLocationDetails200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Location updated successfully |  -  |
| **400** | Invalid request or missing updateMask |  -  |
| **401** | Unauthorized or token expired |  -  |
| **404** | Resource not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

