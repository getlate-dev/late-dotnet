# Late.Api.GMBPlaceActionsApi

All URIs are relative to *https://getlate.dev/api*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**CreateGoogleBusinessPlaceAction**](GMBPlaceActionsApi.md#creategooglebusinessplaceaction) | **POST** /v1/accounts/{accountId}/gmb-place-actions | Create a place action link (booking, ordering, reservation) |
| [**DeleteGoogleBusinessPlaceAction**](GMBPlaceActionsApi.md#deletegooglebusinessplaceaction) | **DELETE** /v1/accounts/{accountId}/gmb-place-actions | Delete a place action link |
| [**ListGoogleBusinessPlaceActions**](GMBPlaceActionsApi.md#listgooglebusinessplaceactions) | **GET** /v1/accounts/{accountId}/gmb-place-actions | List place action links (booking, ordering, reservations) |

<a id="creategooglebusinessplaceaction"></a>
# **CreateGoogleBusinessPlaceAction**
> CreateGoogleBusinessPlaceAction200Response CreateGoogleBusinessPlaceAction (string accountId, CreateGoogleBusinessPlaceActionRequest createGoogleBusinessPlaceActionRequest)

Create a place action link (booking, ordering, reservation)

Creates a place action link for a location.  Available action types: - `APPOINTMENT` - Booking an appointment - `ONLINE_APPOINTMENT` - Booking an online appointment - `DINING_RESERVATION` - Making a dining reservation (OpenTable, Resy, etc.) - `FOOD_ORDERING` - Ordering food for delivery and/or takeout (DoorDash, Uber Eats, etc.) - `FOOD_DELIVERY` - Ordering food for delivery only - `FOOD_TAKEOUT` - Ordering food for takeout only - `SHOP_ONLINE` - Shopping with delivery and/or pickup 

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
    public class CreateGoogleBusinessPlaceActionExample
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
            var apiInstance = new GMBPlaceActionsApi(httpClient, config, httpClientHandler);
            var accountId = "accountId_example";  // string | 
            var createGoogleBusinessPlaceActionRequest = new CreateGoogleBusinessPlaceActionRequest(); // CreateGoogleBusinessPlaceActionRequest | 

            try
            {
                // Create a place action link (booking, ordering, reservation)
                CreateGoogleBusinessPlaceAction200Response result = apiInstance.CreateGoogleBusinessPlaceAction(accountId, createGoogleBusinessPlaceActionRequest);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling GMBPlaceActionsApi.CreateGoogleBusinessPlaceAction: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the CreateGoogleBusinessPlaceActionWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Create a place action link (booking, ordering, reservation)
    ApiResponse<CreateGoogleBusinessPlaceAction200Response> response = apiInstance.CreateGoogleBusinessPlaceActionWithHttpInfo(accountId, createGoogleBusinessPlaceActionRequest);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling GMBPlaceActionsApi.CreateGoogleBusinessPlaceActionWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **accountId** | **string** |  |  |
| **createGoogleBusinessPlaceActionRequest** | [**CreateGoogleBusinessPlaceActionRequest**](CreateGoogleBusinessPlaceActionRequest.md) |  |  |

### Return type

[**CreateGoogleBusinessPlaceAction200Response**](CreateGoogleBusinessPlaceAction200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Place action created successfully |  -  |
| **400** | Invalid request |  -  |
| **401** | Unauthorized |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="deletegooglebusinessplaceaction"></a>
# **DeleteGoogleBusinessPlaceAction**
> DeleteGoogleBusinessPlaceAction200Response DeleteGoogleBusinessPlaceAction (string accountId, string name)

Delete a place action link

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
    public class DeleteGoogleBusinessPlaceActionExample
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
            var apiInstance = new GMBPlaceActionsApi(httpClient, config, httpClientHandler);
            var accountId = "accountId_example";  // string | 
            var name = "name_example";  // string | The resource name of the place action link (e.g. locations/123/placeActionLinks/456)

            try
            {
                // Delete a place action link
                DeleteGoogleBusinessPlaceAction200Response result = apiInstance.DeleteGoogleBusinessPlaceAction(accountId, name);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling GMBPlaceActionsApi.DeleteGoogleBusinessPlaceAction: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the DeleteGoogleBusinessPlaceActionWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Delete a place action link
    ApiResponse<DeleteGoogleBusinessPlaceAction200Response> response = apiInstance.DeleteGoogleBusinessPlaceActionWithHttpInfo(accountId, name);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling GMBPlaceActionsApi.DeleteGoogleBusinessPlaceActionWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **accountId** | **string** |  |  |
| **name** | **string** | The resource name of the place action link (e.g. locations/123/placeActionLinks/456) |  |

### Return type

[**DeleteGoogleBusinessPlaceAction200Response**](DeleteGoogleBusinessPlaceAction200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Place action deleted successfully |  -  |
| **400** | Invalid request |  -  |
| **401** | Unauthorized |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="listgooglebusinessplaceactions"></a>
# **ListGoogleBusinessPlaceActions**
> ListGoogleBusinessPlaceActions200Response ListGoogleBusinessPlaceActions (string accountId, int? pageSize = null, string? pageToken = null)

List place action links (booking, ordering, reservations)

Lists place action links for a Google Business Profile location.  Place actions are the booking, ordering, and reservation buttons that appear on your listing. 

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
    public class ListGoogleBusinessPlaceActionsExample
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
            var apiInstance = new GMBPlaceActionsApi(httpClient, config, httpClientHandler);
            var accountId = "accountId_example";  // string | 
            var pageSize = 100;  // int? |  (optional)  (default to 100)
            var pageToken = "pageToken_example";  // string? |  (optional) 

            try
            {
                // List place action links (booking, ordering, reservations)
                ListGoogleBusinessPlaceActions200Response result = apiInstance.ListGoogleBusinessPlaceActions(accountId, pageSize, pageToken);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling GMBPlaceActionsApi.ListGoogleBusinessPlaceActions: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the ListGoogleBusinessPlaceActionsWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // List place action links (booking, ordering, reservations)
    ApiResponse<ListGoogleBusinessPlaceActions200Response> response = apiInstance.ListGoogleBusinessPlaceActionsWithHttpInfo(accountId, pageSize, pageToken);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling GMBPlaceActionsApi.ListGoogleBusinessPlaceActionsWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **accountId** | **string** |  |  |
| **pageSize** | **int?** |  | [optional] [default to 100] |
| **pageToken** | **string?** |  | [optional]  |

### Return type

[**ListGoogleBusinessPlaceActions200Response**](ListGoogleBusinessPlaceActions200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Place actions fetched successfully |  -  |
| **400** | Invalid request |  -  |
| **401** | Unauthorized |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

