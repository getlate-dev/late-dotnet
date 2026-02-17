# Late.Api.AccountSettingsApi

All URIs are relative to *https://getlate.dev/api*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**DeleteInstagramIceBreakers**](AccountSettingsApi.md#deleteinstagramicebreakers) | **DELETE** /v1/accounts/{accountId}/instagram-ice-breakers | Delete IG ice breakers |
| [**DeleteMessengerMenu**](AccountSettingsApi.md#deletemessengermenu) | **DELETE** /v1/accounts/{accountId}/messenger-menu | Delete FB persistent menu |
| [**DeleteTelegramCommands**](AccountSettingsApi.md#deletetelegramcommands) | **DELETE** /v1/accounts/{accountId}/telegram-commands | Delete TG bot commands |
| [**GetInstagramIceBreakers**](AccountSettingsApi.md#getinstagramicebreakers) | **GET** /v1/accounts/{accountId}/instagram-ice-breakers | Get IG ice breakers |
| [**GetMessengerMenu**](AccountSettingsApi.md#getmessengermenu) | **GET** /v1/accounts/{accountId}/messenger-menu | Get FB persistent menu |
| [**GetTelegramCommands**](AccountSettingsApi.md#gettelegramcommands) | **GET** /v1/accounts/{accountId}/telegram-commands | Get TG bot commands |
| [**SetInstagramIceBreakers**](AccountSettingsApi.md#setinstagramicebreakers) | **PUT** /v1/accounts/{accountId}/instagram-ice-breakers | Set IG ice breakers |
| [**SetMessengerMenu**](AccountSettingsApi.md#setmessengermenu) | **PUT** /v1/accounts/{accountId}/messenger-menu | Set FB persistent menu |
| [**SetTelegramCommands**](AccountSettingsApi.md#settelegramcommands) | **PUT** /v1/accounts/{accountId}/telegram-commands | Set TG bot commands |

<a id="deleteinstagramicebreakers"></a>
# **DeleteInstagramIceBreakers**
> void DeleteInstagramIceBreakers (string accountId)

Delete IG ice breakers

Removes the ice breaker questions from an Instagram account's Messenger experience.

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
    public class DeleteInstagramIceBreakersExample
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
            var apiInstance = new AccountSettingsApi(httpClient, config, httpClientHandler);
            var accountId = "accountId_example";  // string | 

            try
            {
                // Delete IG ice breakers
                apiInstance.DeleteInstagramIceBreakers(accountId);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling AccountSettingsApi.DeleteInstagramIceBreakers: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the DeleteInstagramIceBreakersWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Delete IG ice breakers
    apiInstance.DeleteInstagramIceBreakersWithHttpInfo(accountId);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling AccountSettingsApi.DeleteInstagramIceBreakersWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **accountId** | **string** |  |  |

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
| **200** | Ice breakers deleted |  -  |
| **401** | Unauthorized |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="deletemessengermenu"></a>
# **DeleteMessengerMenu**
> void DeleteMessengerMenu (string accountId)

Delete FB persistent menu

Removes the persistent menu from Facebook Messenger conversations for this account.

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
    public class DeleteMessengerMenuExample
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
            var apiInstance = new AccountSettingsApi(httpClient, config, httpClientHandler);
            var accountId = "accountId_example";  // string | 

            try
            {
                // Delete FB persistent menu
                apiInstance.DeleteMessengerMenu(accountId);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling AccountSettingsApi.DeleteMessengerMenu: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the DeleteMessengerMenuWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Delete FB persistent menu
    apiInstance.DeleteMessengerMenuWithHttpInfo(accountId);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling AccountSettingsApi.DeleteMessengerMenuWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **accountId** | **string** |  |  |

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
| **200** | Menu deleted |  -  |
| **401** | Unauthorized |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="deletetelegramcommands"></a>
# **DeleteTelegramCommands**
> void DeleteTelegramCommands (string accountId)

Delete TG bot commands

Clears all bot commands configured for a Telegram bot account.

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
    public class DeleteTelegramCommandsExample
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
            var apiInstance = new AccountSettingsApi(httpClient, config, httpClientHandler);
            var accountId = "accountId_example";  // string | 

            try
            {
                // Delete TG bot commands
                apiInstance.DeleteTelegramCommands(accountId);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling AccountSettingsApi.DeleteTelegramCommands: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the DeleteTelegramCommandsWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Delete TG bot commands
    apiInstance.DeleteTelegramCommandsWithHttpInfo(accountId);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling AccountSettingsApi.DeleteTelegramCommandsWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **accountId** | **string** |  |  |

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
| **200** | Commands deleted |  -  |
| **401** | Unauthorized |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="getinstagramicebreakers"></a>
# **GetInstagramIceBreakers**
> GetMessengerMenu200Response GetInstagramIceBreakers (string accountId)

Get IG ice breakers

Get the ice breaker configuration for an Instagram account.

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
    public class GetInstagramIceBreakersExample
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
            var apiInstance = new AccountSettingsApi(httpClient, config, httpClientHandler);
            var accountId = "accountId_example";  // string | 

            try
            {
                // Get IG ice breakers
                GetMessengerMenu200Response result = apiInstance.GetInstagramIceBreakers(accountId);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling AccountSettingsApi.GetInstagramIceBreakers: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the GetInstagramIceBreakersWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Get IG ice breakers
    ApiResponse<GetMessengerMenu200Response> response = apiInstance.GetInstagramIceBreakersWithHttpInfo(accountId);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling AccountSettingsApi.GetInstagramIceBreakersWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **accountId** | **string** |  |  |

### Return type

[**GetMessengerMenu200Response**](GetMessengerMenu200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Ice breaker configuration |  -  |
| **400** | Not an Instagram account |  -  |
| **401** | Unauthorized |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="getmessengermenu"></a>
# **GetMessengerMenu**
> GetMessengerMenu200Response GetMessengerMenu (string accountId)

Get FB persistent menu

Get the persistent menu configuration for a Facebook Messenger account.

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
    public class GetMessengerMenuExample
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
            var apiInstance = new AccountSettingsApi(httpClient, config, httpClientHandler);
            var accountId = "accountId_example";  // string | 

            try
            {
                // Get FB persistent menu
                GetMessengerMenu200Response result = apiInstance.GetMessengerMenu(accountId);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling AccountSettingsApi.GetMessengerMenu: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the GetMessengerMenuWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Get FB persistent menu
    ApiResponse<GetMessengerMenu200Response> response = apiInstance.GetMessengerMenuWithHttpInfo(accountId);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling AccountSettingsApi.GetMessengerMenuWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **accountId** | **string** |  |  |

### Return type

[**GetMessengerMenu200Response**](GetMessengerMenu200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Persistent menu configuration |  -  |
| **400** | Not a Facebook account |  -  |
| **401** | Unauthorized |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="gettelegramcommands"></a>
# **GetTelegramCommands**
> GetTelegramCommands200Response GetTelegramCommands (string accountId)

Get TG bot commands

Get the bot commands configuration for a Telegram account.

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
    public class GetTelegramCommandsExample
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
            var apiInstance = new AccountSettingsApi(httpClient, config, httpClientHandler);
            var accountId = "accountId_example";  // string | 

            try
            {
                // Get TG bot commands
                GetTelegramCommands200Response result = apiInstance.GetTelegramCommands(accountId);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling AccountSettingsApi.GetTelegramCommands: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the GetTelegramCommandsWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Get TG bot commands
    ApiResponse<GetTelegramCommands200Response> response = apiInstance.GetTelegramCommandsWithHttpInfo(accountId);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling AccountSettingsApi.GetTelegramCommandsWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **accountId** | **string** |  |  |

### Return type

[**GetTelegramCommands200Response**](GetTelegramCommands200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Bot commands list |  -  |
| **400** | Not a Telegram account |  -  |
| **401** | Unauthorized |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="setinstagramicebreakers"></a>
# **SetInstagramIceBreakers**
> void SetInstagramIceBreakers (string accountId, SetInstagramIceBreakersRequest setInstagramIceBreakersRequest)

Set IG ice breakers

Set ice breakers for an Instagram account. Max 4 ice breakers, question max 80 chars.

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
    public class SetInstagramIceBreakersExample
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
            var apiInstance = new AccountSettingsApi(httpClient, config, httpClientHandler);
            var accountId = "accountId_example";  // string | 
            var setInstagramIceBreakersRequest = new SetInstagramIceBreakersRequest(); // SetInstagramIceBreakersRequest | 

            try
            {
                // Set IG ice breakers
                apiInstance.SetInstagramIceBreakers(accountId, setInstagramIceBreakersRequest);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling AccountSettingsApi.SetInstagramIceBreakers: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the SetInstagramIceBreakersWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Set IG ice breakers
    apiInstance.SetInstagramIceBreakersWithHttpInfo(accountId, setInstagramIceBreakersRequest);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling AccountSettingsApi.SetInstagramIceBreakersWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **accountId** | **string** |  |  |
| **setInstagramIceBreakersRequest** | [**SetInstagramIceBreakersRequest**](SetInstagramIceBreakersRequest.md) |  |  |

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
| **200** | Ice breakers set successfully |  -  |
| **400** | Invalid request |  -  |
| **401** | Unauthorized |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="setmessengermenu"></a>
# **SetMessengerMenu**
> void SetMessengerMenu (string accountId, SetMessengerMenuRequest setMessengerMenuRequest)

Set FB persistent menu

Set the persistent menu for a Facebook Messenger account. Max 3 top-level items, max 5 nested items.

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
    public class SetMessengerMenuExample
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
            var apiInstance = new AccountSettingsApi(httpClient, config, httpClientHandler);
            var accountId = "accountId_example";  // string | 
            var setMessengerMenuRequest = new SetMessengerMenuRequest(); // SetMessengerMenuRequest | 

            try
            {
                // Set FB persistent menu
                apiInstance.SetMessengerMenu(accountId, setMessengerMenuRequest);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling AccountSettingsApi.SetMessengerMenu: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the SetMessengerMenuWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Set FB persistent menu
    apiInstance.SetMessengerMenuWithHttpInfo(accountId, setMessengerMenuRequest);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling AccountSettingsApi.SetMessengerMenuWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **accountId** | **string** |  |  |
| **setMessengerMenuRequest** | [**SetMessengerMenuRequest**](SetMessengerMenuRequest.md) |  |  |

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
| **200** | Menu set successfully |  -  |
| **400** | Invalid request |  -  |
| **401** | Unauthorized |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="settelegramcommands"></a>
# **SetTelegramCommands**
> void SetTelegramCommands (string accountId, SetTelegramCommandsRequest setTelegramCommandsRequest)

Set TG bot commands

Set bot commands for a Telegram account.

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
    public class SetTelegramCommandsExample
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
            var apiInstance = new AccountSettingsApi(httpClient, config, httpClientHandler);
            var accountId = "accountId_example";  // string | 
            var setTelegramCommandsRequest = new SetTelegramCommandsRequest(); // SetTelegramCommandsRequest | 

            try
            {
                // Set TG bot commands
                apiInstance.SetTelegramCommands(accountId, setTelegramCommandsRequest);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling AccountSettingsApi.SetTelegramCommands: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the SetTelegramCommandsWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Set TG bot commands
    apiInstance.SetTelegramCommandsWithHttpInfo(accountId, setTelegramCommandsRequest);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling AccountSettingsApi.SetTelegramCommandsWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **accountId** | **string** |  |  |
| **setTelegramCommandsRequest** | [**SetTelegramCommandsRequest**](SetTelegramCommandsRequest.md) |  |  |

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
| **200** | Commands set successfully |  -  |
| **400** | Invalid request |  -  |
| **401** | Unauthorized |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

