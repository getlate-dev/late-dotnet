# Late.Api.WhatsAppApi

All URIs are relative to *https://getlate.dev/api*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**AddWhatsAppBroadcastRecipients**](WhatsAppApi.md#addwhatsappbroadcastrecipients) | **PATCH** /v1/whatsapp/broadcasts/{broadcastId}/recipients | Add recipients |
| [**BulkDeleteWhatsAppContacts**](WhatsAppApi.md#bulkdeletewhatsappcontacts) | **DELETE** /v1/whatsapp/contacts/bulk | Bulk delete contacts |
| [**BulkUpdateWhatsAppContacts**](WhatsAppApi.md#bulkupdatewhatsappcontacts) | **POST** /v1/whatsapp/contacts/bulk | Bulk update contacts |
| [**CancelWhatsAppBroadcastSchedule**](WhatsAppApi.md#cancelwhatsappbroadcastschedule) | **DELETE** /v1/whatsapp/broadcasts/{broadcastId}/schedule | Cancel scheduled broadcast |
| [**CreateWhatsAppBroadcast**](WhatsAppApi.md#createwhatsappbroadcast) | **POST** /v1/whatsapp/broadcasts | Create broadcast |
| [**CreateWhatsAppContact**](WhatsAppApi.md#createwhatsappcontact) | **POST** /v1/whatsapp/contacts | Create contact |
| [**CreateWhatsAppTemplate**](WhatsAppApi.md#createwhatsapptemplate) | **POST** /v1/whatsapp/templates | Create template |
| [**DeleteWhatsAppBroadcast**](WhatsAppApi.md#deletewhatsappbroadcast) | **DELETE** /v1/whatsapp/broadcasts/{broadcastId} | Delete broadcast |
| [**DeleteWhatsAppContact**](WhatsAppApi.md#deletewhatsappcontact) | **DELETE** /v1/whatsapp/contacts/{contactId} | Delete contact |
| [**DeleteWhatsAppGroup**](WhatsAppApi.md#deletewhatsappgroup) | **DELETE** /v1/whatsapp/groups | Delete group |
| [**DeleteWhatsAppTemplate**](WhatsAppApi.md#deletewhatsapptemplate) | **DELETE** /v1/whatsapp/templates/{templateName} | Delete template |
| [**GetWhatsAppBroadcast**](WhatsAppApi.md#getwhatsappbroadcast) | **GET** /v1/whatsapp/broadcasts/{broadcastId} | Get broadcast |
| [**GetWhatsAppBroadcastRecipients**](WhatsAppApi.md#getwhatsappbroadcastrecipients) | **GET** /v1/whatsapp/broadcasts/{broadcastId}/recipients | List recipients |
| [**GetWhatsAppBroadcasts**](WhatsAppApi.md#getwhatsappbroadcasts) | **GET** /v1/whatsapp/broadcasts | List broadcasts |
| [**GetWhatsAppBusinessProfile**](WhatsAppApi.md#getwhatsappbusinessprofile) | **GET** /v1/whatsapp/business-profile | Get business profile |
| [**GetWhatsAppContact**](WhatsAppApi.md#getwhatsappcontact) | **GET** /v1/whatsapp/contacts/{contactId} | Get contact |
| [**GetWhatsAppContacts**](WhatsAppApi.md#getwhatsappcontacts) | **GET** /v1/whatsapp/contacts | List contacts |
| [**GetWhatsAppGroups**](WhatsAppApi.md#getwhatsappgroups) | **GET** /v1/whatsapp/groups | List contact groups |
| [**GetWhatsAppTemplate**](WhatsAppApi.md#getwhatsapptemplate) | **GET** /v1/whatsapp/templates/{templateName} | Get template |
| [**GetWhatsAppTemplates**](WhatsAppApi.md#getwhatsapptemplates) | **GET** /v1/whatsapp/templates | List templates |
| [**ImportWhatsAppContacts**](WhatsAppApi.md#importwhatsappcontacts) | **POST** /v1/whatsapp/contacts/import | Bulk import contacts |
| [**RemoveWhatsAppBroadcastRecipients**](WhatsAppApi.md#removewhatsappbroadcastrecipients) | **DELETE** /v1/whatsapp/broadcasts/{broadcastId}/recipients | Remove recipients |
| [**RenameWhatsAppGroup**](WhatsAppApi.md#renamewhatsappgroup) | **POST** /v1/whatsapp/groups | Rename group |
| [**ScheduleWhatsAppBroadcast**](WhatsAppApi.md#schedulewhatsappbroadcast) | **POST** /v1/whatsapp/broadcasts/{broadcastId}/schedule | Schedule broadcast |
| [**SendWhatsAppBroadcast**](WhatsAppApi.md#sendwhatsappbroadcast) | **POST** /v1/whatsapp/broadcasts/{broadcastId}/send | Send broadcast |
| [**SendWhatsAppBulk**](WhatsAppApi.md#sendwhatsappbulk) | **POST** /v1/whatsapp/bulk | Bulk send template messages |
| [**UpdateWhatsAppBusinessProfile**](WhatsAppApi.md#updatewhatsappbusinessprofile) | **POST** /v1/whatsapp/business-profile | Update business profile |
| [**UpdateWhatsAppContact**](WhatsAppApi.md#updatewhatsappcontact) | **PUT** /v1/whatsapp/contacts/{contactId} | Update contact |
| [**UpdateWhatsAppTemplate**](WhatsAppApi.md#updatewhatsapptemplate) | **PATCH** /v1/whatsapp/templates/{templateName} | Update template |

<a id="addwhatsappbroadcastrecipients"></a>
# **AddWhatsAppBroadcastRecipients**
> AddWhatsAppBroadcastRecipients200Response AddWhatsAppBroadcastRecipients (string broadcastId, AddWhatsAppBroadcastRecipientsRequest addWhatsAppBroadcastRecipientsRequest)

Add recipients

Add recipients to a draft broadcast. Maximum 1000 recipients per request. Duplicate phone numbers are automatically skipped. 

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
    public class AddWhatsAppBroadcastRecipientsExample
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
            var apiInstance = new WhatsAppApi(httpClient, config, httpClientHandler);
            var broadcastId = "broadcastId_example";  // string | Broadcast ID
            var addWhatsAppBroadcastRecipientsRequest = new AddWhatsAppBroadcastRecipientsRequest(); // AddWhatsAppBroadcastRecipientsRequest | 

            try
            {
                // Add recipients
                AddWhatsAppBroadcastRecipients200Response result = apiInstance.AddWhatsAppBroadcastRecipients(broadcastId, addWhatsAppBroadcastRecipientsRequest);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling WhatsAppApi.AddWhatsAppBroadcastRecipients: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the AddWhatsAppBroadcastRecipientsWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Add recipients
    ApiResponse<AddWhatsAppBroadcastRecipients200Response> response = apiInstance.AddWhatsAppBroadcastRecipientsWithHttpInfo(broadcastId, addWhatsAppBroadcastRecipientsRequest);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling WhatsAppApi.AddWhatsAppBroadcastRecipientsWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **broadcastId** | **string** | Broadcast ID |  |
| **addWhatsAppBroadcastRecipientsRequest** | [**AddWhatsAppBroadcastRecipientsRequest**](AddWhatsAppBroadcastRecipientsRequest.md) |  |  |

### Return type

[**AddWhatsAppBroadcastRecipients200Response**](AddWhatsAppBroadcastRecipients200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Recipients added successfully |  -  |
| **400** | Validation error or broadcast not in draft status |  -  |
| **401** | Unauthorized |  -  |
| **404** | Resource not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="bulkdeletewhatsappcontacts"></a>
# **BulkDeleteWhatsAppContacts**
> BulkDeleteWhatsAppContacts200Response BulkDeleteWhatsAppContacts (BulkDeleteWhatsAppContactsRequest bulkDeleteWhatsAppContactsRequest)

Bulk delete contacts

Permanently delete multiple contacts at once (max 500 per request).

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
    public class BulkDeleteWhatsAppContactsExample
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
            var apiInstance = new WhatsAppApi(httpClient, config, httpClientHandler);
            var bulkDeleteWhatsAppContactsRequest = new BulkDeleteWhatsAppContactsRequest(); // BulkDeleteWhatsAppContactsRequest | 

            try
            {
                // Bulk delete contacts
                BulkDeleteWhatsAppContacts200Response result = apiInstance.BulkDeleteWhatsAppContacts(bulkDeleteWhatsAppContactsRequest);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling WhatsAppApi.BulkDeleteWhatsAppContacts: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the BulkDeleteWhatsAppContactsWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Bulk delete contacts
    ApiResponse<BulkDeleteWhatsAppContacts200Response> response = apiInstance.BulkDeleteWhatsAppContactsWithHttpInfo(bulkDeleteWhatsAppContactsRequest);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling WhatsAppApi.BulkDeleteWhatsAppContactsWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **bulkDeleteWhatsAppContactsRequest** | [**BulkDeleteWhatsAppContactsRequest**](BulkDeleteWhatsAppContactsRequest.md) |  |  |

### Return type

[**BulkDeleteWhatsAppContacts200Response**](BulkDeleteWhatsAppContacts200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Bulk delete completed |  -  |
| **400** | contactIds array is required |  -  |
| **401** | Unauthorized |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="bulkupdatewhatsappcontacts"></a>
# **BulkUpdateWhatsAppContacts**
> BulkUpdateWhatsAppContacts200Response BulkUpdateWhatsAppContacts (BulkUpdateWhatsAppContactsRequest bulkUpdateWhatsAppContactsRequest)

Bulk update contacts

Perform bulk operations on multiple contacts (max 500 per request). Supported actions: addTags, removeTags, addGroups, removeGroups, optIn, optOut, block, unblock. 

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
    public class BulkUpdateWhatsAppContactsExample
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
            var apiInstance = new WhatsAppApi(httpClient, config, httpClientHandler);
            var bulkUpdateWhatsAppContactsRequest = new BulkUpdateWhatsAppContactsRequest(); // BulkUpdateWhatsAppContactsRequest | 

            try
            {
                // Bulk update contacts
                BulkUpdateWhatsAppContacts200Response result = apiInstance.BulkUpdateWhatsAppContacts(bulkUpdateWhatsAppContactsRequest);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling WhatsAppApi.BulkUpdateWhatsAppContacts: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the BulkUpdateWhatsAppContactsWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Bulk update contacts
    ApiResponse<BulkUpdateWhatsAppContacts200Response> response = apiInstance.BulkUpdateWhatsAppContactsWithHttpInfo(bulkUpdateWhatsAppContactsRequest);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling WhatsAppApi.BulkUpdateWhatsAppContactsWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **bulkUpdateWhatsAppContactsRequest** | [**BulkUpdateWhatsAppContactsRequest**](BulkUpdateWhatsAppContactsRequest.md) |  |  |

### Return type

[**BulkUpdateWhatsAppContacts200Response**](BulkUpdateWhatsAppContacts200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Bulk update completed |  -  |
| **400** | Validation error (invalid action |  -  |
| **401** | Unauthorized |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="cancelwhatsappbroadcastschedule"></a>
# **CancelWhatsAppBroadcastSchedule**
> CancelWhatsAppBroadcastSchedule200Response CancelWhatsAppBroadcastSchedule (string broadcastId)

Cancel scheduled broadcast

Cancel a scheduled broadcast and return it to draft status. Only broadcasts in scheduled status can be cancelled. 

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
    public class CancelWhatsAppBroadcastScheduleExample
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
            var apiInstance = new WhatsAppApi(httpClient, config, httpClientHandler);
            var broadcastId = "broadcastId_example";  // string | Broadcast ID

            try
            {
                // Cancel scheduled broadcast
                CancelWhatsAppBroadcastSchedule200Response result = apiInstance.CancelWhatsAppBroadcastSchedule(broadcastId);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling WhatsAppApi.CancelWhatsAppBroadcastSchedule: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the CancelWhatsAppBroadcastScheduleWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Cancel scheduled broadcast
    ApiResponse<CancelWhatsAppBroadcastSchedule200Response> response = apiInstance.CancelWhatsAppBroadcastScheduleWithHttpInfo(broadcastId);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling WhatsAppApi.CancelWhatsAppBroadcastScheduleWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **broadcastId** | **string** | Broadcast ID |  |

### Return type

[**CancelWhatsAppBroadcastSchedule200Response**](CancelWhatsAppBroadcastSchedule200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Schedule cancelled, broadcast returned to draft |  -  |
| **400** | Broadcast is not scheduled |  -  |
| **401** | Unauthorized |  -  |
| **404** | Resource not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="createwhatsappbroadcast"></a>
# **CreateWhatsAppBroadcast**
> CreateWhatsAppBroadcast200Response CreateWhatsAppBroadcast (CreateWhatsAppBroadcastRequest createWhatsAppBroadcastRequest)

Create broadcast

Create a new draft broadcast. Optionally include initial recipients. After creation, add recipients and then send or schedule the broadcast. 

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
    public class CreateWhatsAppBroadcastExample
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
            var apiInstance = new WhatsAppApi(httpClient, config, httpClientHandler);
            var createWhatsAppBroadcastRequest = new CreateWhatsAppBroadcastRequest(); // CreateWhatsAppBroadcastRequest | 

            try
            {
                // Create broadcast
                CreateWhatsAppBroadcast200Response result = apiInstance.CreateWhatsAppBroadcast(createWhatsAppBroadcastRequest);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling WhatsAppApi.CreateWhatsAppBroadcast: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the CreateWhatsAppBroadcastWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Create broadcast
    ApiResponse<CreateWhatsAppBroadcast200Response> response = apiInstance.CreateWhatsAppBroadcastWithHttpInfo(createWhatsAppBroadcastRequest);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling WhatsAppApi.CreateWhatsAppBroadcastWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **createWhatsAppBroadcastRequest** | [**CreateWhatsAppBroadcastRequest**](CreateWhatsAppBroadcastRequest.md) |  |  |

### Return type

[**CreateWhatsAppBroadcast200Response**](CreateWhatsAppBroadcast200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Broadcast created as draft |  -  |
| **400** | Validation error (missing name |  -  |
| **401** | Unauthorized |  -  |
| **404** | WhatsApp account not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="createwhatsappcontact"></a>
# **CreateWhatsAppContact**
> CreateWhatsAppContact200Response CreateWhatsAppContact (CreateWhatsAppContactRequest createWhatsAppContactRequest)

Create contact

Create a new WhatsApp contact. Phone number must be unique per account and in E.164 format (e.g., +1234567890). 

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
    public class CreateWhatsAppContactExample
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
            var apiInstance = new WhatsAppApi(httpClient, config, httpClientHandler);
            var createWhatsAppContactRequest = new CreateWhatsAppContactRequest(); // CreateWhatsAppContactRequest | 

            try
            {
                // Create contact
                CreateWhatsAppContact200Response result = apiInstance.CreateWhatsAppContact(createWhatsAppContactRequest);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling WhatsAppApi.CreateWhatsAppContact: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the CreateWhatsAppContactWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Create contact
    ApiResponse<CreateWhatsAppContact200Response> response = apiInstance.CreateWhatsAppContactWithHttpInfo(createWhatsAppContactRequest);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling WhatsAppApi.CreateWhatsAppContactWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **createWhatsAppContactRequest** | [**CreateWhatsAppContactRequest**](CreateWhatsAppContactRequest.md) |  |  |

### Return type

[**CreateWhatsAppContact200Response**](CreateWhatsAppContact200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Contact created successfully |  -  |
| **400** | Validation error (missing fields |  -  |
| **401** | Unauthorized |  -  |
| **404** | WhatsApp account not found |  -  |
| **409** | Contact with this phone number already exists |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="createwhatsapptemplate"></a>
# **CreateWhatsAppTemplate**
> CreateWhatsAppTemplate200Response CreateWhatsAppTemplate (CreateWhatsAppTemplateRequest createWhatsAppTemplateRequest)

Create template

Create a new message template. Template names must be lowercase, start with a letter, and contain only letters, numbers, and underscores. Templates are submitted to Meta for review. 

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
    public class CreateWhatsAppTemplateExample
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
            var apiInstance = new WhatsAppApi(httpClient, config, httpClientHandler);
            var createWhatsAppTemplateRequest = new CreateWhatsAppTemplateRequest(); // CreateWhatsAppTemplateRequest | 

            try
            {
                // Create template
                CreateWhatsAppTemplate200Response result = apiInstance.CreateWhatsAppTemplate(createWhatsAppTemplateRequest);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling WhatsAppApi.CreateWhatsAppTemplate: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the CreateWhatsAppTemplateWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Create template
    ApiResponse<CreateWhatsAppTemplate200Response> response = apiInstance.CreateWhatsAppTemplateWithHttpInfo(createWhatsAppTemplateRequest);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling WhatsAppApi.CreateWhatsAppTemplateWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **createWhatsAppTemplateRequest** | [**CreateWhatsAppTemplateRequest**](CreateWhatsAppTemplateRequest.md) |  |  |

### Return type

[**CreateWhatsAppTemplate200Response**](CreateWhatsAppTemplate200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Template created and submitted for review |  -  |
| **400** | Validation error (invalid name format |  -  |
| **401** | Unauthorized |  -  |
| **404** | WhatsApp account not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="deletewhatsappbroadcast"></a>
# **DeleteWhatsAppBroadcast**
> UnpublishPost200Response DeleteWhatsAppBroadcast (string broadcastId)

Delete broadcast

Delete a broadcast. Only draft or cancelled broadcasts can be deleted.

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
    public class DeleteWhatsAppBroadcastExample
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
            var apiInstance = new WhatsAppApi(httpClient, config, httpClientHandler);
            var broadcastId = "broadcastId_example";  // string | Broadcast ID

            try
            {
                // Delete broadcast
                UnpublishPost200Response result = apiInstance.DeleteWhatsAppBroadcast(broadcastId);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling WhatsAppApi.DeleteWhatsAppBroadcast: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the DeleteWhatsAppBroadcastWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Delete broadcast
    ApiResponse<UnpublishPost200Response> response = apiInstance.DeleteWhatsAppBroadcastWithHttpInfo(broadcastId);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling WhatsAppApi.DeleteWhatsAppBroadcastWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **broadcastId** | **string** | Broadcast ID |  |

### Return type

[**UnpublishPost200Response**](UnpublishPost200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Broadcast deleted successfully |  -  |
| **400** | Can only delete draft or cancelled broadcasts |  -  |
| **401** | Unauthorized |  -  |
| **404** | Resource not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="deletewhatsappcontact"></a>
# **DeleteWhatsAppContact**
> UnpublishPost200Response DeleteWhatsAppContact (string contactId)

Delete contact

Permanently delete a WhatsApp contact.

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
    public class DeleteWhatsAppContactExample
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
            var apiInstance = new WhatsAppApi(httpClient, config, httpClientHandler);
            var contactId = "contactId_example";  // string | Contact ID

            try
            {
                // Delete contact
                UnpublishPost200Response result = apiInstance.DeleteWhatsAppContact(contactId);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling WhatsAppApi.DeleteWhatsAppContact: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the DeleteWhatsAppContactWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Delete contact
    ApiResponse<UnpublishPost200Response> response = apiInstance.DeleteWhatsAppContactWithHttpInfo(contactId);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling WhatsAppApi.DeleteWhatsAppContactWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **contactId** | **string** | Contact ID |  |

### Return type

[**UnpublishPost200Response**](UnpublishPost200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Contact deleted successfully |  -  |
| **401** | Unauthorized |  -  |
| **404** | Resource not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="deletewhatsappgroup"></a>
# **DeleteWhatsAppGroup**
> RenameWhatsAppGroup200Response DeleteWhatsAppGroup (DeleteWhatsAppGroupRequest deleteWhatsAppGroupRequest)

Delete group

Delete a contact group. This removes the group from all contacts but does not delete the contacts themselves.

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
    public class DeleteWhatsAppGroupExample
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
            var apiInstance = new WhatsAppApi(httpClient, config, httpClientHandler);
            var deleteWhatsAppGroupRequest = new DeleteWhatsAppGroupRequest(); // DeleteWhatsAppGroupRequest | 

            try
            {
                // Delete group
                RenameWhatsAppGroup200Response result = apiInstance.DeleteWhatsAppGroup(deleteWhatsAppGroupRequest);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling WhatsAppApi.DeleteWhatsAppGroup: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the DeleteWhatsAppGroupWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Delete group
    ApiResponse<RenameWhatsAppGroup200Response> response = apiInstance.DeleteWhatsAppGroupWithHttpInfo(deleteWhatsAppGroupRequest);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling WhatsAppApi.DeleteWhatsAppGroupWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **deleteWhatsAppGroupRequest** | [**DeleteWhatsAppGroupRequest**](DeleteWhatsAppGroupRequest.md) |  |  |

### Return type

[**RenameWhatsAppGroup200Response**](RenameWhatsAppGroup200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Group deleted successfully |  -  |
| **400** | Validation error (missing fields) |  -  |
| **401** | Unauthorized |  -  |
| **404** | WhatsApp account not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="deletewhatsapptemplate"></a>
# **DeleteWhatsAppTemplate**
> UnpublishPost200Response DeleteWhatsAppTemplate (string templateName, string accountId)

Delete template

Permanently delete a message template by name.

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
    public class DeleteWhatsAppTemplateExample
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
            var apiInstance = new WhatsAppApi(httpClient, config, httpClientHandler);
            var templateName = "templateName_example";  // string | Template name
            var accountId = "accountId_example";  // string | WhatsApp social account ID

            try
            {
                // Delete template
                UnpublishPost200Response result = apiInstance.DeleteWhatsAppTemplate(templateName, accountId);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling WhatsAppApi.DeleteWhatsAppTemplate: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the DeleteWhatsAppTemplateWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Delete template
    ApiResponse<UnpublishPost200Response> response = apiInstance.DeleteWhatsAppTemplateWithHttpInfo(templateName, accountId);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling WhatsAppApi.DeleteWhatsAppTemplateWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **templateName** | **string** | Template name |  |
| **accountId** | **string** | WhatsApp social account ID |  |

### Return type

[**UnpublishPost200Response**](UnpublishPost200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Template deleted successfully |  -  |
| **400** | accountId or template name is required |  -  |
| **401** | Unauthorized |  -  |
| **404** | Resource not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="getwhatsappbroadcast"></a>
# **GetWhatsAppBroadcast**
> GetWhatsAppBroadcast200Response GetWhatsAppBroadcast (string broadcastId)

Get broadcast

Retrieve detailed information about a single broadcast including delivery statistics.

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
    public class GetWhatsAppBroadcastExample
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
            var apiInstance = new WhatsAppApi(httpClient, config, httpClientHandler);
            var broadcastId = "broadcastId_example";  // string | Broadcast ID

            try
            {
                // Get broadcast
                GetWhatsAppBroadcast200Response result = apiInstance.GetWhatsAppBroadcast(broadcastId);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling WhatsAppApi.GetWhatsAppBroadcast: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the GetWhatsAppBroadcastWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Get broadcast
    ApiResponse<GetWhatsAppBroadcast200Response> response = apiInstance.GetWhatsAppBroadcastWithHttpInfo(broadcastId);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling WhatsAppApi.GetWhatsAppBroadcastWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **broadcastId** | **string** | Broadcast ID |  |

### Return type

[**GetWhatsAppBroadcast200Response**](GetWhatsAppBroadcast200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Broadcast retrieved successfully |  -  |
| **401** | Unauthorized |  -  |
| **404** | Resource not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="getwhatsappbroadcastrecipients"></a>
# **GetWhatsAppBroadcastRecipients**
> GetWhatsAppBroadcastRecipients200Response GetWhatsAppBroadcastRecipients (string broadcastId, string? status = null, int? limit = null, int? skip = null)

List recipients

List recipients of a broadcast with their delivery status. Supports filtering by delivery status and pagination. 

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
    public class GetWhatsAppBroadcastRecipientsExample
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
            var apiInstance = new WhatsAppApi(httpClient, config, httpClientHandler);
            var broadcastId = "broadcastId_example";  // string | Broadcast ID
            var status = "pending";  // string? | Filter by recipient delivery status (optional) 
            var limit = 100;  // int? | Maximum results (default 100) (optional)  (default to 100)
            var skip = 0;  // int? | Offset for pagination (optional)  (default to 0)

            try
            {
                // List recipients
                GetWhatsAppBroadcastRecipients200Response result = apiInstance.GetWhatsAppBroadcastRecipients(broadcastId, status, limit, skip);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling WhatsAppApi.GetWhatsAppBroadcastRecipients: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the GetWhatsAppBroadcastRecipientsWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // List recipients
    ApiResponse<GetWhatsAppBroadcastRecipients200Response> response = apiInstance.GetWhatsAppBroadcastRecipientsWithHttpInfo(broadcastId, status, limit, skip);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling WhatsAppApi.GetWhatsAppBroadcastRecipientsWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **broadcastId** | **string** | Broadcast ID |  |
| **status** | **string?** | Filter by recipient delivery status | [optional]  |
| **limit** | **int?** | Maximum results (default 100) | [optional] [default to 100] |
| **skip** | **int?** | Offset for pagination | [optional] [default to 0] |

### Return type

[**GetWhatsAppBroadcastRecipients200Response**](GetWhatsAppBroadcastRecipients200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Recipients retrieved successfully |  -  |
| **401** | Unauthorized |  -  |
| **404** | Resource not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="getwhatsappbroadcasts"></a>
# **GetWhatsAppBroadcasts**
> GetWhatsAppBroadcasts200Response GetWhatsAppBroadcasts (string accountId, string? status = null, int? limit = null, int? skip = null)

List broadcasts

List all WhatsApp broadcasts for an account. Returns broadcasts sorted by creation date (newest first) without the full recipients list for performance. 

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
    public class GetWhatsAppBroadcastsExample
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
            var apiInstance = new WhatsAppApi(httpClient, config, httpClientHandler);
            var accountId = "accountId_example";  // string | WhatsApp social account ID
            var status = "draft";  // string? | Filter by broadcast status (optional) 
            var limit = 50;  // int? | Maximum results (default 50) (optional)  (default to 50)
            var skip = 0;  // int? | Offset for pagination (optional)  (default to 0)

            try
            {
                // List broadcasts
                GetWhatsAppBroadcasts200Response result = apiInstance.GetWhatsAppBroadcasts(accountId, status, limit, skip);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling WhatsAppApi.GetWhatsAppBroadcasts: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the GetWhatsAppBroadcastsWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // List broadcasts
    ApiResponse<GetWhatsAppBroadcasts200Response> response = apiInstance.GetWhatsAppBroadcastsWithHttpInfo(accountId, status, limit, skip);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling WhatsAppApi.GetWhatsAppBroadcastsWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **accountId** | **string** | WhatsApp social account ID |  |
| **status** | **string?** | Filter by broadcast status | [optional]  |
| **limit** | **int?** | Maximum results (default 50) | [optional] [default to 50] |
| **skip** | **int?** | Offset for pagination | [optional] [default to 0] |

### Return type

[**GetWhatsAppBroadcasts200Response**](GetWhatsAppBroadcasts200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Broadcasts retrieved successfully |  -  |
| **400** | accountId is required |  -  |
| **401** | Unauthorized |  -  |
| **404** | WhatsApp account not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="getwhatsappbusinessprofile"></a>
# **GetWhatsAppBusinessProfile**
> GetWhatsAppBusinessProfile200Response GetWhatsAppBusinessProfile (string accountId)

Get business profile

Retrieve the WhatsApp Business profile for the account (about, address, description, email, websites, etc.).

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
    public class GetWhatsAppBusinessProfileExample
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
            var apiInstance = new WhatsAppApi(httpClient, config, httpClientHandler);
            var accountId = "accountId_example";  // string | WhatsApp social account ID

            try
            {
                // Get business profile
                GetWhatsAppBusinessProfile200Response result = apiInstance.GetWhatsAppBusinessProfile(accountId);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling WhatsAppApi.GetWhatsAppBusinessProfile: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the GetWhatsAppBusinessProfileWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Get business profile
    ApiResponse<GetWhatsAppBusinessProfile200Response> response = apiInstance.GetWhatsAppBusinessProfileWithHttpInfo(accountId);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling WhatsAppApi.GetWhatsAppBusinessProfileWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **accountId** | **string** | WhatsApp social account ID |  |

### Return type

[**GetWhatsAppBusinessProfile200Response**](GetWhatsAppBusinessProfile200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Business profile retrieved successfully |  -  |
| **400** | accountId is required or phone number ID not found |  -  |
| **401** | Unauthorized |  -  |
| **404** | WhatsApp account not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="getwhatsappcontact"></a>
# **GetWhatsAppContact**
> GetWhatsAppContact200Response GetWhatsAppContact (string contactId)

Get contact

Retrieve a single WhatsApp contact by ID with full details.

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
    public class GetWhatsAppContactExample
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
            var apiInstance = new WhatsAppApi(httpClient, config, httpClientHandler);
            var contactId = "contactId_example";  // string | Contact ID

            try
            {
                // Get contact
                GetWhatsAppContact200Response result = apiInstance.GetWhatsAppContact(contactId);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling WhatsAppApi.GetWhatsAppContact: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the GetWhatsAppContactWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Get contact
    ApiResponse<GetWhatsAppContact200Response> response = apiInstance.GetWhatsAppContactWithHttpInfo(contactId);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling WhatsAppApi.GetWhatsAppContactWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **contactId** | **string** | Contact ID |  |

### Return type

[**GetWhatsAppContact200Response**](GetWhatsAppContact200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Contact retrieved successfully |  -  |
| **401** | Unauthorized |  -  |
| **404** | Resource not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="getwhatsappcontacts"></a>
# **GetWhatsAppContacts**
> GetWhatsAppContacts200Response GetWhatsAppContacts (string accountId, string? search = null, string? tag = null, string? group = null, string? optedIn = null, int? limit = null, int? skip = null)

List contacts

List WhatsApp contacts for an account. Supports filtering by tags, groups, opt-in status, and text search. Returns contacts sorted by name with available filter options. 

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
    public class GetWhatsAppContactsExample
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
            var apiInstance = new WhatsAppApi(httpClient, config, httpClientHandler);
            var accountId = "accountId_example";  // string | WhatsApp social account ID
            var search = "search_example";  // string? | Search contacts by name, phone, email, or company (optional) 
            var tag = "tag_example";  // string? | Filter by tag (optional) 
            var group = "group_example";  // string? | Filter by group (optional) 
            var optedIn = "true";  // string? | Filter by opt-in status (optional) 
            var limit = 50;  // int? | Maximum results (default 50) (optional)  (default to 50)
            var skip = 0;  // int? | Offset for pagination (optional)  (default to 0)

            try
            {
                // List contacts
                GetWhatsAppContacts200Response result = apiInstance.GetWhatsAppContacts(accountId, search, tag, group, optedIn, limit, skip);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling WhatsAppApi.GetWhatsAppContacts: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the GetWhatsAppContactsWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // List contacts
    ApiResponse<GetWhatsAppContacts200Response> response = apiInstance.GetWhatsAppContactsWithHttpInfo(accountId, search, tag, group, optedIn, limit, skip);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling WhatsAppApi.GetWhatsAppContactsWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **accountId** | **string** | WhatsApp social account ID |  |
| **search** | **string?** | Search contacts by name, phone, email, or company | [optional]  |
| **tag** | **string?** | Filter by tag | [optional]  |
| **group** | **string?** | Filter by group | [optional]  |
| **optedIn** | **string?** | Filter by opt-in status | [optional]  |
| **limit** | **int?** | Maximum results (default 50) | [optional] [default to 50] |
| **skip** | **int?** | Offset for pagination | [optional] [default to 0] |

### Return type

[**GetWhatsAppContacts200Response**](GetWhatsAppContacts200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Contacts retrieved successfully |  -  |
| **400** | accountId is required |  -  |
| **401** | Unauthorized |  -  |
| **404** | WhatsApp account not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="getwhatsappgroups"></a>
# **GetWhatsAppGroups**
> GetWhatsAppGroups200Response GetWhatsAppGroups (string accountId)

List contact groups

List all contact groups for a WhatsApp account with contact counts. Groups are derived from the groups field on contacts, not stored as separate documents. 

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
    public class GetWhatsAppGroupsExample
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
            var apiInstance = new WhatsAppApi(httpClient, config, httpClientHandler);
            var accountId = "accountId_example";  // string | WhatsApp social account ID

            try
            {
                // List contact groups
                GetWhatsAppGroups200Response result = apiInstance.GetWhatsAppGroups(accountId);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling WhatsAppApi.GetWhatsAppGroups: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the GetWhatsAppGroupsWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // List contact groups
    ApiResponse<GetWhatsAppGroups200Response> response = apiInstance.GetWhatsAppGroupsWithHttpInfo(accountId);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling WhatsAppApi.GetWhatsAppGroupsWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **accountId** | **string** | WhatsApp social account ID |  |

### Return type

[**GetWhatsAppGroups200Response**](GetWhatsAppGroups200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Groups retrieved successfully |  -  |
| **400** | accountId is required |  -  |
| **401** | Unauthorized |  -  |
| **404** | WhatsApp account not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="getwhatsapptemplate"></a>
# **GetWhatsAppTemplate**
> GetWhatsAppTemplate200Response GetWhatsAppTemplate (string templateName, string accountId)

Get template

Retrieve a single message template by name.

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
    public class GetWhatsAppTemplateExample
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
            var apiInstance = new WhatsAppApi(httpClient, config, httpClientHandler);
            var templateName = "templateName_example";  // string | Template name
            var accountId = "accountId_example";  // string | WhatsApp social account ID

            try
            {
                // Get template
                GetWhatsAppTemplate200Response result = apiInstance.GetWhatsAppTemplate(templateName, accountId);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling WhatsAppApi.GetWhatsAppTemplate: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the GetWhatsAppTemplateWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Get template
    ApiResponse<GetWhatsAppTemplate200Response> response = apiInstance.GetWhatsAppTemplateWithHttpInfo(templateName, accountId);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling WhatsAppApi.GetWhatsAppTemplateWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **templateName** | **string** | Template name |  |
| **accountId** | **string** | WhatsApp social account ID |  |

### Return type

[**GetWhatsAppTemplate200Response**](GetWhatsAppTemplate200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Template retrieved successfully |  -  |
| **400** | accountId is required |  -  |
| **401** | Unauthorized |  -  |
| **404** | Resource not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="getwhatsapptemplates"></a>
# **GetWhatsAppTemplates**
> GetWhatsAppTemplates200Response GetWhatsAppTemplates (string accountId)

List templates

List all message templates for the WhatsApp Business Account (WABA) associated with the given account. Templates are fetched directly from the WhatsApp Cloud API. 

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
    public class GetWhatsAppTemplatesExample
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
            var apiInstance = new WhatsAppApi(httpClient, config, httpClientHandler);
            var accountId = "accountId_example";  // string | WhatsApp social account ID

            try
            {
                // List templates
                GetWhatsAppTemplates200Response result = apiInstance.GetWhatsAppTemplates(accountId);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling WhatsAppApi.GetWhatsAppTemplates: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the GetWhatsAppTemplatesWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // List templates
    ApiResponse<GetWhatsAppTemplates200Response> response = apiInstance.GetWhatsAppTemplatesWithHttpInfo(accountId);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling WhatsAppApi.GetWhatsAppTemplatesWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **accountId** | **string** | WhatsApp social account ID |  |

### Return type

[**GetWhatsAppTemplates200Response**](GetWhatsAppTemplates200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Templates retrieved successfully |  -  |
| **400** | accountId is required or WABA ID not found |  -  |
| **401** | Unauthorized |  -  |
| **404** | WhatsApp account not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="importwhatsappcontacts"></a>
# **ImportWhatsAppContacts**
> ImportWhatsAppContacts200Response ImportWhatsAppContacts (ImportWhatsAppContactsRequest importWhatsAppContactsRequest)

Bulk import contacts

Import up to 1000 contacts at once. Each contact requires a phone number and name. Duplicates are skipped by default. Supports default tags and groups applied to all imported contacts. 

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
    public class ImportWhatsAppContactsExample
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
            var apiInstance = new WhatsAppApi(httpClient, config, httpClientHandler);
            var importWhatsAppContactsRequest = new ImportWhatsAppContactsRequest(); // ImportWhatsAppContactsRequest | 

            try
            {
                // Bulk import contacts
                ImportWhatsAppContacts200Response result = apiInstance.ImportWhatsAppContacts(importWhatsAppContactsRequest);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling WhatsAppApi.ImportWhatsAppContacts: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the ImportWhatsAppContactsWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Bulk import contacts
    ApiResponse<ImportWhatsAppContacts200Response> response = apiInstance.ImportWhatsAppContactsWithHttpInfo(importWhatsAppContactsRequest);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling WhatsAppApi.ImportWhatsAppContactsWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **importWhatsAppContactsRequest** | [**ImportWhatsAppContactsRequest**](ImportWhatsAppContactsRequest.md) |  |  |

### Return type

[**ImportWhatsAppContacts200Response**](ImportWhatsAppContacts200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Import completed |  -  |
| **400** | Validation error (missing fields |  -  |
| **401** | Unauthorized |  -  |
| **404** | WhatsApp account not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="removewhatsappbroadcastrecipients"></a>
# **RemoveWhatsAppBroadcastRecipients**
> RemoveWhatsAppBroadcastRecipients200Response RemoveWhatsAppBroadcastRecipients (string broadcastId, RemoveWhatsAppBroadcastRecipientsRequest removeWhatsAppBroadcastRecipientsRequest)

Remove recipients

Remove recipients from a draft broadcast by phone number.

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
    public class RemoveWhatsAppBroadcastRecipientsExample
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
            var apiInstance = new WhatsAppApi(httpClient, config, httpClientHandler);
            var broadcastId = "broadcastId_example";  // string | Broadcast ID
            var removeWhatsAppBroadcastRecipientsRequest = new RemoveWhatsAppBroadcastRecipientsRequest(); // RemoveWhatsAppBroadcastRecipientsRequest | 

            try
            {
                // Remove recipients
                RemoveWhatsAppBroadcastRecipients200Response result = apiInstance.RemoveWhatsAppBroadcastRecipients(broadcastId, removeWhatsAppBroadcastRecipientsRequest);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling WhatsAppApi.RemoveWhatsAppBroadcastRecipients: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the RemoveWhatsAppBroadcastRecipientsWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Remove recipients
    ApiResponse<RemoveWhatsAppBroadcastRecipients200Response> response = apiInstance.RemoveWhatsAppBroadcastRecipientsWithHttpInfo(broadcastId, removeWhatsAppBroadcastRecipientsRequest);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling WhatsAppApi.RemoveWhatsAppBroadcastRecipientsWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **broadcastId** | **string** | Broadcast ID |  |
| **removeWhatsAppBroadcastRecipientsRequest** | [**RemoveWhatsAppBroadcastRecipientsRequest**](RemoveWhatsAppBroadcastRecipientsRequest.md) |  |  |

### Return type

[**RemoveWhatsAppBroadcastRecipients200Response**](RemoveWhatsAppBroadcastRecipients200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Recipients removed successfully |  -  |
| **400** | Validation error or broadcast not in draft status |  -  |
| **401** | Unauthorized |  -  |
| **404** | Resource not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="renamewhatsappgroup"></a>
# **RenameWhatsAppGroup**
> RenameWhatsAppGroup200Response RenameWhatsAppGroup (RenameWhatsAppGroupRequest renameWhatsAppGroupRequest)

Rename group

Rename a contact group. This updates the group name on all contacts that belong to the group.

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
    public class RenameWhatsAppGroupExample
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
            var apiInstance = new WhatsAppApi(httpClient, config, httpClientHandler);
            var renameWhatsAppGroupRequest = new RenameWhatsAppGroupRequest(); // RenameWhatsAppGroupRequest | 

            try
            {
                // Rename group
                RenameWhatsAppGroup200Response result = apiInstance.RenameWhatsAppGroup(renameWhatsAppGroupRequest);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling WhatsAppApi.RenameWhatsAppGroup: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the RenameWhatsAppGroupWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Rename group
    ApiResponse<RenameWhatsAppGroup200Response> response = apiInstance.RenameWhatsAppGroupWithHttpInfo(renameWhatsAppGroupRequest);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling WhatsAppApi.RenameWhatsAppGroupWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **renameWhatsAppGroupRequest** | [**RenameWhatsAppGroupRequest**](RenameWhatsAppGroupRequest.md) |  |  |

### Return type

[**RenameWhatsAppGroup200Response**](RenameWhatsAppGroup200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Group renamed successfully |  -  |
| **400** | Validation error (missing fields |  -  |
| **401** | Unauthorized |  -  |
| **404** | WhatsApp account not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="schedulewhatsappbroadcast"></a>
# **ScheduleWhatsAppBroadcast**
> ScheduleWhatsAppBroadcast200Response ScheduleWhatsAppBroadcast (string broadcastId, ScheduleWhatsAppBroadcastRequest scheduleWhatsAppBroadcastRequest)

Schedule broadcast

Schedule a draft broadcast for future sending. The scheduled time must be in the future and no more than 30 days in advance. The broadcast must be in draft status and have recipients. 

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
    public class ScheduleWhatsAppBroadcastExample
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
            var apiInstance = new WhatsAppApi(httpClient, config, httpClientHandler);
            var broadcastId = "broadcastId_example";  // string | Broadcast ID
            var scheduleWhatsAppBroadcastRequest = new ScheduleWhatsAppBroadcastRequest(); // ScheduleWhatsAppBroadcastRequest | 

            try
            {
                // Schedule broadcast
                ScheduleWhatsAppBroadcast200Response result = apiInstance.ScheduleWhatsAppBroadcast(broadcastId, scheduleWhatsAppBroadcastRequest);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling WhatsAppApi.ScheduleWhatsAppBroadcast: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the ScheduleWhatsAppBroadcastWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Schedule broadcast
    ApiResponse<ScheduleWhatsAppBroadcast200Response> response = apiInstance.ScheduleWhatsAppBroadcastWithHttpInfo(broadcastId, scheduleWhatsAppBroadcastRequest);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling WhatsAppApi.ScheduleWhatsAppBroadcastWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **broadcastId** | **string** | Broadcast ID |  |
| **scheduleWhatsAppBroadcastRequest** | [**ScheduleWhatsAppBroadcastRequest**](ScheduleWhatsAppBroadcastRequest.md) |  |  |

### Return type

[**ScheduleWhatsAppBroadcast200Response**](ScheduleWhatsAppBroadcast200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Broadcast scheduled successfully |  -  |
| **400** | Invalid schedule time or broadcast not in draft status |  -  |
| **401** | Unauthorized |  -  |
| **404** | Resource not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="sendwhatsappbroadcast"></a>
# **SendWhatsAppBroadcast**
> SendWhatsAppBroadcast200Response SendWhatsAppBroadcast (string broadcastId)

Send broadcast

Start sending a broadcast immediately. The broadcast must be in draft or scheduled status and have at least one recipient. Messages are sent sequentially with rate limiting. 

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
    public class SendWhatsAppBroadcastExample
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
            var apiInstance = new WhatsAppApi(httpClient, config, httpClientHandler);
            var broadcastId = "broadcastId_example";  // string | Broadcast ID

            try
            {
                // Send broadcast
                SendWhatsAppBroadcast200Response result = apiInstance.SendWhatsAppBroadcast(broadcastId);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling WhatsAppApi.SendWhatsAppBroadcast: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the SendWhatsAppBroadcastWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Send broadcast
    ApiResponse<SendWhatsAppBroadcast200Response> response = apiInstance.SendWhatsAppBroadcastWithHttpInfo(broadcastId);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling WhatsAppApi.SendWhatsAppBroadcastWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **broadcastId** | **string** | Broadcast ID |  |

### Return type

[**SendWhatsAppBroadcast200Response**](SendWhatsAppBroadcast200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Broadcast send completed |  -  |
| **400** | Invalid broadcast status or no recipients |  -  |
| **401** | Unauthorized |  -  |
| **404** | Resource not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="sendwhatsappbulk"></a>
# **SendWhatsAppBulk**
> SendWhatsAppBulk200Response SendWhatsAppBulk (SendWhatsAppBulkRequest sendWhatsAppBulkRequest)

Bulk send template messages

Send a template message to multiple recipients in a single request. Maximum 100 recipients per request. Only template messages are supported for bulk sending (not free-form text).  Each recipient can have optional per-recipient template variables for personalization. Returns detailed results for each recipient. 

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
    public class SendWhatsAppBulkExample
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
            var apiInstance = new WhatsAppApi(httpClient, config, httpClientHandler);
            var sendWhatsAppBulkRequest = new SendWhatsAppBulkRequest(); // SendWhatsAppBulkRequest | 

            try
            {
                // Bulk send template messages
                SendWhatsAppBulk200Response result = apiInstance.SendWhatsAppBulk(sendWhatsAppBulkRequest);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling WhatsAppApi.SendWhatsAppBulk: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the SendWhatsAppBulkWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Bulk send template messages
    ApiResponse<SendWhatsAppBulk200Response> response = apiInstance.SendWhatsAppBulkWithHttpInfo(sendWhatsAppBulkRequest);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling WhatsAppApi.SendWhatsAppBulkWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **sendWhatsAppBulkRequest** | [**SendWhatsAppBulkRequest**](SendWhatsAppBulkRequest.md) |  |  |

### Return type

[**SendWhatsAppBulk200Response**](SendWhatsAppBulk200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Bulk send completed |  -  |
| **400** | Validation error (missing fields |  -  |
| **401** | Unauthorized |  -  |
| **404** | WhatsApp account not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="updatewhatsappbusinessprofile"></a>
# **UpdateWhatsAppBusinessProfile**
> UnpublishPost200Response UpdateWhatsAppBusinessProfile (UpdateWhatsAppBusinessProfileRequest updateWhatsAppBusinessProfileRequest)

Update business profile

Update the WhatsApp Business profile. All fields are optional; only provided fields will be updated. Constraints: about max 139 chars, description max 512 chars, max 2 websites. 

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
    public class UpdateWhatsAppBusinessProfileExample
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
            var apiInstance = new WhatsAppApi(httpClient, config, httpClientHandler);
            var updateWhatsAppBusinessProfileRequest = new UpdateWhatsAppBusinessProfileRequest(); // UpdateWhatsAppBusinessProfileRequest | 

            try
            {
                // Update business profile
                UnpublishPost200Response result = apiInstance.UpdateWhatsAppBusinessProfile(updateWhatsAppBusinessProfileRequest);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling WhatsAppApi.UpdateWhatsAppBusinessProfile: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the UpdateWhatsAppBusinessProfileWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Update business profile
    ApiResponse<UnpublishPost200Response> response = apiInstance.UpdateWhatsAppBusinessProfileWithHttpInfo(updateWhatsAppBusinessProfileRequest);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling WhatsAppApi.UpdateWhatsAppBusinessProfileWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **updateWhatsAppBusinessProfileRequest** | [**UpdateWhatsAppBusinessProfileRequest**](UpdateWhatsAppBusinessProfileRequest.md) |  |  |

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
| **200** | Business profile updated successfully |  -  |
| **400** | Validation error (field too long |  -  |
| **401** | Unauthorized |  -  |
| **404** | WhatsApp account not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="updatewhatsappcontact"></a>
# **UpdateWhatsAppContact**
> UpdateWhatsAppContact200Response UpdateWhatsAppContact (string contactId, UpdateWhatsAppContactRequest updateWhatsAppContactRequest)

Update contact

Update an existing WhatsApp contact. All fields are optional; only provided fields will be updated. Custom fields are merged with existing values. Set a custom field to null to remove it. 

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
    public class UpdateWhatsAppContactExample
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
            var apiInstance = new WhatsAppApi(httpClient, config, httpClientHandler);
            var contactId = "contactId_example";  // string | Contact ID
            var updateWhatsAppContactRequest = new UpdateWhatsAppContactRequest(); // UpdateWhatsAppContactRequest | 

            try
            {
                // Update contact
                UpdateWhatsAppContact200Response result = apiInstance.UpdateWhatsAppContact(contactId, updateWhatsAppContactRequest);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling WhatsAppApi.UpdateWhatsAppContact: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the UpdateWhatsAppContactWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Update contact
    ApiResponse<UpdateWhatsAppContact200Response> response = apiInstance.UpdateWhatsAppContactWithHttpInfo(contactId, updateWhatsAppContactRequest);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling WhatsAppApi.UpdateWhatsAppContactWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **contactId** | **string** | Contact ID |  |
| **updateWhatsAppContactRequest** | [**UpdateWhatsAppContactRequest**](UpdateWhatsAppContactRequest.md) |  |  |

### Return type

[**UpdateWhatsAppContact200Response**](UpdateWhatsAppContact200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Contact updated successfully |  -  |
| **401** | Unauthorized |  -  |
| **404** | Resource not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="updatewhatsapptemplate"></a>
# **UpdateWhatsAppTemplate**
> UpdateWhatsAppTemplate200Response UpdateWhatsAppTemplate (string templateName, UpdateWhatsAppTemplateRequest updateWhatsAppTemplateRequest)

Update template

Update a message template's components. Only certain fields can be updated depending on the template's current approval state. Approved templates can only have components updated. 

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
    public class UpdateWhatsAppTemplateExample
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
            var apiInstance = new WhatsAppApi(httpClient, config, httpClientHandler);
            var templateName = "templateName_example";  // string | Template name
            var updateWhatsAppTemplateRequest = new UpdateWhatsAppTemplateRequest(); // UpdateWhatsAppTemplateRequest | 

            try
            {
                // Update template
                UpdateWhatsAppTemplate200Response result = apiInstance.UpdateWhatsAppTemplate(templateName, updateWhatsAppTemplateRequest);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling WhatsAppApi.UpdateWhatsAppTemplate: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the UpdateWhatsAppTemplateWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Update template
    ApiResponse<UpdateWhatsAppTemplate200Response> response = apiInstance.UpdateWhatsAppTemplateWithHttpInfo(templateName, updateWhatsAppTemplateRequest);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling WhatsAppApi.UpdateWhatsAppTemplateWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **templateName** | **string** | Template name |  |
| **updateWhatsAppTemplateRequest** | [**UpdateWhatsAppTemplateRequest**](UpdateWhatsAppTemplateRequest.md) |  |  |

### Return type

[**UpdateWhatsAppTemplate200Response**](UpdateWhatsAppTemplate200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Template updated successfully |  -  |
| **400** | Validation error (missing fields) |  -  |
| **401** | Unauthorized |  -  |
| **404** | Resource not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

