# Late.Api.WebhooksApi

All URIs are relative to *https://getlate.dev/api*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**CreateWebhookSettings**](WebhooksApi.md#createwebhooksettings) | **POST** /v1/webhooks/settings | Create webhook |
| [**DeleteWebhookSettings**](WebhooksApi.md#deletewebhooksettings) | **DELETE** /v1/webhooks/settings | Delete webhook |
| [**GetWebhookLogs**](WebhooksApi.md#getwebhooklogs) | **GET** /v1/webhooks/logs | Get delivery logs |
| [**GetWebhookSettings**](WebhooksApi.md#getwebhooksettings) | **GET** /v1/webhooks/settings | List webhooks |
| [**TestWebhook**](WebhooksApi.md#testwebhook) | **POST** /v1/webhooks/test | Send test webhook |
| [**UpdateWebhookSettings**](WebhooksApi.md#updatewebhooksettings) | **PUT** /v1/webhooks/settings | Update webhook |

<a id="createwebhooksettings"></a>
# **CreateWebhookSettings**
> UpdateWebhookSettings200Response CreateWebhookSettings (CreateWebhookSettingsRequest createWebhookSettingsRequest)

Create webhook

Create a new webhook configuration. Maximum 10 webhooks per user.  **Note:** Webhooks are automatically disabled after 10 consecutive delivery failures. 

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
    public class CreateWebhookSettingsExample
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
            var apiInstance = new WebhooksApi(httpClient, config, httpClientHandler);
            var createWebhookSettingsRequest = new CreateWebhookSettingsRequest(); // CreateWebhookSettingsRequest | 

            try
            {
                // Create webhook
                UpdateWebhookSettings200Response result = apiInstance.CreateWebhookSettings(createWebhookSettingsRequest);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling WebhooksApi.CreateWebhookSettings: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the CreateWebhookSettingsWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Create webhook
    ApiResponse<UpdateWebhookSettings200Response> response = apiInstance.CreateWebhookSettingsWithHttpInfo(createWebhookSettingsRequest);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling WebhooksApi.CreateWebhookSettingsWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **createWebhookSettingsRequest** | [**CreateWebhookSettingsRequest**](CreateWebhookSettingsRequest.md) |  |  |

### Return type

[**UpdateWebhookSettings200Response**](UpdateWebhookSettings200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Webhook created successfully |  -  |
| **400** | Validation error or maximum webhooks reached |  -  |
| **401** | Unauthorized |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="deletewebhooksettings"></a>
# **DeleteWebhookSettings**
> UpdateRedditSubreddits200Response DeleteWebhookSettings (string id)

Delete webhook

Permanently delete a webhook configuration.

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
    public class DeleteWebhookSettingsExample
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
            var apiInstance = new WebhooksApi(httpClient, config, httpClientHandler);
            var id = "id_example";  // string | Webhook ID to delete

            try
            {
                // Delete webhook
                UpdateRedditSubreddits200Response result = apiInstance.DeleteWebhookSettings(id);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling WebhooksApi.DeleteWebhookSettings: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the DeleteWebhookSettingsWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Delete webhook
    ApiResponse<UpdateRedditSubreddits200Response> response = apiInstance.DeleteWebhookSettingsWithHttpInfo(id);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling WebhooksApi.DeleteWebhookSettingsWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **id** | **string** | Webhook ID to delete |  |

### Return type

[**UpdateRedditSubreddits200Response**](UpdateRedditSubreddits200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Webhook deleted successfully |  -  |
| **400** | Webhook ID required |  -  |
| **401** | Unauthorized |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="getwebhooklogs"></a>
# **GetWebhookLogs**
> GetWebhookLogs200Response GetWebhookLogs (int? limit = null, string? status = null, string? varEvent = null, string? webhookId = null)

Get delivery logs

Retrieve webhook delivery history. Logs are automatically deleted after 7 days. 

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
    public class GetWebhookLogsExample
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
            var apiInstance = new WebhooksApi(httpClient, config, httpClientHandler);
            var limit = 50;  // int? | Maximum number of logs to return (max 100) (optional)  (default to 50)
            var status = "success";  // string? | Filter by delivery status (optional) 
            var varEvent = "post.scheduled";  // string? | Filter by event type (optional) 
            var webhookId = "webhookId_example";  // string? | Filter by webhook ID (optional) 

            try
            {
                // Get delivery logs
                GetWebhookLogs200Response result = apiInstance.GetWebhookLogs(limit, status, varEvent, webhookId);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling WebhooksApi.GetWebhookLogs: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the GetWebhookLogsWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Get delivery logs
    ApiResponse<GetWebhookLogs200Response> response = apiInstance.GetWebhookLogsWithHttpInfo(limit, status, varEvent, webhookId);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling WebhooksApi.GetWebhookLogsWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **limit** | **int?** | Maximum number of logs to return (max 100) | [optional] [default to 50] |
| **status** | **string?** | Filter by delivery status | [optional]  |
| **varEvent** | **string?** | Filter by event type | [optional]  |
| **webhookId** | **string?** | Filter by webhook ID | [optional]  |

### Return type

[**GetWebhookLogs200Response**](GetWebhookLogs200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Webhook logs retrieved successfully |  -  |
| **401** | Unauthorized |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="getwebhooksettings"></a>
# **GetWebhookSettings**
> GetWebhookSettings200Response GetWebhookSettings ()

List webhooks

Retrieve all configured webhooks for the authenticated user. Supports up to 10 webhooks per user.

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
    public class GetWebhookSettingsExample
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
            var apiInstance = new WebhooksApi(httpClient, config, httpClientHandler);

            try
            {
                // List webhooks
                GetWebhookSettings200Response result = apiInstance.GetWebhookSettings();
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling WebhooksApi.GetWebhookSettings: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the GetWebhookSettingsWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // List webhooks
    ApiResponse<GetWebhookSettings200Response> response = apiInstance.GetWebhookSettingsWithHttpInfo();
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling WebhooksApi.GetWebhookSettingsWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters
This endpoint does not need any parameter.
### Return type

[**GetWebhookSettings200Response**](GetWebhookSettings200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Webhooks retrieved successfully |  -  |
| **401** | Unauthorized |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="testwebhook"></a>
# **TestWebhook**
> UnpublishPost200Response TestWebhook (TestWebhookRequest testWebhookRequest)

Send test webhook

Send a test webhook to verify your endpoint is configured correctly. The test payload includes `event: \"webhook.test\"` to distinguish it from real events. 

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
    public class TestWebhookExample
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
            var apiInstance = new WebhooksApi(httpClient, config, httpClientHandler);
            var testWebhookRequest = new TestWebhookRequest(); // TestWebhookRequest | 

            try
            {
                // Send test webhook
                UnpublishPost200Response result = apiInstance.TestWebhook(testWebhookRequest);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling WebhooksApi.TestWebhook: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the TestWebhookWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Send test webhook
    ApiResponse<UnpublishPost200Response> response = apiInstance.TestWebhookWithHttpInfo(testWebhookRequest);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling WebhooksApi.TestWebhookWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **testWebhookRequest** | [**TestWebhookRequest**](TestWebhookRequest.md) |  |  |

### Return type

[**UnpublishPost200Response**](UnpublishPost200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Test webhook sent successfully |  -  |
| **400** | Webhook ID required |  -  |
| **401** | Unauthorized |  -  |
| **500** | Test webhook failed to deliver |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="updatewebhooksettings"></a>
# **UpdateWebhookSettings**
> UpdateWebhookSettings200Response UpdateWebhookSettings (UpdateWebhookSettingsRequest updateWebhookSettingsRequest)

Update webhook

Update an existing webhook configuration. All fields except `_id` are optional - only provided fields will be updated.  **Note:** Webhooks are automatically disabled after 10 consecutive delivery failures. 

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
    public class UpdateWebhookSettingsExample
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
            var apiInstance = new WebhooksApi(httpClient, config, httpClientHandler);
            var updateWebhookSettingsRequest = new UpdateWebhookSettingsRequest(); // UpdateWebhookSettingsRequest | 

            try
            {
                // Update webhook
                UpdateWebhookSettings200Response result = apiInstance.UpdateWebhookSettings(updateWebhookSettingsRequest);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling WebhooksApi.UpdateWebhookSettings: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the UpdateWebhookSettingsWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Update webhook
    ApiResponse<UpdateWebhookSettings200Response> response = apiInstance.UpdateWebhookSettingsWithHttpInfo(updateWebhookSettingsRequest);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling WebhooksApi.UpdateWebhookSettingsWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **updateWebhookSettingsRequest** | [**UpdateWebhookSettingsRequest**](UpdateWebhookSettingsRequest.md) |  |  |

### Return type

[**UpdateWebhookSettings200Response**](UpdateWebhookSettings200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Webhook updated successfully |  -  |
| **400** | Validation error or missing webhook ID |  -  |
| **401** | Unauthorized |  -  |
| **404** | Webhook not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

