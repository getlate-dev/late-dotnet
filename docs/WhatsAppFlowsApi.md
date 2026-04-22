# Zernio.Api.WhatsAppFlowsApi

All URIs are relative to *https://zernio.com/api*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**CreateWhatsAppFlow**](WhatsAppFlowsApi.md#createwhatsappflow) | **POST** /v1/whatsapp/flows | Create flow |
| [**DeleteWhatsAppFlow**](WhatsAppFlowsApi.md#deletewhatsappflow) | **DELETE** /v1/whatsapp/flows/{flowId} | Delete flow |
| [**DeprecateWhatsAppFlow**](WhatsAppFlowsApi.md#deprecatewhatsappflow) | **POST** /v1/whatsapp/flows/{flowId}/deprecate | Deprecate flow |
| [**GetWhatsAppFlow**](WhatsAppFlowsApi.md#getwhatsappflow) | **GET** /v1/whatsapp/flows/{flowId} | Get flow |
| [**GetWhatsAppFlowJson**](WhatsAppFlowsApi.md#getwhatsappflowjson) | **GET** /v1/whatsapp/flows/{flowId}/json | Get flow JSON asset |
| [**ListWhatsAppFlows**](WhatsAppFlowsApi.md#listwhatsappflows) | **GET** /v1/whatsapp/flows | List flows |
| [**PublishWhatsAppFlow**](WhatsAppFlowsApi.md#publishwhatsappflow) | **POST** /v1/whatsapp/flows/{flowId}/publish | Publish flow |
| [**SendWhatsAppFlowMessage**](WhatsAppFlowsApi.md#sendwhatsappflowmessage) | **POST** /v1/whatsapp/flows/send | Send flow message |
| [**UpdateWhatsAppFlow**](WhatsAppFlowsApi.md#updatewhatsappflow) | **PATCH** /v1/whatsapp/flows/{flowId} | Update flow |
| [**UploadWhatsAppFlowJson**](WhatsAppFlowsApi.md#uploadwhatsappflowjson) | **PUT** /v1/whatsapp/flows/{flowId}/json | Upload flow JSON |

<a id="createwhatsappflow"></a>
# **CreateWhatsAppFlow**
> CreateWhatsAppFlow200Response CreateWhatsAppFlow (CreateWhatsAppFlowRequest createWhatsAppFlowRequest)

Create flow

Create a new WhatsApp Flow in DRAFT status. Optionally clone an existing flow. After creating, upload a Flow JSON definition, then publish to make it sendable. 

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
    public class CreateWhatsAppFlowExample
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
            var apiInstance = new WhatsAppFlowsApi(httpClient, config, httpClientHandler);
            var createWhatsAppFlowRequest = new CreateWhatsAppFlowRequest(); // CreateWhatsAppFlowRequest | 

            try
            {
                // Create flow
                CreateWhatsAppFlow200Response result = apiInstance.CreateWhatsAppFlow(createWhatsAppFlowRequest);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling WhatsAppFlowsApi.CreateWhatsAppFlow: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the CreateWhatsAppFlowWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Create flow
    ApiResponse<CreateWhatsAppFlow200Response> response = apiInstance.CreateWhatsAppFlowWithHttpInfo(createWhatsAppFlowRequest);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling WhatsAppFlowsApi.CreateWhatsAppFlowWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **createWhatsAppFlowRequest** | [**CreateWhatsAppFlowRequest**](CreateWhatsAppFlowRequest.md) |  |  |

### Return type

[**CreateWhatsAppFlow200Response**](CreateWhatsAppFlow200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Flow created |  -  |
| **400** | Validation error |  -  |
| **401** | Unauthorized |  -  |
| **404** | WhatsApp account not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="deletewhatsappflow"></a>
# **DeleteWhatsAppFlow**
> UpdateYoutubeDefaultPlaylist200Response DeleteWhatsAppFlow (string flowId, string accountId)

Delete flow

Delete a DRAFT flow. This is irreversible. Only flows in DRAFT status can be deleted. 

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
    public class DeleteWhatsAppFlowExample
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
            var apiInstance = new WhatsAppFlowsApi(httpClient, config, httpClientHandler);
            var flowId = "flowId_example";  // string | Flow ID
            var accountId = "accountId_example";  // string | WhatsApp social account ID

            try
            {
                // Delete flow
                UpdateYoutubeDefaultPlaylist200Response result = apiInstance.DeleteWhatsAppFlow(flowId, accountId);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling WhatsAppFlowsApi.DeleteWhatsAppFlow: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the DeleteWhatsAppFlowWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Delete flow
    ApiResponse<UpdateYoutubeDefaultPlaylist200Response> response = apiInstance.DeleteWhatsAppFlowWithHttpInfo(flowId, accountId);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling WhatsAppFlowsApi.DeleteWhatsAppFlowWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **flowId** | **string** | Flow ID |  |
| **accountId** | **string** | WhatsApp social account ID |  |

### Return type

[**UpdateYoutubeDefaultPlaylist200Response**](UpdateYoutubeDefaultPlaylist200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Flow deleted |  -  |
| **400** | Flow is not in DRAFT status |  -  |
| **401** | Unauthorized |  -  |
| **404** | WhatsApp account or flow not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="deprecatewhatsappflow"></a>
# **DeprecateWhatsAppFlow**
> UpdateYoutubeDefaultPlaylist200Response DeprecateWhatsAppFlow (string flowId, PublishWhatsAppFlowRequest publishWhatsAppFlowRequest)

Deprecate flow

Deprecate a PUBLISHED flow. This is irreversible. Deprecated flows cannot be sent or opened, but existing active sessions may continue until they complete. 

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
    public class DeprecateWhatsAppFlowExample
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
            var apiInstance = new WhatsAppFlowsApi(httpClient, config, httpClientHandler);
            var flowId = "flowId_example";  // string | Flow ID
            var publishWhatsAppFlowRequest = new PublishWhatsAppFlowRequest(); // PublishWhatsAppFlowRequest | 

            try
            {
                // Deprecate flow
                UpdateYoutubeDefaultPlaylist200Response result = apiInstance.DeprecateWhatsAppFlow(flowId, publishWhatsAppFlowRequest);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling WhatsAppFlowsApi.DeprecateWhatsAppFlow: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the DeprecateWhatsAppFlowWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Deprecate flow
    ApiResponse<UpdateYoutubeDefaultPlaylist200Response> response = apiInstance.DeprecateWhatsAppFlowWithHttpInfo(flowId, publishWhatsAppFlowRequest);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling WhatsAppFlowsApi.DeprecateWhatsAppFlowWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **flowId** | **string** | Flow ID |  |
| **publishWhatsAppFlowRequest** | [**PublishWhatsAppFlowRequest**](PublishWhatsAppFlowRequest.md) |  |  |

### Return type

[**UpdateYoutubeDefaultPlaylist200Response**](UpdateYoutubeDefaultPlaylist200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Flow deprecated |  -  |
| **400** | Flow is not in PUBLISHED status |  -  |
| **401** | Unauthorized |  -  |
| **404** | WhatsApp account not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="getwhatsappflow"></a>
# **GetWhatsAppFlow**
> GetWhatsAppFlow200Response GetWhatsAppFlow (string flowId, string accountId, string? fields = null)

Get flow

Get details for a specific flow, including status, categories, validation errors, and preview URL. 

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
    public class GetWhatsAppFlowExample
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
            var apiInstance = new WhatsAppFlowsApi(httpClient, config, httpClientHandler);
            var flowId = "flowId_example";  // string | Flow ID
            var accountId = "accountId_example";  // string | WhatsApp social account ID
            var fields = "fields_example";  // string? | Comma-separated fields to return (default: id,name,status,categories,validation_errors,json_version,preview,data_api_version,endpoint_uri) (optional) 

            try
            {
                // Get flow
                GetWhatsAppFlow200Response result = apiInstance.GetWhatsAppFlow(flowId, accountId, fields);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling WhatsAppFlowsApi.GetWhatsAppFlow: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the GetWhatsAppFlowWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Get flow
    ApiResponse<GetWhatsAppFlow200Response> response = apiInstance.GetWhatsAppFlowWithHttpInfo(flowId, accountId, fields);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling WhatsAppFlowsApi.GetWhatsAppFlowWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **flowId** | **string** | Flow ID |  |
| **accountId** | **string** | WhatsApp social account ID |  |
| **fields** | **string?** | Comma-separated fields to return (default: id,name,status,categories,validation_errors,json_version,preview,data_api_version,endpoint_uri) | [optional]  |

### Return type

[**GetWhatsAppFlow200Response**](GetWhatsAppFlow200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Flow details |  -  |
| **401** | Unauthorized |  -  |
| **404** | Flow or account not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="getwhatsappflowjson"></a>
# **GetWhatsAppFlowJson**
> GetWhatsAppFlowJson200Response GetWhatsAppFlowJson (string flowId, string accountId)

Get flow JSON asset

Get the flow JSON asset metadata, including a temporary download URL for the Flow JSON file. 

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
    public class GetWhatsAppFlowJsonExample
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
            var apiInstance = new WhatsAppFlowsApi(httpClient, config, httpClientHandler);
            var flowId = "flowId_example";  // string | Flow ID
            var accountId = "accountId_example";  // string | WhatsApp social account ID

            try
            {
                // Get flow JSON asset
                GetWhatsAppFlowJson200Response result = apiInstance.GetWhatsAppFlowJson(flowId, accountId);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling WhatsAppFlowsApi.GetWhatsAppFlowJson: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the GetWhatsAppFlowJsonWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Get flow JSON asset
    ApiResponse<GetWhatsAppFlowJson200Response> response = apiInstance.GetWhatsAppFlowJsonWithHttpInfo(flowId, accountId);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling WhatsAppFlowsApi.GetWhatsAppFlowJsonWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **flowId** | **string** | Flow ID |  |
| **accountId** | **string** | WhatsApp social account ID |  |

### Return type

[**GetWhatsAppFlowJson200Response**](GetWhatsAppFlowJson200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Flow JSON asset |  -  |
| **401** | Unauthorized |  -  |
| **404** | WhatsApp account not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="listwhatsappflows"></a>
# **ListWhatsAppFlows**
> ListWhatsAppFlows200Response ListWhatsAppFlows (string accountId)

List flows

List all WhatsApp Flows for the Business Account (WABA) associated with the given account. 

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
    public class ListWhatsAppFlowsExample
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
            var apiInstance = new WhatsAppFlowsApi(httpClient, config, httpClientHandler);
            var accountId = "accountId_example";  // string | WhatsApp social account ID

            try
            {
                // List flows
                ListWhatsAppFlows200Response result = apiInstance.ListWhatsAppFlows(accountId);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling WhatsAppFlowsApi.ListWhatsAppFlows: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the ListWhatsAppFlowsWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // List flows
    ApiResponse<ListWhatsAppFlows200Response> response = apiInstance.ListWhatsAppFlowsWithHttpInfo(accountId);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling WhatsAppFlowsApi.ListWhatsAppFlowsWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **accountId** | **string** | WhatsApp social account ID |  |

### Return type

[**ListWhatsAppFlows200Response**](ListWhatsAppFlows200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Flows retrieved |  -  |
| **400** | WABA ID not found on account |  -  |
| **401** | Unauthorized |  -  |
| **404** | WhatsApp account not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="publishwhatsappflow"></a>
# **PublishWhatsAppFlow**
> UpdateYoutubeDefaultPlaylist200Response PublishWhatsAppFlow (string flowId, PublishWhatsAppFlowRequest publishWhatsAppFlowRequest)

Publish flow

Publish a DRAFT flow. This is irreversible. Once published, the flow and its JSON become immutable and the flow can be sent to users. To update a published flow, create a new flow (optionally cloning this one via cloneFlowId). 

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
    public class PublishWhatsAppFlowExample
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
            var apiInstance = new WhatsAppFlowsApi(httpClient, config, httpClientHandler);
            var flowId = "flowId_example";  // string | Flow ID
            var publishWhatsAppFlowRequest = new PublishWhatsAppFlowRequest(); // PublishWhatsAppFlowRequest | 

            try
            {
                // Publish flow
                UpdateYoutubeDefaultPlaylist200Response result = apiInstance.PublishWhatsAppFlow(flowId, publishWhatsAppFlowRequest);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling WhatsAppFlowsApi.PublishWhatsAppFlow: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the PublishWhatsAppFlowWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Publish flow
    ApiResponse<UpdateYoutubeDefaultPlaylist200Response> response = apiInstance.PublishWhatsAppFlowWithHttpInfo(flowId, publishWhatsAppFlowRequest);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling WhatsAppFlowsApi.PublishWhatsAppFlowWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **flowId** | **string** | Flow ID |  |
| **publishWhatsAppFlowRequest** | [**PublishWhatsAppFlowRequest**](PublishWhatsAppFlowRequest.md) |  |  |

### Return type

[**UpdateYoutubeDefaultPlaylist200Response**](UpdateYoutubeDefaultPlaylist200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Flow published |  -  |
| **400** | Flow is not in DRAFT status or has validation errors |  -  |
| **401** | Unauthorized |  -  |
| **404** | WhatsApp account not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="sendwhatsappflowmessage"></a>
# **SendWhatsAppFlowMessage**
> SendWhatsAppFlowMessage200Response SendWhatsAppFlowMessage (SendWhatsAppFlowMessageRequest sendWhatsAppFlowMessageRequest)

Send flow message

Send a published flow as an interactive message with a CTA button. When the recipient taps the button, the flow opens natively in WhatsApp. Flow responses are received via webhooks. 

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
    public class SendWhatsAppFlowMessageExample
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
            var apiInstance = new WhatsAppFlowsApi(httpClient, config, httpClientHandler);
            var sendWhatsAppFlowMessageRequest = new SendWhatsAppFlowMessageRequest(); // SendWhatsAppFlowMessageRequest | 

            try
            {
                // Send flow message
                SendWhatsAppFlowMessage200Response result = apiInstance.SendWhatsAppFlowMessage(sendWhatsAppFlowMessageRequest);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling WhatsAppFlowsApi.SendWhatsAppFlowMessage: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the SendWhatsAppFlowMessageWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Send flow message
    ApiResponse<SendWhatsAppFlowMessage200Response> response = apiInstance.SendWhatsAppFlowMessageWithHttpInfo(sendWhatsAppFlowMessageRequest);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling WhatsAppFlowsApi.SendWhatsAppFlowMessageWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **sendWhatsAppFlowMessageRequest** | [**SendWhatsAppFlowMessageRequest**](SendWhatsAppFlowMessageRequest.md) |  |  |

### Return type

[**SendWhatsAppFlowMessage200Response**](SendWhatsAppFlowMessage200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Flow message sent |  -  |
| **400** | Validation error or missing phone number ID |  -  |
| **401** | Unauthorized |  -  |
| **404** | WhatsApp account not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="updatewhatsappflow"></a>
# **UpdateWhatsAppFlow**
> UpdateYoutubeDefaultPlaylist200Response UpdateWhatsAppFlow (string flowId, UpdateWhatsAppFlowRequest updateWhatsAppFlowRequest)

Update flow

Update metadata (name, categories) of a DRAFT flow. Published flows are immutable. 

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
    public class UpdateWhatsAppFlowExample
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
            var apiInstance = new WhatsAppFlowsApi(httpClient, config, httpClientHandler);
            var flowId = "flowId_example";  // string | Flow ID
            var updateWhatsAppFlowRequest = new UpdateWhatsAppFlowRequest(); // UpdateWhatsAppFlowRequest | 

            try
            {
                // Update flow
                UpdateYoutubeDefaultPlaylist200Response result = apiInstance.UpdateWhatsAppFlow(flowId, updateWhatsAppFlowRequest);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling WhatsAppFlowsApi.UpdateWhatsAppFlow: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the UpdateWhatsAppFlowWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Update flow
    ApiResponse<UpdateYoutubeDefaultPlaylist200Response> response = apiInstance.UpdateWhatsAppFlowWithHttpInfo(flowId, updateWhatsAppFlowRequest);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling WhatsAppFlowsApi.UpdateWhatsAppFlowWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **flowId** | **string** | Flow ID |  |
| **updateWhatsAppFlowRequest** | [**UpdateWhatsAppFlowRequest**](UpdateWhatsAppFlowRequest.md) |  |  |

### Return type

[**UpdateYoutubeDefaultPlaylist200Response**](UpdateYoutubeDefaultPlaylist200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Flow updated |  -  |
| **400** | At least one of name or categories is required, or flow is not in DRAFT status |  -  |
| **401** | Unauthorized |  -  |
| **404** | WhatsApp account or flow not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="uploadwhatsappflowjson"></a>
# **UploadWhatsAppFlowJson**
> UploadWhatsAppFlowJson200Response UploadWhatsAppFlowJson (string flowId, UploadWhatsAppFlowJsonRequest uploadWhatsAppFlowJsonRequest)

Upload flow JSON

Upload or update the Flow JSON for a DRAFT flow. The Flow JSON defines all screens, components (text inputs, dropdowns, date pickers, etc.), and navigation.  Meta validates the JSON on upload and returns any validation errors. See: https://developers.facebook.com/docs/whatsapp/flows/reference/flowjson 

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
    public class UploadWhatsAppFlowJsonExample
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
            var apiInstance = new WhatsAppFlowsApi(httpClient, config, httpClientHandler);
            var flowId = "flowId_example";  // string | Flow ID
            var uploadWhatsAppFlowJsonRequest = new UploadWhatsAppFlowJsonRequest(); // UploadWhatsAppFlowJsonRequest | 

            try
            {
                // Upload flow JSON
                UploadWhatsAppFlowJson200Response result = apiInstance.UploadWhatsAppFlowJson(flowId, uploadWhatsAppFlowJsonRequest);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling WhatsAppFlowsApi.UploadWhatsAppFlowJson: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the UploadWhatsAppFlowJsonWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Upload flow JSON
    ApiResponse<UploadWhatsAppFlowJson200Response> response = apiInstance.UploadWhatsAppFlowJsonWithHttpInfo(flowId, uploadWhatsAppFlowJsonRequest);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling WhatsAppFlowsApi.UploadWhatsAppFlowJsonWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **flowId** | **string** | Flow ID |  |
| **uploadWhatsAppFlowJsonRequest** | [**UploadWhatsAppFlowJsonRequest**](UploadWhatsAppFlowJsonRequest.md) |  |  |

### Return type

[**UploadWhatsAppFlowJson200Response**](UploadWhatsAppFlowJson200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Flow JSON uploaded |  -  |
| **400** | Invalid JSON or flow is not in DRAFT status |  -  |
| **401** | Unauthorized |  -  |
| **404** | WhatsApp account not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

