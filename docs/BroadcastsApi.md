# Late.Api.BroadcastsApi

All URIs are relative to *https://zernio.com/api*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**AddBroadcastRecipients**](BroadcastsApi.md#addbroadcastrecipients) | **POST** /v1/broadcasts/{broadcastId}/recipients | Add recipients to a broadcast |
| [**CancelBroadcast**](BroadcastsApi.md#cancelbroadcast) | **POST** /v1/broadcasts/{broadcastId}/cancel | Cancel a broadcast |
| [**CreateBroadcast**](BroadcastsApi.md#createbroadcast) | **POST** /v1/broadcasts | Create a broadcast draft |
| [**DeleteBroadcast**](BroadcastsApi.md#deletebroadcast) | **DELETE** /v1/broadcasts/{broadcastId} | Delete a broadcast (draft only) |
| [**GetBroadcast**](BroadcastsApi.md#getbroadcast) | **GET** /v1/broadcasts/{broadcastId} | Get broadcast details |
| [**ListBroadcastRecipients**](BroadcastsApi.md#listbroadcastrecipients) | **GET** /v1/broadcasts/{broadcastId}/recipients | List broadcast recipients |
| [**ListBroadcasts**](BroadcastsApi.md#listbroadcasts) | **GET** /v1/broadcasts | List broadcasts |
| [**ScheduleBroadcast**](BroadcastsApi.md#schedulebroadcast) | **POST** /v1/broadcasts/{broadcastId}/schedule | Schedule broadcast for later |
| [**SendBroadcast**](BroadcastsApi.md#sendbroadcast) | **POST** /v1/broadcasts/{broadcastId}/send | Trigger immediate send |
| [**UpdateBroadcast**](BroadcastsApi.md#updatebroadcast) | **PATCH** /v1/broadcasts/{broadcastId} | Update a broadcast |

<a id="addbroadcastrecipients"></a>
# **AddBroadcastRecipients**
> AddBroadcastRecipients200Response AddBroadcastRecipients (string broadcastId, AddBroadcastRecipientsRequest addBroadcastRecipientsRequest)

Add recipients to a broadcast

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
    public class AddBroadcastRecipientsExample
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
            var apiInstance = new BroadcastsApi(httpClient, config, httpClientHandler);
            var broadcastId = "broadcastId_example";  // string | 
            var addBroadcastRecipientsRequest = new AddBroadcastRecipientsRequest(); // AddBroadcastRecipientsRequest | 

            try
            {
                // Add recipients to a broadcast
                AddBroadcastRecipients200Response result = apiInstance.AddBroadcastRecipients(broadcastId, addBroadcastRecipientsRequest);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling BroadcastsApi.AddBroadcastRecipients: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the AddBroadcastRecipientsWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Add recipients to a broadcast
    ApiResponse<AddBroadcastRecipients200Response> response = apiInstance.AddBroadcastRecipientsWithHttpInfo(broadcastId, addBroadcastRecipientsRequest);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling BroadcastsApi.AddBroadcastRecipientsWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **broadcastId** | **string** |  |  |
| **addBroadcastRecipientsRequest** | [**AddBroadcastRecipientsRequest**](AddBroadcastRecipientsRequest.md) |  |  |

### Return type

[**AddBroadcastRecipients200Response**](AddBroadcastRecipients200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Recipients added |  -  |
| **401** | Unauthorized |  -  |
| **404** | Resource not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="cancelbroadcast"></a>
# **CancelBroadcast**
> CancelBroadcast200Response CancelBroadcast (string broadcastId)

Cancel a broadcast

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
    public class CancelBroadcastExample
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
            var apiInstance = new BroadcastsApi(httpClient, config, httpClientHandler);
            var broadcastId = "broadcastId_example";  // string | 

            try
            {
                // Cancel a broadcast
                CancelBroadcast200Response result = apiInstance.CancelBroadcast(broadcastId);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling BroadcastsApi.CancelBroadcast: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the CancelBroadcastWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Cancel a broadcast
    ApiResponse<CancelBroadcast200Response> response = apiInstance.CancelBroadcastWithHttpInfo(broadcastId);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling BroadcastsApi.CancelBroadcastWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **broadcastId** | **string** |  |  |

### Return type

[**CancelBroadcast200Response**](CancelBroadcast200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Broadcast cancelled |  -  |
| **400** | Cannot cancel in current status |  -  |
| **401** | Unauthorized |  -  |
| **404** | Resource not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="createbroadcast"></a>
# **CreateBroadcast**
> void CreateBroadcast (CreateBroadcastRequest createBroadcastRequest)

Create a broadcast draft

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
    public class CreateBroadcastExample
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
            var apiInstance = new BroadcastsApi(httpClient, config, httpClientHandler);
            var createBroadcastRequest = new CreateBroadcastRequest(); // CreateBroadcastRequest | 

            try
            {
                // Create a broadcast draft
                apiInstance.CreateBroadcast(createBroadcastRequest);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling BroadcastsApi.CreateBroadcast: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the CreateBroadcastWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Create a broadcast draft
    apiInstance.CreateBroadcastWithHttpInfo(createBroadcastRequest);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling BroadcastsApi.CreateBroadcastWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **createBroadcastRequest** | [**CreateBroadcastRequest**](CreateBroadcastRequest.md) |  |  |

### Return type

void (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Broadcast created |  -  |
| **401** | Unauthorized |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="deletebroadcast"></a>
# **DeleteBroadcast**
> void DeleteBroadcast (string broadcastId)

Delete a broadcast (draft only)

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
    public class DeleteBroadcastExample
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
            var apiInstance = new BroadcastsApi(httpClient, config, httpClientHandler);
            var broadcastId = "broadcastId_example";  // string | 

            try
            {
                // Delete a broadcast (draft only)
                apiInstance.DeleteBroadcast(broadcastId);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling BroadcastsApi.DeleteBroadcast: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the DeleteBroadcastWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Delete a broadcast (draft only)
    apiInstance.DeleteBroadcastWithHttpInfo(broadcastId);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling BroadcastsApi.DeleteBroadcastWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **broadcastId** | **string** |  |  |

### Return type

void (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Broadcast deleted |  -  |
| **401** | Unauthorized |  -  |
| **404** | Resource not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="getbroadcast"></a>
# **GetBroadcast**
> GetBroadcast200Response GetBroadcast (string broadcastId)

Get broadcast details

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
    public class GetBroadcastExample
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
            var apiInstance = new BroadcastsApi(httpClient, config, httpClientHandler);
            var broadcastId = "broadcastId_example";  // string | 

            try
            {
                // Get broadcast details
                GetBroadcast200Response result = apiInstance.GetBroadcast(broadcastId);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling BroadcastsApi.GetBroadcast: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the GetBroadcastWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Get broadcast details
    ApiResponse<GetBroadcast200Response> response = apiInstance.GetBroadcastWithHttpInfo(broadcastId);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling BroadcastsApi.GetBroadcastWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **broadcastId** | **string** |  |  |

### Return type

[**GetBroadcast200Response**](GetBroadcast200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Broadcast details with stats |  -  |
| **401** | Unauthorized |  -  |
| **404** | Resource not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="listbroadcastrecipients"></a>
# **ListBroadcastRecipients**
> ListBroadcastRecipients200Response ListBroadcastRecipients (string broadcastId, string? status = null, int? limit = null, int? skip = null)

List broadcast recipients

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
    public class ListBroadcastRecipientsExample
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
            var apiInstance = new BroadcastsApi(httpClient, config, httpClientHandler);
            var broadcastId = "broadcastId_example";  // string | 
            var status = "pending";  // string? |  (optional) 
            var limit = 50;  // int? |  (optional)  (default to 50)
            var skip = 0;  // int? |  (optional)  (default to 0)

            try
            {
                // List broadcast recipients
                ListBroadcastRecipients200Response result = apiInstance.ListBroadcastRecipients(broadcastId, status, limit, skip);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling BroadcastsApi.ListBroadcastRecipients: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the ListBroadcastRecipientsWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // List broadcast recipients
    ApiResponse<ListBroadcastRecipients200Response> response = apiInstance.ListBroadcastRecipientsWithHttpInfo(broadcastId, status, limit, skip);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling BroadcastsApi.ListBroadcastRecipientsWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **broadcastId** | **string** |  |  |
| **status** | **string?** |  | [optional]  |
| **limit** | **int?** |  | [optional] [default to 50] |
| **skip** | **int?** |  | [optional] [default to 0] |

### Return type

[**ListBroadcastRecipients200Response**](ListBroadcastRecipients200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Recipients list with delivery status |  -  |
| **401** | Unauthorized |  -  |
| **404** | Resource not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="listbroadcasts"></a>
# **ListBroadcasts**
> ListBroadcasts200Response ListBroadcasts (string? profileId = null, string? status = null, string? platform = null, int? limit = null, int? skip = null)

List broadcasts

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
    public class ListBroadcastsExample
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
            var apiInstance = new BroadcastsApi(httpClient, config, httpClientHandler);
            var profileId = "profileId_example";  // string? | Filter by profile. Omit to list across all profiles (optional) 
            var status = "draft";  // string? |  (optional) 
            var platform = "platform_example";  // string? |  (optional) 
            var limit = 50;  // int? |  (optional)  (default to 50)
            var skip = 0;  // int? |  (optional)  (default to 0)

            try
            {
                // List broadcasts
                ListBroadcasts200Response result = apiInstance.ListBroadcasts(profileId, status, platform, limit, skip);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling BroadcastsApi.ListBroadcasts: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the ListBroadcastsWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // List broadcasts
    ApiResponse<ListBroadcasts200Response> response = apiInstance.ListBroadcastsWithHttpInfo(profileId, status, platform, limit, skip);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling BroadcastsApi.ListBroadcastsWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **profileId** | **string?** | Filter by profile. Omit to list across all profiles | [optional]  |
| **status** | **string?** |  | [optional]  |
| **platform** | **string?** |  | [optional]  |
| **limit** | **int?** |  | [optional] [default to 50] |
| **skip** | **int?** |  | [optional] [default to 0] |

### Return type

[**ListBroadcasts200Response**](ListBroadcasts200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Broadcasts list |  -  |
| **401** | Unauthorized |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="schedulebroadcast"></a>
# **ScheduleBroadcast**
> ScheduleBroadcast200Response ScheduleBroadcast (string broadcastId, ScheduleBroadcastRequest scheduleBroadcastRequest)

Schedule broadcast for later

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
    public class ScheduleBroadcastExample
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
            var apiInstance = new BroadcastsApi(httpClient, config, httpClientHandler);
            var broadcastId = "broadcastId_example";  // string | 
            var scheduleBroadcastRequest = new ScheduleBroadcastRequest(); // ScheduleBroadcastRequest | 

            try
            {
                // Schedule broadcast for later
                ScheduleBroadcast200Response result = apiInstance.ScheduleBroadcast(broadcastId, scheduleBroadcastRequest);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling BroadcastsApi.ScheduleBroadcast: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the ScheduleBroadcastWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Schedule broadcast for later
    ApiResponse<ScheduleBroadcast200Response> response = apiInstance.ScheduleBroadcastWithHttpInfo(broadcastId, scheduleBroadcastRequest);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling BroadcastsApi.ScheduleBroadcastWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **broadcastId** | **string** |  |  |
| **scheduleBroadcastRequest** | [**ScheduleBroadcastRequest**](ScheduleBroadcastRequest.md) |  |  |

### Return type

[**ScheduleBroadcast200Response**](ScheduleBroadcast200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Broadcast scheduled |  -  |
| **400** | Invalid date or status |  -  |
| **401** | Unauthorized |  -  |
| **404** | Resource not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="sendbroadcast"></a>
# **SendBroadcast**
> SendBroadcast200Response SendBroadcast (string broadcastId)

Trigger immediate send

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
    public class SendBroadcastExample
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
            var apiInstance = new BroadcastsApi(httpClient, config, httpClientHandler);
            var broadcastId = "broadcastId_example";  // string | 

            try
            {
                // Trigger immediate send
                SendBroadcast200Response result = apiInstance.SendBroadcast(broadcastId);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling BroadcastsApi.SendBroadcast: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the SendBroadcastWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Trigger immediate send
    ApiResponse<SendBroadcast200Response> response = apiInstance.SendBroadcastWithHttpInfo(broadcastId);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling BroadcastsApi.SendBroadcastWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **broadcastId** | **string** |  |  |

### Return type

[**SendBroadcast200Response**](SendBroadcast200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Broadcast sending started |  -  |
| **400** | Invalid status or no recipients |  -  |
| **401** | Unauthorized |  -  |
| **404** | Resource not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="updatebroadcast"></a>
# **UpdateBroadcast**
> UpdateBroadcast200Response UpdateBroadcast (string broadcastId)

Update a broadcast

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
    public class UpdateBroadcastExample
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
            var apiInstance = new BroadcastsApi(httpClient, config, httpClientHandler);
            var broadcastId = "broadcastId_example";  // string | 

            try
            {
                // Update a broadcast
                UpdateBroadcast200Response result = apiInstance.UpdateBroadcast(broadcastId);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling BroadcastsApi.UpdateBroadcast: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the UpdateBroadcastWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Update a broadcast
    ApiResponse<UpdateBroadcast200Response> response = apiInstance.UpdateBroadcastWithHttpInfo(broadcastId);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling BroadcastsApi.UpdateBroadcastWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **broadcastId** | **string** |  |  |

### Return type

[**UpdateBroadcast200Response**](UpdateBroadcast200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Broadcast updated |  -  |
| **401** | Unauthorized |  -  |
| **404** | Resource not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

