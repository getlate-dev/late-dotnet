# Late.Api.CommentAutomationsApi

All URIs are relative to *https://zernio.com/api*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**CreateCommentAutomation**](CommentAutomationsApi.md#createcommentautomation) | **POST** /v1/comment-automations | Create comment-to-DM automation |
| [**DeleteCommentAutomation**](CommentAutomationsApi.md#deletecommentautomation) | **DELETE** /v1/comment-automations/{automationId} | Delete automation |
| [**GetCommentAutomation**](CommentAutomationsApi.md#getcommentautomation) | **GET** /v1/comment-automations/{automationId} | Get automation details |
| [**ListCommentAutomationLogs**](CommentAutomationsApi.md#listcommentautomationlogs) | **GET** /v1/comment-automations/{automationId}/logs | List automation logs |
| [**ListCommentAutomations**](CommentAutomationsApi.md#listcommentautomations) | **GET** /v1/comment-automations | List comment-to-DM automations |
| [**UpdateCommentAutomation**](CommentAutomationsApi.md#updatecommentautomation) | **PATCH** /v1/comment-automations/{automationId} | Update automation settings |

<a id="createcommentautomation"></a>
# **CreateCommentAutomation**
> CreateCommentAutomation200Response CreateCommentAutomation (CreateCommentAutomationRequest createCommentAutomationRequest)

Create comment-to-DM automation

Create a keyword-triggered DM automation on an Instagram or Facebook post. When someone comments a matching keyword, they automatically receive a DM. Only one active automation per post is allowed. 

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
    public class CreateCommentAutomationExample
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
            var apiInstance = new CommentAutomationsApi(httpClient, config, httpClientHandler);
            var createCommentAutomationRequest = new CreateCommentAutomationRequest(); // CreateCommentAutomationRequest | 

            try
            {
                // Create comment-to-DM automation
                CreateCommentAutomation200Response result = apiInstance.CreateCommentAutomation(createCommentAutomationRequest);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling CommentAutomationsApi.CreateCommentAutomation: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the CreateCommentAutomationWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Create comment-to-DM automation
    ApiResponse<CreateCommentAutomation200Response> response = apiInstance.CreateCommentAutomationWithHttpInfo(createCommentAutomationRequest);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling CommentAutomationsApi.CreateCommentAutomationWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **createCommentAutomationRequest** | [**CreateCommentAutomationRequest**](CreateCommentAutomationRequest.md) |  |  |

### Return type

[**CreateCommentAutomation200Response**](CreateCommentAutomation200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Automation created |  -  |
| **400** | Validation error |  -  |
| **401** | Unauthorized |  -  |
| **409** | Active automation already exists for this post |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="deletecommentautomation"></a>
# **DeleteCommentAutomation**
> void DeleteCommentAutomation (string automationId)

Delete automation

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
    public class DeleteCommentAutomationExample
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
            var apiInstance = new CommentAutomationsApi(httpClient, config, httpClientHandler);
            var automationId = "automationId_example";  // string | 

            try
            {
                // Delete automation
                apiInstance.DeleteCommentAutomation(automationId);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling CommentAutomationsApi.DeleteCommentAutomation: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the DeleteCommentAutomationWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Delete automation
    apiInstance.DeleteCommentAutomationWithHttpInfo(automationId);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling CommentAutomationsApi.DeleteCommentAutomationWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **automationId** | **string** |  |  |

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
| **200** | Automation deleted |  -  |
| **401** | Unauthorized |  -  |
| **404** | Resource not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="getcommentautomation"></a>
# **GetCommentAutomation**
> GetCommentAutomation200Response GetCommentAutomation (string automationId)

Get automation details

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
    public class GetCommentAutomationExample
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
            var apiInstance = new CommentAutomationsApi(httpClient, config, httpClientHandler);
            var automationId = "automationId_example";  // string | 

            try
            {
                // Get automation details
                GetCommentAutomation200Response result = apiInstance.GetCommentAutomation(automationId);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling CommentAutomationsApi.GetCommentAutomation: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the GetCommentAutomationWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Get automation details
    ApiResponse<GetCommentAutomation200Response> response = apiInstance.GetCommentAutomationWithHttpInfo(automationId);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling CommentAutomationsApi.GetCommentAutomationWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **automationId** | **string** |  |  |

### Return type

[**GetCommentAutomation200Response**](GetCommentAutomation200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Automation details with stats and recent trigger logs |  -  |
| **401** | Unauthorized |  -  |
| **404** | Resource not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="listcommentautomationlogs"></a>
# **ListCommentAutomationLogs**
> ListCommentAutomationLogs200Response ListCommentAutomationLogs (string automationId, string? status = null, int? limit = null, int? skip = null)

List automation logs

Paginated list of every comment that triggered this automation, with send status and commenter info.

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
    public class ListCommentAutomationLogsExample
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
            var apiInstance = new CommentAutomationsApi(httpClient, config, httpClientHandler);
            var automationId = "automationId_example";  // string | 
            var status = "sent";  // string? | Filter by result status (optional) 
            var limit = 50;  // int? |  (optional)  (default to 50)
            var skip = 0;  // int? |  (optional)  (default to 0)

            try
            {
                // List automation logs
                ListCommentAutomationLogs200Response result = apiInstance.ListCommentAutomationLogs(automationId, status, limit, skip);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling CommentAutomationsApi.ListCommentAutomationLogs: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the ListCommentAutomationLogsWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // List automation logs
    ApiResponse<ListCommentAutomationLogs200Response> response = apiInstance.ListCommentAutomationLogsWithHttpInfo(automationId, status, limit, skip);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling CommentAutomationsApi.ListCommentAutomationLogsWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **automationId** | **string** |  |  |
| **status** | **string?** | Filter by result status | [optional]  |
| **limit** | **int?** |  | [optional] [default to 50] |
| **skip** | **int?** |  | [optional] [default to 0] |

### Return type

[**ListCommentAutomationLogs200Response**](ListCommentAutomationLogs200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Trigger logs with pagination |  -  |
| **401** | Unauthorized |  -  |
| **404** | Resource not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="listcommentautomations"></a>
# **ListCommentAutomations**
> ListCommentAutomations200Response ListCommentAutomations (string? profileId = null)

List comment-to-DM automations

List all comment-to-DM automations for a profile. Returns automations with their stats.

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
    public class ListCommentAutomationsExample
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
            var apiInstance = new CommentAutomationsApi(httpClient, config, httpClientHandler);
            var profileId = "profileId_example";  // string? | Filter by profile. Omit to list across all profiles (optional) 

            try
            {
                // List comment-to-DM automations
                ListCommentAutomations200Response result = apiInstance.ListCommentAutomations(profileId);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling CommentAutomationsApi.ListCommentAutomations: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the ListCommentAutomationsWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // List comment-to-DM automations
    ApiResponse<ListCommentAutomations200Response> response = apiInstance.ListCommentAutomationsWithHttpInfo(profileId);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling CommentAutomationsApi.ListCommentAutomationsWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **profileId** | **string?** | Filter by profile. Omit to list across all profiles | [optional]  |

### Return type

[**ListCommentAutomations200Response**](ListCommentAutomations200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Automations list |  -  |
| **401** | Unauthorized |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="updatecommentautomation"></a>
# **UpdateCommentAutomation**
> UpdateCommentAutomation200Response UpdateCommentAutomation (string automationId, UpdateCommentAutomationRequest? updateCommentAutomationRequest = null)

Update automation settings

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
    public class UpdateCommentAutomationExample
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
            var apiInstance = new CommentAutomationsApi(httpClient, config, httpClientHandler);
            var automationId = "automationId_example";  // string | 
            var updateCommentAutomationRequest = new UpdateCommentAutomationRequest?(); // UpdateCommentAutomationRequest? |  (optional) 

            try
            {
                // Update automation settings
                UpdateCommentAutomation200Response result = apiInstance.UpdateCommentAutomation(automationId, updateCommentAutomationRequest);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling CommentAutomationsApi.UpdateCommentAutomation: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the UpdateCommentAutomationWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Update automation settings
    ApiResponse<UpdateCommentAutomation200Response> response = apiInstance.UpdateCommentAutomationWithHttpInfo(automationId, updateCommentAutomationRequest);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling CommentAutomationsApi.UpdateCommentAutomationWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **automationId** | **string** |  |  |
| **updateCommentAutomationRequest** | [**UpdateCommentAutomationRequest?**](UpdateCommentAutomationRequest?.md) |  | [optional]  |

### Return type

[**UpdateCommentAutomation200Response**](UpdateCommentAutomation200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Automation updated |  -  |
| **401** | Unauthorized |  -  |
| **404** | Resource not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

