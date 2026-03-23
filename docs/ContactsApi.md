# Late.Api.ContactsApi

All URIs are relative to *https://zernio.com/api*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**BulkCreateContacts**](ContactsApi.md#bulkcreatecontacts) | **POST** /v1/contacts/bulk | Bulk create contacts |
| [**CreateContact**](ContactsApi.md#createcontact) | **POST** /v1/contacts | Create a contact |
| [**DeleteContact**](ContactsApi.md#deletecontact) | **DELETE** /v1/contacts/{contactId} | Delete a contact |
| [**GetContact**](ContactsApi.md#getcontact) | **GET** /v1/contacts/{contactId} | Get contact with channels |
| [**GetContactChannels**](ContactsApi.md#getcontactchannels) | **GET** /v1/contacts/{contactId}/channels | List channels for a contact |
| [**ListContacts**](ContactsApi.md#listcontacts) | **GET** /v1/contacts | List contacts |
| [**UpdateContact**](ContactsApi.md#updatecontact) | **PATCH** /v1/contacts/{contactId} | Update a contact |

<a id="bulkcreatecontacts"></a>
# **BulkCreateContacts**
> void BulkCreateContacts (BulkCreateContactsRequest bulkCreateContactsRequest)

Bulk create contacts

Import up to 1000 contacts at a time. Skips duplicates.

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
    public class BulkCreateContactsExample
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
            var apiInstance = new ContactsApi(httpClient, config, httpClientHandler);
            var bulkCreateContactsRequest = new BulkCreateContactsRequest(); // BulkCreateContactsRequest | 

            try
            {
                // Bulk create contacts
                apiInstance.BulkCreateContacts(bulkCreateContactsRequest);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling ContactsApi.BulkCreateContacts: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the BulkCreateContactsWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Bulk create contacts
    apiInstance.BulkCreateContactsWithHttpInfo(bulkCreateContactsRequest);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling ContactsApi.BulkCreateContactsWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **bulkCreateContactsRequest** | [**BulkCreateContactsRequest**](BulkCreateContactsRequest.md) |  |  |

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
| **200** | Bulk import results |  -  |
| **401** | Unauthorized |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="createcontact"></a>
# **CreateContact**
> void CreateContact (CreateContactRequest createContactRequest)

Create a contact

Create a new contact. Optionally create a platform channel in the same request by providing accountId, platform, and platformIdentifier.

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
    public class CreateContactExample
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
            var apiInstance = new ContactsApi(httpClient, config, httpClientHandler);
            var createContactRequest = new CreateContactRequest(); // CreateContactRequest | 

            try
            {
                // Create a contact
                apiInstance.CreateContact(createContactRequest);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling ContactsApi.CreateContact: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the CreateContactWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Create a contact
    apiInstance.CreateContactWithHttpInfo(createContactRequest);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling ContactsApi.CreateContactWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **createContactRequest** | [**CreateContactRequest**](CreateContactRequest.md) |  |  |

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
| **200** | Contact created |  -  |
| **401** | Unauthorized |  -  |
| **409** | Duplicate contact |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="deletecontact"></a>
# **DeleteContact**
> void DeleteContact (string contactId)

Delete a contact

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
    public class DeleteContactExample
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
            var apiInstance = new ContactsApi(httpClient, config, httpClientHandler);
            var contactId = "contactId_example";  // string | 

            try
            {
                // Delete a contact
                apiInstance.DeleteContact(contactId);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling ContactsApi.DeleteContact: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the DeleteContactWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Delete a contact
    apiInstance.DeleteContactWithHttpInfo(contactId);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling ContactsApi.DeleteContactWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **contactId** | **string** |  |  |

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
| **200** | Contact deleted |  -  |
| **401** | Unauthorized |  -  |
| **404** | Resource not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="getcontact"></a>
# **GetContact**
> void GetContact (string contactId)

Get contact with channels

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
    public class GetContactExample
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
            var apiInstance = new ContactsApi(httpClient, config, httpClientHandler);
            var contactId = "contactId_example";  // string | 

            try
            {
                // Get contact with channels
                apiInstance.GetContact(contactId);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling ContactsApi.GetContact: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the GetContactWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Get contact with channels
    apiInstance.GetContactWithHttpInfo(contactId);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling ContactsApi.GetContactWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **contactId** | **string** |  |  |

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
| **200** | Contact with channels |  -  |
| **401** | Unauthorized |  -  |
| **404** | Resource not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="getcontactchannels"></a>
# **GetContactChannels**
> void GetContactChannels (string contactId)

List channels for a contact

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
    public class GetContactChannelsExample
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
            var apiInstance = new ContactsApi(httpClient, config, httpClientHandler);
            var contactId = "contactId_example";  // string | 

            try
            {
                // List channels for a contact
                apiInstance.GetContactChannels(contactId);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling ContactsApi.GetContactChannels: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the GetContactChannelsWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // List channels for a contact
    apiInstance.GetContactChannelsWithHttpInfo(contactId);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling ContactsApi.GetContactChannelsWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **contactId** | **string** |  |  |

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
| **200** | List of contact channels |  -  |
| **401** | Unauthorized |  -  |
| **404** | Resource not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="listcontacts"></a>
# **ListContacts**
> void ListContacts (string? profileId = null, string? search = null, string? tag = null, string? platform = null, string? isSubscribed = null, int? limit = null, int? skip = null)

List contacts

List and search contacts for a profile. Supports filtering by tags, platform, subscription status, and full-text search.

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
    public class ListContactsExample
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
            var apiInstance = new ContactsApi(httpClient, config, httpClientHandler);
            var profileId = "profileId_example";  // string? | Filter by profile. Omit to list across all profiles (optional) 
            var search = "search_example";  // string? |  (optional) 
            var tag = "tag_example";  // string? |  (optional) 
            var platform = "instagram";  // string? |  (optional) 
            var isSubscribed = "true";  // string? |  (optional) 
            var limit = 50;  // int? |  (optional)  (default to 50)
            var skip = 0;  // int? |  (optional)  (default to 0)

            try
            {
                // List contacts
                apiInstance.ListContacts(profileId, search, tag, platform, isSubscribed, limit, skip);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling ContactsApi.ListContacts: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the ListContactsWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // List contacts
    apiInstance.ListContactsWithHttpInfo(profileId, search, tag, platform, isSubscribed, limit, skip);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling ContactsApi.ListContactsWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **profileId** | **string?** | Filter by profile. Omit to list across all profiles | [optional]  |
| **search** | **string?** |  | [optional]  |
| **tag** | **string?** |  | [optional]  |
| **platform** | **string?** |  | [optional]  |
| **isSubscribed** | **string?** |  | [optional]  |
| **limit** | **int?** |  | [optional] [default to 50] |
| **skip** | **int?** |  | [optional] [default to 0] |

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
| **200** | Contacts list with pagination and filter metadata |  -  |
| **401** | Unauthorized |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="updatecontact"></a>
# **UpdateContact**
> void UpdateContact (string contactId, UpdateContactRequest? updateContactRequest = null)

Update a contact

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
    public class UpdateContactExample
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
            var apiInstance = new ContactsApi(httpClient, config, httpClientHandler);
            var contactId = "contactId_example";  // string | 
            var updateContactRequest = new UpdateContactRequest?(); // UpdateContactRequest? |  (optional) 

            try
            {
                // Update a contact
                apiInstance.UpdateContact(contactId, updateContactRequest);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling ContactsApi.UpdateContact: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the UpdateContactWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Update a contact
    apiInstance.UpdateContactWithHttpInfo(contactId, updateContactRequest);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling ContactsApi.UpdateContactWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **contactId** | **string** |  |  |
| **updateContactRequest** | [**UpdateContactRequest?**](UpdateContactRequest?.md) |  | [optional]  |

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
| **200** | Contact updated |  -  |
| **401** | Unauthorized |  -  |
| **404** | Resource not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

