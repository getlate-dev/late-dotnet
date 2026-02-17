# Late.Api.QueueApi

All URIs are relative to *https://getlate.dev/api*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**CreateQueueSlot**](QueueApi.md#createqueueslot) | **POST** /v1/queue/slots | Create schedule |
| [**DeleteQueueSlot**](QueueApi.md#deletequeueslot) | **DELETE** /v1/queue/slots | Delete schedule |
| [**GetNextQueueSlot**](QueueApi.md#getnextqueueslot) | **GET** /v1/queue/next-slot | Get next available slot |
| [**ListQueueSlots**](QueueApi.md#listqueueslots) | **GET** /v1/queue/slots | List schedules |
| [**PreviewQueue**](QueueApi.md#previewqueue) | **GET** /v1/queue/preview | Preview upcoming slots |
| [**UpdateQueueSlot**](QueueApi.md#updatequeueslot) | **PUT** /v1/queue/slots | Update schedule |

<a id="createqueueslot"></a>
# **CreateQueueSlot**
> CreateQueueSlot201Response CreateQueueSlot (CreateQueueSlotRequest createQueueSlotRequest)

Create schedule

Create an additional queue for a profile. The first queue created becomes the default. Subsequent queues are non-default unless explicitly set. 

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
    public class CreateQueueSlotExample
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
            var apiInstance = new QueueApi(httpClient, config, httpClientHandler);
            var createQueueSlotRequest = new CreateQueueSlotRequest(); // CreateQueueSlotRequest | 

            try
            {
                // Create schedule
                CreateQueueSlot201Response result = apiInstance.CreateQueueSlot(createQueueSlotRequest);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling QueueApi.CreateQueueSlot: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the CreateQueueSlotWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Create schedule
    ApiResponse<CreateQueueSlot201Response> response = apiInstance.CreateQueueSlotWithHttpInfo(createQueueSlotRequest);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling QueueApi.CreateQueueSlotWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **createQueueSlotRequest** | [**CreateQueueSlotRequest**](CreateQueueSlotRequest.md) |  |  |

### Return type

[**CreateQueueSlot201Response**](CreateQueueSlot201Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Queue created |  -  |
| **400** | Invalid request or validation error |  -  |
| **401** | Unauthorized |  -  |
| **404** | Profile not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="deletequeueslot"></a>
# **DeleteQueueSlot**
> DeleteQueueSlot200Response DeleteQueueSlot (string profileId, string queueId)

Delete schedule

Delete a queue from a profile. Requires queueId to specify which queue to delete. If deleting the default queue, another queue will be promoted to default. 

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
    public class DeleteQueueSlotExample
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
            var apiInstance = new QueueApi(httpClient, config, httpClientHandler);
            var profileId = "profileId_example";  // string | 
            var queueId = "queueId_example";  // string | Queue ID to delete

            try
            {
                // Delete schedule
                DeleteQueueSlot200Response result = apiInstance.DeleteQueueSlot(profileId, queueId);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling QueueApi.DeleteQueueSlot: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the DeleteQueueSlotWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Delete schedule
    ApiResponse<DeleteQueueSlot200Response> response = apiInstance.DeleteQueueSlotWithHttpInfo(profileId, queueId);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling QueueApi.DeleteQueueSlotWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **profileId** | **string** |  |  |
| **queueId** | **string** | Queue ID to delete |  |

### Return type

[**DeleteQueueSlot200Response**](DeleteQueueSlot200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Queue schedule deleted |  -  |
| **400** | Missing profileId or queueId |  -  |
| **401** | Unauthorized |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="getnextqueueslot"></a>
# **GetNextQueueSlot**
> GetNextQueueSlot200Response GetNextQueueSlot (string profileId, string? queueId = null)

Get next available slot

Returns the next available queue slot for preview/informational purposes.  **Important: To schedule a post to the queue, do NOT use this endpoint's response with `scheduledFor`.** That creates a manual post, not a queue post.  Instead, use `POST /v1/posts` with `queuedFromProfile` (and optionally `queueId`). The system will automatically assign the next available slot with proper locking to prevent race conditions.  This endpoint is useful for: - Showing users when their next post will go out before they commit - Debugging/verifying queue configuration - Building UI previews  If no queueId is specified, uses the profile's default queue. 

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
    public class GetNextQueueSlotExample
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
            var apiInstance = new QueueApi(httpClient, config, httpClientHandler);
            var profileId = "profileId_example";  // string | 
            var queueId = "queueId_example";  // string? | Specific queue ID (optional, defaults to profile's default queue) (optional) 

            try
            {
                // Get next available slot
                GetNextQueueSlot200Response result = apiInstance.GetNextQueueSlot(profileId, queueId);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling QueueApi.GetNextQueueSlot: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the GetNextQueueSlotWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Get next available slot
    ApiResponse<GetNextQueueSlot200Response> response = apiInstance.GetNextQueueSlotWithHttpInfo(profileId, queueId);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling QueueApi.GetNextQueueSlotWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **profileId** | **string** |  |  |
| **queueId** | **string?** | Specific queue ID (optional, defaults to profile&#39;s default queue) | [optional]  |

### Return type

[**GetNextQueueSlot200Response**](GetNextQueueSlot200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Next available slot |  -  |
| **400** | Invalid parameters or inactive queue |  -  |
| **401** | Unauthorized |  -  |
| **404** | Profile or queue schedule not found, or no available slots |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="listqueueslots"></a>
# **ListQueueSlots**
> ListQueueSlots200Response ListQueueSlots (string profileId, string? queueId = null, string? all = null)

List schedules

Retrieve queue schedules for a profile. Each profile can have multiple queues. - Without `all=true`: Returns the default queue (or specific queue if queueId provided) - With `all=true`: Returns all queues for the profile 

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
    public class ListQueueSlotsExample
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
            var apiInstance = new QueueApi(httpClient, config, httpClientHandler);
            var profileId = "profileId_example";  // string | Profile ID to get queues for
            var queueId = "queueId_example";  // string? | Specific queue ID to retrieve (optional) (optional) 
            var all = "true";  // string? | Set to 'true' to list all queues for the profile (optional) 

            try
            {
                // List schedules
                ListQueueSlots200Response result = apiInstance.ListQueueSlots(profileId, queueId, all);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling QueueApi.ListQueueSlots: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the ListQueueSlotsWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // List schedules
    ApiResponse<ListQueueSlots200Response> response = apiInstance.ListQueueSlotsWithHttpInfo(profileId, queueId, all);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling QueueApi.ListQueueSlotsWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **profileId** | **string** | Profile ID to get queues for |  |
| **queueId** | **string?** | Specific queue ID to retrieve (optional) | [optional]  |
| **all** | **string?** | Set to &#39;true&#39; to list all queues for the profile | [optional]  |

### Return type

[**ListQueueSlots200Response**](ListQueueSlots200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Queue schedule(s) retrieved |  -  |
| **400** | Missing profileId |  -  |
| **401** | Unauthorized |  -  |
| **404** | Profile not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="previewqueue"></a>
# **PreviewQueue**
> PreviewQueue200Response PreviewQueue (string profileId, int? count = null)

Preview upcoming slots

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
    public class PreviewQueueExample
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
            var apiInstance = new QueueApi(httpClient, config, httpClientHandler);
            var profileId = "profileId_example";  // string | 
            var count = 20;  // int? |  (optional)  (default to 20)

            try
            {
                // Preview upcoming slots
                PreviewQueue200Response result = apiInstance.PreviewQueue(profileId, count);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling QueueApi.PreviewQueue: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the PreviewQueueWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Preview upcoming slots
    ApiResponse<PreviewQueue200Response> response = apiInstance.PreviewQueueWithHttpInfo(profileId, count);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling QueueApi.PreviewQueueWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **profileId** | **string** |  |  |
| **count** | **int?** |  | [optional] [default to 20] |

### Return type

[**PreviewQueue200Response**](PreviewQueue200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Queue slots preview |  -  |
| **400** | Invalid parameters |  -  |
| **401** | Unauthorized |  -  |
| **404** | Profile or queue schedule not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="updatequeueslot"></a>
# **UpdateQueueSlot**
> UpdateQueueSlot200Response UpdateQueueSlot (UpdateQueueSlotRequest updateQueueSlotRequest)

Update schedule

Create a new queue or update an existing one. - Without queueId: Creates or updates the default queue - With queueId: Updates the specific queue - With setAsDefault=true: Makes this queue the default for the profile 

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
    public class UpdateQueueSlotExample
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
            var apiInstance = new QueueApi(httpClient, config, httpClientHandler);
            var updateQueueSlotRequest = new UpdateQueueSlotRequest(); // UpdateQueueSlotRequest | 

            try
            {
                // Update schedule
                UpdateQueueSlot200Response result = apiInstance.UpdateQueueSlot(updateQueueSlotRequest);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling QueueApi.UpdateQueueSlot: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the UpdateQueueSlotWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Update schedule
    ApiResponse<UpdateQueueSlot200Response> response = apiInstance.UpdateQueueSlotWithHttpInfo(updateQueueSlotRequest);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling QueueApi.UpdateQueueSlotWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **updateQueueSlotRequest** | [**UpdateQueueSlotRequest**](UpdateQueueSlotRequest.md) |  |  |

### Return type

[**UpdateQueueSlot200Response**](UpdateQueueSlot200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Queue schedule updated |  -  |
| **400** | Invalid request |  -  |
| **401** | Unauthorized |  -  |
| **404** | Profile not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

