# Late.Api.AdAudiencesApi

All URIs are relative to *https://zernio.com/api*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**AddUsersToAdAudience**](AdAudiencesApi.md#adduserstoadaudience) | **POST** /v1/ads/audiences/{audienceId}/users | Add users to audience |
| [**CreateAdAudience**](AdAudiencesApi.md#createadaudience) | **POST** /v1/ads/audiences | Create custom audience |
| [**DeleteAdAudience**](AdAudiencesApi.md#deleteadaudience) | **DELETE** /v1/ads/audiences/{audienceId} | Delete custom audience |
| [**GetAdAudience**](AdAudiencesApi.md#getadaudience) | **GET** /v1/ads/audiences/{audienceId} | Get audience details |
| [**ListAdAudiences**](AdAudiencesApi.md#listadaudiences) | **GET** /v1/ads/audiences | List custom audiences |

<a id="adduserstoadaudience"></a>
# **AddUsersToAdAudience**
> AddUsersToAdAudience200Response AddUsersToAdAudience (string audienceId, AddUsersToAdAudienceRequest addUsersToAdAudienceRequest)

Add users to audience

Upload user data (emails and/or phone numbers) to a customer_list audience. Data is SHA256-hashed server-side before sending to Meta. Max 10,000 users per request.

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
    public class AddUsersToAdAudienceExample
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
            var apiInstance = new AdAudiencesApi(httpClient, config, httpClientHandler);
            var audienceId = "audienceId_example";  // string | 
            var addUsersToAdAudienceRequest = new AddUsersToAdAudienceRequest(); // AddUsersToAdAudienceRequest | 

            try
            {
                // Add users to audience
                AddUsersToAdAudience200Response result = apiInstance.AddUsersToAdAudience(audienceId, addUsersToAdAudienceRequest);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling AdAudiencesApi.AddUsersToAdAudience: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the AddUsersToAdAudienceWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Add users to audience
    ApiResponse<AddUsersToAdAudience200Response> response = apiInstance.AddUsersToAdAudienceWithHttpInfo(audienceId, addUsersToAdAudienceRequest);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling AdAudiencesApi.AddUsersToAdAudienceWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **audienceId** | **string** |  |  |
| **addUsersToAdAudienceRequest** | [**AddUsersToAdAudienceRequest**](AddUsersToAdAudienceRequest.md) |  |  |

### Return type

[**AddUsersToAdAudience200Response**](AddUsersToAdAudience200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Users added |  -  |
| **400** | Invalid input (empty users array, missing email/phone) |  -  |
| **401** | Unauthorized |  -  |
| **403** | Ads add-on required |  -  |
| **404** | Resource not found |  -  |
| **422** | Audience is not a customer_list type or has no platform ID yet |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="createadaudience"></a>
# **CreateAdAudience**
> CreateAdAudience201Response CreateAdAudience (CreateAdAudienceRequest createAdAudienceRequest)

Create custom audience

Create a customer list, website retargeting, or lookalike audience on Meta (Facebook/Instagram).

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
    public class CreateAdAudienceExample
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
            var apiInstance = new AdAudiencesApi(httpClient, config, httpClientHandler);
            var createAdAudienceRequest = new CreateAdAudienceRequest(); // CreateAdAudienceRequest | 

            try
            {
                // Create custom audience
                CreateAdAudience201Response result = apiInstance.CreateAdAudience(createAdAudienceRequest);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling AdAudiencesApi.CreateAdAudience: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the CreateAdAudienceWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Create custom audience
    ApiResponse<CreateAdAudience201Response> response = apiInstance.CreateAdAudienceWithHttpInfo(createAdAudienceRequest);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling AdAudiencesApi.CreateAdAudienceWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **createAdAudienceRequest** | [**CreateAdAudienceRequest**](CreateAdAudienceRequest.md) |  |  |

### Return type

[**CreateAdAudience201Response**](CreateAdAudience201Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Audience created |  -  |
| **400** | Missing required fields |  -  |
| **401** | Unauthorized |  -  |
| **403** | Ads add-on required |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="deleteadaudience"></a>
# **DeleteAdAudience**
> DeleteAccountGroup200Response DeleteAdAudience (string audienceId)

Delete custom audience

Deletes the audience from both Meta and the local database.

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
    public class DeleteAdAudienceExample
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
            var apiInstance = new AdAudiencesApi(httpClient, config, httpClientHandler);
            var audienceId = "audienceId_example";  // string | 

            try
            {
                // Delete custom audience
                DeleteAccountGroup200Response result = apiInstance.DeleteAdAudience(audienceId);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling AdAudiencesApi.DeleteAdAudience: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the DeleteAdAudienceWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Delete custom audience
    ApiResponse<DeleteAccountGroup200Response> response = apiInstance.DeleteAdAudienceWithHttpInfo(audienceId);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling AdAudiencesApi.DeleteAdAudienceWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **audienceId** | **string** |  |  |

### Return type

[**DeleteAccountGroup200Response**](DeleteAccountGroup200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Audience deleted |  -  |
| **401** | Unauthorized |  -  |
| **403** | Ads add-on required |  -  |
| **404** | Resource not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="getadaudience"></a>
# **GetAdAudience**
> GetAdAudience200Response GetAdAudience (string audienceId)

Get audience details

Returns the local audience record and fresh data from Meta (if available).

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
    public class GetAdAudienceExample
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
            var apiInstance = new AdAudiencesApi(httpClient, config, httpClientHandler);
            var audienceId = "audienceId_example";  // string | 

            try
            {
                // Get audience details
                GetAdAudience200Response result = apiInstance.GetAdAudience(audienceId);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling AdAudiencesApi.GetAdAudience: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the GetAdAudienceWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Get audience details
    ApiResponse<GetAdAudience200Response> response = apiInstance.GetAdAudienceWithHttpInfo(audienceId);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling AdAudiencesApi.GetAdAudienceWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **audienceId** | **string** |  |  |

### Return type

[**GetAdAudience200Response**](GetAdAudience200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Audience details |  -  |
| **401** | Unauthorized |  -  |
| **403** | Ads add-on required |  -  |
| **404** | Resource not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="listadaudiences"></a>
# **ListAdAudiences**
> ListAdAudiences200Response ListAdAudiences (string accountId, string adAccountId, string? platform = null)

List custom audiences

Returns custom audiences for the given ad account. Supports Meta, Google, TikTok, and Pinterest.

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
    public class ListAdAudiencesExample
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
            var apiInstance = new AdAudiencesApi(httpClient, config, httpClientHandler);
            var accountId = "accountId_example";  // string | Social account ID
            var adAccountId = "adAccountId_example";  // string | Platform ad account ID
            var platform = "facebook";  // string? |  (optional) 

            try
            {
                // List custom audiences
                ListAdAudiences200Response result = apiInstance.ListAdAudiences(accountId, adAccountId, platform);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling AdAudiencesApi.ListAdAudiences: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the ListAdAudiencesWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // List custom audiences
    ApiResponse<ListAdAudiences200Response> response = apiInstance.ListAdAudiencesWithHttpInfo(accountId, adAccountId, platform);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling AdAudiencesApi.ListAdAudiencesWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **accountId** | **string** | Social account ID |  |
| **adAccountId** | **string** | Platform ad account ID |  |
| **platform** | **string?** |  | [optional]  |

### Return type

[**ListAdAudiences200Response**](ListAdAudiences200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Audiences |  -  |
| **401** | Unauthorized |  -  |
| **403** | Ads add-on required |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

