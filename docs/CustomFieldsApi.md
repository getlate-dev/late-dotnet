# Late.Api.CustomFieldsApi

All URIs are relative to *https://zernio.com/api*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**ClearContactFieldValue**](CustomFieldsApi.md#clearcontactfieldvalue) | **DELETE** /v1/contacts/{contactId}/fields/{slug} | Clear a custom field value |
| [**CreateCustomField**](CustomFieldsApi.md#createcustomfield) | **POST** /v1/custom-fields | Create a custom field definition |
| [**DeleteCustomField**](CustomFieldsApi.md#deletecustomfield) | **DELETE** /v1/custom-fields/{fieldId} | Delete a custom field definition |
| [**ListCustomFields**](CustomFieldsApi.md#listcustomfields) | **GET** /v1/custom-fields | List custom field definitions |
| [**SetContactFieldValue**](CustomFieldsApi.md#setcontactfieldvalue) | **PUT** /v1/contacts/{contactId}/fields/{slug} | Set a custom field value |
| [**UpdateCustomField**](CustomFieldsApi.md#updatecustomfield) | **PATCH** /v1/custom-fields/{fieldId} | Update a custom field definition |

<a id="clearcontactfieldvalue"></a>
# **ClearContactFieldValue**
> void ClearContactFieldValue (string contactId, string slug)

Clear a custom field value

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
    public class ClearContactFieldValueExample
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
            var apiInstance = new CustomFieldsApi(httpClient, config, httpClientHandler);
            var contactId = "contactId_example";  // string | 
            var slug = "slug_example";  // string | 

            try
            {
                // Clear a custom field value
                apiInstance.ClearContactFieldValue(contactId, slug);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling CustomFieldsApi.ClearContactFieldValue: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the ClearContactFieldValueWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Clear a custom field value
    apiInstance.ClearContactFieldValueWithHttpInfo(contactId, slug);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling CustomFieldsApi.ClearContactFieldValueWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **contactId** | **string** |  |  |
| **slug** | **string** |  |  |

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
| **200** | Field value cleared |  -  |
| **401** | Unauthorized |  -  |
| **404** | Resource not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="createcustomfield"></a>
# **CreateCustomField**
> void CreateCustomField (CreateCustomFieldRequest createCustomFieldRequest)

Create a custom field definition

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
    public class CreateCustomFieldExample
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
            var apiInstance = new CustomFieldsApi(httpClient, config, httpClientHandler);
            var createCustomFieldRequest = new CreateCustomFieldRequest(); // CreateCustomFieldRequest | 

            try
            {
                // Create a custom field definition
                apiInstance.CreateCustomField(createCustomFieldRequest);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling CustomFieldsApi.CreateCustomField: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the CreateCustomFieldWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Create a custom field definition
    apiInstance.CreateCustomFieldWithHttpInfo(createCustomFieldRequest);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling CustomFieldsApi.CreateCustomFieldWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **createCustomFieldRequest** | [**CreateCustomFieldRequest**](CreateCustomFieldRequest.md) |  |  |

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
| **200** | Custom field created |  -  |
| **401** | Unauthorized |  -  |
| **409** | Duplicate slug |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="deletecustomfield"></a>
# **DeleteCustomField**
> void DeleteCustomField (string fieldId)

Delete a custom field definition

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
    public class DeleteCustomFieldExample
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
            var apiInstance = new CustomFieldsApi(httpClient, config, httpClientHandler);
            var fieldId = "fieldId_example";  // string | 

            try
            {
                // Delete a custom field definition
                apiInstance.DeleteCustomField(fieldId);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling CustomFieldsApi.DeleteCustomField: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the DeleteCustomFieldWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Delete a custom field definition
    apiInstance.DeleteCustomFieldWithHttpInfo(fieldId);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling CustomFieldsApi.DeleteCustomFieldWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **fieldId** | **string** |  |  |

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
| **200** | Custom field deleted |  -  |
| **401** | Unauthorized |  -  |
| **404** | Resource not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="listcustomfields"></a>
# **ListCustomFields**
> void ListCustomFields (string? profileId = null)

List custom field definitions

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
    public class ListCustomFieldsExample
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
            var apiInstance = new CustomFieldsApi(httpClient, config, httpClientHandler);
            var profileId = "profileId_example";  // string? | Filter by profile. Omit to list across all profiles (optional) 

            try
            {
                // List custom field definitions
                apiInstance.ListCustomFields(profileId);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling CustomFieldsApi.ListCustomFields: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the ListCustomFieldsWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // List custom field definitions
    apiInstance.ListCustomFieldsWithHttpInfo(profileId);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling CustomFieldsApi.ListCustomFieldsWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **profileId** | **string?** | Filter by profile. Omit to list across all profiles | [optional]  |

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
| **200** | List of custom field definitions |  -  |
| **401** | Unauthorized |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="setcontactfieldvalue"></a>
# **SetContactFieldValue**
> void SetContactFieldValue (string contactId, string slug, SetContactFieldValueRequest setContactFieldValueRequest)

Set a custom field value

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
    public class SetContactFieldValueExample
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
            var apiInstance = new CustomFieldsApi(httpClient, config, httpClientHandler);
            var contactId = "contactId_example";  // string | 
            var slug = "slug_example";  // string | 
            var setContactFieldValueRequest = new SetContactFieldValueRequest(); // SetContactFieldValueRequest | 

            try
            {
                // Set a custom field value
                apiInstance.SetContactFieldValue(contactId, slug, setContactFieldValueRequest);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling CustomFieldsApi.SetContactFieldValue: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the SetContactFieldValueWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Set a custom field value
    apiInstance.SetContactFieldValueWithHttpInfo(contactId, slug, setContactFieldValueRequest);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling CustomFieldsApi.SetContactFieldValueWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **contactId** | **string** |  |  |
| **slug** | **string** |  |  |
| **setContactFieldValueRequest** | [**SetContactFieldValueRequest**](SetContactFieldValueRequest.md) |  |  |

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
| **200** | Field value set |  -  |
| **401** | Unauthorized |  -  |
| **404** | Resource not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="updatecustomfield"></a>
# **UpdateCustomField**
> void UpdateCustomField (string fieldId, UpdateCustomFieldRequest? updateCustomFieldRequest = null)

Update a custom field definition

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
    public class UpdateCustomFieldExample
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
            var apiInstance = new CustomFieldsApi(httpClient, config, httpClientHandler);
            var fieldId = "fieldId_example";  // string | 
            var updateCustomFieldRequest = new UpdateCustomFieldRequest?(); // UpdateCustomFieldRequest? |  (optional) 

            try
            {
                // Update a custom field definition
                apiInstance.UpdateCustomField(fieldId, updateCustomFieldRequest);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling CustomFieldsApi.UpdateCustomField: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the UpdateCustomFieldWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Update a custom field definition
    apiInstance.UpdateCustomFieldWithHttpInfo(fieldId, updateCustomFieldRequest);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling CustomFieldsApi.UpdateCustomFieldWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **fieldId** | **string** |  |  |
| **updateCustomFieldRequest** | [**UpdateCustomFieldRequest?**](UpdateCustomFieldRequest?.md) |  | [optional]  |

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
| **200** | Custom field updated |  -  |
| **401** | Unauthorized |  -  |
| **404** | Resource not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

