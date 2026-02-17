# Late.Api.AccountGroupsApi

All URIs are relative to *https://getlate.dev/api*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**CreateAccountGroup**](AccountGroupsApi.md#createaccountgroup) | **POST** /v1/account-groups | Create group |
| [**DeleteAccountGroup**](AccountGroupsApi.md#deleteaccountgroup) | **DELETE** /v1/account-groups/{groupId} | Delete group |
| [**ListAccountGroups**](AccountGroupsApi.md#listaccountgroups) | **GET** /v1/account-groups | List groups |
| [**UpdateAccountGroup**](AccountGroupsApi.md#updateaccountgroup) | **PUT** /v1/account-groups/{groupId} | Update group |

<a id="createaccountgroup"></a>
# **CreateAccountGroup**
> CreateAccountGroup201Response CreateAccountGroup (CreateAccountGroupRequest createAccountGroupRequest)

Create group

Creates a new account group with a name and a list of social account IDs.

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
    public class CreateAccountGroupExample
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
            var apiInstance = new AccountGroupsApi(httpClient, config, httpClientHandler);
            var createAccountGroupRequest = new CreateAccountGroupRequest(); // CreateAccountGroupRequest | 

            try
            {
                // Create group
                CreateAccountGroup201Response result = apiInstance.CreateAccountGroup(createAccountGroupRequest);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling AccountGroupsApi.CreateAccountGroup: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the CreateAccountGroupWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Create group
    ApiResponse<CreateAccountGroup201Response> response = apiInstance.CreateAccountGroupWithHttpInfo(createAccountGroupRequest);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling AccountGroupsApi.CreateAccountGroupWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **createAccountGroupRequest** | [**CreateAccountGroupRequest**](CreateAccountGroupRequest.md) |  |  |

### Return type

[**CreateAccountGroup201Response**](CreateAccountGroup201Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Created |  -  |
| **400** | Invalid request |  -  |
| **401** | Unauthorized |  -  |
| **409** | Group name already exists |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="deleteaccountgroup"></a>
# **DeleteAccountGroup**
> DeleteAccountGroup200Response DeleteAccountGroup (string groupId)

Delete group

Permanently deletes an account group. The accounts themselves are not affected.

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
    public class DeleteAccountGroupExample
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
            var apiInstance = new AccountGroupsApi(httpClient, config, httpClientHandler);
            var groupId = "groupId_example";  // string | 

            try
            {
                // Delete group
                DeleteAccountGroup200Response result = apiInstance.DeleteAccountGroup(groupId);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling AccountGroupsApi.DeleteAccountGroup: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the DeleteAccountGroupWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Delete group
    ApiResponse<DeleteAccountGroup200Response> response = apiInstance.DeleteAccountGroupWithHttpInfo(groupId);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling AccountGroupsApi.DeleteAccountGroupWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **groupId** | **string** |  |  |

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
| **200** | Deleted |  -  |
| **401** | Unauthorized |  -  |
| **404** | Resource not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="listaccountgroups"></a>
# **ListAccountGroups**
> ListAccountGroups200Response ListAccountGroups ()

List groups

Returns all account groups for the authenticated user, including group names and associated account IDs.

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
    public class ListAccountGroupsExample
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
            var apiInstance = new AccountGroupsApi(httpClient, config, httpClientHandler);

            try
            {
                // List groups
                ListAccountGroups200Response result = apiInstance.ListAccountGroups();
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling AccountGroupsApi.ListAccountGroups: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the ListAccountGroupsWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // List groups
    ApiResponse<ListAccountGroups200Response> response = apiInstance.ListAccountGroupsWithHttpInfo();
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling AccountGroupsApi.ListAccountGroupsWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters
This endpoint does not need any parameter.
### Return type

[**ListAccountGroups200Response**](ListAccountGroups200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Groups |  -  |
| **401** | Unauthorized |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="updateaccountgroup"></a>
# **UpdateAccountGroup**
> UpdateAccountGroup200Response UpdateAccountGroup (string groupId, UpdateAccountGroupRequest updateAccountGroupRequest)

Update group

Updates the name or account list of an existing group. You can rename the group, change its accounts, or both.

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
    public class UpdateAccountGroupExample
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
            var apiInstance = new AccountGroupsApi(httpClient, config, httpClientHandler);
            var groupId = "groupId_example";  // string | 
            var updateAccountGroupRequest = new UpdateAccountGroupRequest(); // UpdateAccountGroupRequest | 

            try
            {
                // Update group
                UpdateAccountGroup200Response result = apiInstance.UpdateAccountGroup(groupId, updateAccountGroupRequest);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling AccountGroupsApi.UpdateAccountGroup: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the UpdateAccountGroupWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Update group
    ApiResponse<UpdateAccountGroup200Response> response = apiInstance.UpdateAccountGroupWithHttpInfo(groupId, updateAccountGroupRequest);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling AccountGroupsApi.UpdateAccountGroupWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **groupId** | **string** |  |  |
| **updateAccountGroupRequest** | [**UpdateAccountGroupRequest**](UpdateAccountGroupRequest.md) |  |  |

### Return type

[**UpdateAccountGroup200Response**](UpdateAccountGroup200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Updated |  -  |
| **401** | Unauthorized |  -  |
| **404** | Resource not found |  -  |
| **409** | Group name already exists |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

