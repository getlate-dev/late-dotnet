# Late.Api.WhatsAppApi

All URIs are relative to *https://zernio.com/api*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**AddWhatsAppGroupParticipants**](WhatsAppApi.md#addwhatsappgroupparticipants) | **POST** /v1/whatsapp/wa-groups/{groupId}/participants | Add participants |
| [**ApproveWhatsAppGroupJoinRequests**](WhatsAppApi.md#approvewhatsappgroupjoinrequests) | **POST** /v1/whatsapp/wa-groups/{groupId}/join-requests | Approve join requests |
| [**CreateWhatsAppGroupChat**](WhatsAppApi.md#createwhatsappgroupchat) | **POST** /v1/whatsapp/wa-groups | Create group |
| [**CreateWhatsAppGroupInviteLink**](WhatsAppApi.md#createwhatsappgroupinvitelink) | **POST** /v1/whatsapp/wa-groups/{groupId}/invite-link | Create invite link |
| [**CreateWhatsAppTemplate**](WhatsAppApi.md#createwhatsapptemplate) | **POST** /v1/whatsapp/templates | Create template |
| [**DeleteWhatsAppGroupChat**](WhatsAppApi.md#deletewhatsappgroupchat) | **DELETE** /v1/whatsapp/wa-groups/{groupId} | Delete group |
| [**DeleteWhatsAppTemplate**](WhatsAppApi.md#deletewhatsapptemplate) | **DELETE** /v1/whatsapp/templates/{templateName} | Delete template |
| [**GetWhatsAppBusinessProfile**](WhatsAppApi.md#getwhatsappbusinessprofile) | **GET** /v1/whatsapp/business-profile | Get business profile |
| [**GetWhatsAppDisplayName**](WhatsAppApi.md#getwhatsappdisplayname) | **GET** /v1/whatsapp/business-profile/display-name | Get display name status |
| [**GetWhatsAppGroupChat**](WhatsAppApi.md#getwhatsappgroupchat) | **GET** /v1/whatsapp/wa-groups/{groupId} | Get group info |
| [**GetWhatsAppTemplate**](WhatsAppApi.md#getwhatsapptemplate) | **GET** /v1/whatsapp/templates/{templateName} | Get template |
| [**GetWhatsAppTemplates**](WhatsAppApi.md#getwhatsapptemplates) | **GET** /v1/whatsapp/templates | List templates |
| [**ListWhatsAppGroupChats**](WhatsAppApi.md#listwhatsappgroupchats) | **GET** /v1/whatsapp/wa-groups | List active groups |
| [**ListWhatsAppGroupJoinRequests**](WhatsAppApi.md#listwhatsappgroupjoinrequests) | **GET** /v1/whatsapp/wa-groups/{groupId}/join-requests | List join requests |
| [**RejectWhatsAppGroupJoinRequests**](WhatsAppApi.md#rejectwhatsappgroupjoinrequests) | **DELETE** /v1/whatsapp/wa-groups/{groupId}/join-requests | Reject join requests |
| [**RemoveWhatsAppGroupParticipants**](WhatsAppApi.md#removewhatsappgroupparticipants) | **DELETE** /v1/whatsapp/wa-groups/{groupId}/participants | Remove participants |
| [**UpdateWhatsAppBusinessProfile**](WhatsAppApi.md#updatewhatsappbusinessprofile) | **POST** /v1/whatsapp/business-profile | Update business profile |
| [**UpdateWhatsAppDisplayName**](WhatsAppApi.md#updatewhatsappdisplayname) | **POST** /v1/whatsapp/business-profile/display-name | Request display name change |
| [**UpdateWhatsAppGroupChat**](WhatsAppApi.md#updatewhatsappgroupchat) | **POST** /v1/whatsapp/wa-groups/{groupId} | Update group settings |
| [**UpdateWhatsAppTemplate**](WhatsAppApi.md#updatewhatsapptemplate) | **PATCH** /v1/whatsapp/templates/{templateName} | Update template |
| [**UploadWhatsAppProfilePhoto**](WhatsAppApi.md#uploadwhatsappprofilephoto) | **POST** /v1/whatsapp/business-profile/photo | Upload profile picture |

<a id="addwhatsappgroupparticipants"></a>
# **AddWhatsAppGroupParticipants**
> UnpublishPost200Response AddWhatsAppGroupParticipants (string groupId, string accountId, AddWhatsAppGroupParticipantsRequest addWhatsAppGroupParticipantsRequest)

Add participants

Add participants to a WhatsApp group. Maximum 8 participants per request. 

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
    public class AddWhatsAppGroupParticipantsExample
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
            var apiInstance = new WhatsAppApi(httpClient, config, httpClientHandler);
            var groupId = "groupId_example";  // string | Group ID
            var accountId = "accountId_example";  // string | WhatsApp social account ID
            var addWhatsAppGroupParticipantsRequest = new AddWhatsAppGroupParticipantsRequest(); // AddWhatsAppGroupParticipantsRequest | 

            try
            {
                // Add participants
                UnpublishPost200Response result = apiInstance.AddWhatsAppGroupParticipants(groupId, accountId, addWhatsAppGroupParticipantsRequest);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling WhatsAppApi.AddWhatsAppGroupParticipants: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the AddWhatsAppGroupParticipantsWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Add participants
    ApiResponse<UnpublishPost200Response> response = apiInstance.AddWhatsAppGroupParticipantsWithHttpInfo(groupId, accountId, addWhatsAppGroupParticipantsRequest);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling WhatsAppApi.AddWhatsAppGroupParticipantsWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **groupId** | **string** | Group ID |  |
| **accountId** | **string** | WhatsApp social account ID |  |
| **addWhatsAppGroupParticipantsRequest** | [**AddWhatsAppGroupParticipantsRequest**](AddWhatsAppGroupParticipantsRequest.md) |  |  |

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
| **200** | Participants added |  -  |
| **401** | Unauthorized |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="approvewhatsappgroupjoinrequests"></a>
# **ApproveWhatsAppGroupJoinRequests**
> UnpublishPost200Response ApproveWhatsAppGroupJoinRequests (string groupId, string accountId, ApproveWhatsAppGroupJoinRequestsRequest approveWhatsAppGroupJoinRequestsRequest)

Approve join requests

Approve pending join requests for a WhatsApp group. 

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
    public class ApproveWhatsAppGroupJoinRequestsExample
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
            var apiInstance = new WhatsAppApi(httpClient, config, httpClientHandler);
            var groupId = "groupId_example";  // string | Group ID
            var accountId = "accountId_example";  // string | WhatsApp social account ID
            var approveWhatsAppGroupJoinRequestsRequest = new ApproveWhatsAppGroupJoinRequestsRequest(); // ApproveWhatsAppGroupJoinRequestsRequest | 

            try
            {
                // Approve join requests
                UnpublishPost200Response result = apiInstance.ApproveWhatsAppGroupJoinRequests(groupId, accountId, approveWhatsAppGroupJoinRequestsRequest);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling WhatsAppApi.ApproveWhatsAppGroupJoinRequests: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the ApproveWhatsAppGroupJoinRequestsWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Approve join requests
    ApiResponse<UnpublishPost200Response> response = apiInstance.ApproveWhatsAppGroupJoinRequestsWithHttpInfo(groupId, accountId, approveWhatsAppGroupJoinRequestsRequest);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling WhatsAppApi.ApproveWhatsAppGroupJoinRequestsWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **groupId** | **string** | Group ID |  |
| **accountId** | **string** | WhatsApp social account ID |  |
| **approveWhatsAppGroupJoinRequestsRequest** | [**ApproveWhatsAppGroupJoinRequestsRequest**](ApproveWhatsAppGroupJoinRequestsRequest.md) |  |  |

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
| **200** | Requests approved |  -  |
| **401** | Unauthorized |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="createwhatsappgroupchat"></a>
# **CreateWhatsAppGroupChat**
> CreateWhatsAppGroupChat201Response CreateWhatsAppGroupChat (CreateWhatsAppGroupChatRequest createWhatsAppGroupChatRequest)

Create group

Create a new WhatsApp group chat. Returns the group ID and optionally an invite link. 

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
    public class CreateWhatsAppGroupChatExample
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
            var apiInstance = new WhatsAppApi(httpClient, config, httpClientHandler);
            var createWhatsAppGroupChatRequest = new CreateWhatsAppGroupChatRequest(); // CreateWhatsAppGroupChatRequest | 

            try
            {
                // Create group
                CreateWhatsAppGroupChat201Response result = apiInstance.CreateWhatsAppGroupChat(createWhatsAppGroupChatRequest);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling WhatsAppApi.CreateWhatsAppGroupChat: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the CreateWhatsAppGroupChatWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Create group
    ApiResponse<CreateWhatsAppGroupChat201Response> response = apiInstance.CreateWhatsAppGroupChatWithHttpInfo(createWhatsAppGroupChatRequest);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling WhatsAppApi.CreateWhatsAppGroupChatWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **createWhatsAppGroupChatRequest** | [**CreateWhatsAppGroupChatRequest**](CreateWhatsAppGroupChatRequest.md) |  |  |

### Return type

[**CreateWhatsAppGroupChat201Response**](CreateWhatsAppGroupChat201Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Group created |  -  |
| **401** | Unauthorized |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="createwhatsappgroupinvitelink"></a>
# **CreateWhatsAppGroupInviteLink**
> CreateWhatsAppGroupInviteLink200Response CreateWhatsAppGroupInviteLink (string groupId, string accountId)

Create invite link

Create a new invite link for a WhatsApp group. The previous link is revoked. 

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
    public class CreateWhatsAppGroupInviteLinkExample
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
            var apiInstance = new WhatsAppApi(httpClient, config, httpClientHandler);
            var groupId = "groupId_example";  // string | Group ID
            var accountId = "accountId_example";  // string | WhatsApp social account ID

            try
            {
                // Create invite link
                CreateWhatsAppGroupInviteLink200Response result = apiInstance.CreateWhatsAppGroupInviteLink(groupId, accountId);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling WhatsAppApi.CreateWhatsAppGroupInviteLink: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the CreateWhatsAppGroupInviteLinkWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Create invite link
    ApiResponse<CreateWhatsAppGroupInviteLink200Response> response = apiInstance.CreateWhatsAppGroupInviteLinkWithHttpInfo(groupId, accountId);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling WhatsAppApi.CreateWhatsAppGroupInviteLinkWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **groupId** | **string** | Group ID |  |
| **accountId** | **string** | WhatsApp social account ID |  |

### Return type

[**CreateWhatsAppGroupInviteLink200Response**](CreateWhatsAppGroupInviteLink200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Invite link created |  -  |
| **401** | Unauthorized |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="createwhatsapptemplate"></a>
# **CreateWhatsAppTemplate**
> CreateWhatsAppTemplate200Response CreateWhatsAppTemplate (CreateWhatsAppTemplateRequest createWhatsAppTemplateRequest)

Create template

Create a new message template. Supports two modes:  **Custom template:** Provide `components` with your own content. Submitted to Meta for review (can take up to 24h).  **Library template:** Provide `library_template_name` instead of `components` to use a pre-built template from Meta's template library. Library templates are **pre-approved** (no review wait). You can optionally customize parameters and buttons via `library_template_body_inputs` and `library_template_button_inputs`.  Browse available library templates at: https://business.facebook.com/wa/manage/message-templates/ 

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
            config.BasePath = "https://zernio.com/api";
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
| **200** | Template created (pre-approved for library templates, pending review for custom) |  -  |
| **400** | Validation error (invalid name format |  -  |
| **401** | Unauthorized |  -  |
| **404** | WhatsApp account not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="deletewhatsappgroupchat"></a>
# **DeleteWhatsAppGroupChat**
> UnpublishPost200Response DeleteWhatsAppGroupChat (string groupId, string accountId)

Delete group

Delete a WhatsApp group and remove all participants. 

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
    public class DeleteWhatsAppGroupChatExample
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
            var apiInstance = new WhatsAppApi(httpClient, config, httpClientHandler);
            var groupId = "groupId_example";  // string | Group ID
            var accountId = "accountId_example";  // string | WhatsApp social account ID

            try
            {
                // Delete group
                UnpublishPost200Response result = apiInstance.DeleteWhatsAppGroupChat(groupId, accountId);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling WhatsAppApi.DeleteWhatsAppGroupChat: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the DeleteWhatsAppGroupChatWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Delete group
    ApiResponse<UnpublishPost200Response> response = apiInstance.DeleteWhatsAppGroupChatWithHttpInfo(groupId, accountId);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling WhatsAppApi.DeleteWhatsAppGroupChatWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **groupId** | **string** | Group ID |  |
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
| **200** | Group deleted |  -  |
| **401** | Unauthorized |  -  |
| **404** | Resource not found |  -  |

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
            config.BasePath = "https://zernio.com/api";
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
            config.BasePath = "https://zernio.com/api";
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

<a id="getwhatsappdisplayname"></a>
# **GetWhatsAppDisplayName**
> GetWhatsAppDisplayName200Response GetWhatsAppDisplayName (string accountId)

Get display name status

Fetch the current display name and its Meta review status for a WhatsApp Business account. Display name changes require Meta approval and can take 1-3 business days. 

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
    public class GetWhatsAppDisplayNameExample
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
            var apiInstance = new WhatsAppApi(httpClient, config, httpClientHandler);
            var accountId = "accountId_example";  // string | WhatsApp social account ID

            try
            {
                // Get display name status
                GetWhatsAppDisplayName200Response result = apiInstance.GetWhatsAppDisplayName(accountId);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling WhatsAppApi.GetWhatsAppDisplayName: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the GetWhatsAppDisplayNameWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Get display name status
    ApiResponse<GetWhatsAppDisplayName200Response> response = apiInstance.GetWhatsAppDisplayNameWithHttpInfo(accountId);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling WhatsAppApi.GetWhatsAppDisplayNameWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **accountId** | **string** | WhatsApp social account ID |  |

### Return type

[**GetWhatsAppDisplayName200Response**](GetWhatsAppDisplayName200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Display name info retrieved |  -  |
| **401** | Unauthorized |  -  |
| **404** | WhatsApp account not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="getwhatsappgroupchat"></a>
# **GetWhatsAppGroupChat**
> GetWhatsAppGroupChat200Response GetWhatsAppGroupChat (string groupId, string accountId)

Get group info

Retrieve metadata about a WhatsApp group including subject, description, participants, and settings. 

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
    public class GetWhatsAppGroupChatExample
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
            var apiInstance = new WhatsAppApi(httpClient, config, httpClientHandler);
            var groupId = "groupId_example";  // string | Group ID
            var accountId = "accountId_example";  // string | WhatsApp social account ID

            try
            {
                // Get group info
                GetWhatsAppGroupChat200Response result = apiInstance.GetWhatsAppGroupChat(groupId, accountId);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling WhatsAppApi.GetWhatsAppGroupChat: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the GetWhatsAppGroupChatWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Get group info
    ApiResponse<GetWhatsAppGroupChat200Response> response = apiInstance.GetWhatsAppGroupChatWithHttpInfo(groupId, accountId);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling WhatsAppApi.GetWhatsAppGroupChatWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **groupId** | **string** | Group ID |  |
| **accountId** | **string** | WhatsApp social account ID |  |

### Return type

[**GetWhatsAppGroupChat200Response**](GetWhatsAppGroupChat200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Group info |  -  |
| **401** | Unauthorized |  -  |
| **404** | Resource not found |  -  |

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
            config.BasePath = "https://zernio.com/api";
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
            config.BasePath = "https://zernio.com/api";
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

<a id="listwhatsappgroupchats"></a>
# **ListWhatsAppGroupChats**
> ListWhatsAppGroupChats200Response ListWhatsAppGroupChats (string accountId, int? limit = null, string? after = null)

List active groups

List active WhatsApp group chats for a business phone number. These are actual WhatsApp group conversations on the platform. 

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
    public class ListWhatsAppGroupChatsExample
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
            var apiInstance = new WhatsAppApi(httpClient, config, httpClientHandler);
            var accountId = "accountId_example";  // string | WhatsApp social account ID
            var limit = 25;  // int? | Max groups to return (optional)  (default to 25)
            var after = "after_example";  // string? | Pagination cursor (optional) 

            try
            {
                // List active groups
                ListWhatsAppGroupChats200Response result = apiInstance.ListWhatsAppGroupChats(accountId, limit, after);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling WhatsAppApi.ListWhatsAppGroupChats: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the ListWhatsAppGroupChatsWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // List active groups
    ApiResponse<ListWhatsAppGroupChats200Response> response = apiInstance.ListWhatsAppGroupChatsWithHttpInfo(accountId, limit, after);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling WhatsAppApi.ListWhatsAppGroupChatsWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **accountId** | **string** | WhatsApp social account ID |  |
| **limit** | **int?** | Max groups to return | [optional] [default to 25] |
| **after** | **string?** | Pagination cursor | [optional]  |

### Return type

[**ListWhatsAppGroupChats200Response**](ListWhatsAppGroupChats200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | List of active groups |  -  |
| **401** | Unauthorized |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="listwhatsappgroupjoinrequests"></a>
# **ListWhatsAppGroupJoinRequests**
> ListWhatsAppGroupJoinRequests200Response ListWhatsAppGroupJoinRequests (string groupId, string accountId)

List join requests

List pending join requests for a WhatsApp group (only for groups with approval_required mode). 

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
    public class ListWhatsAppGroupJoinRequestsExample
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
            var apiInstance = new WhatsAppApi(httpClient, config, httpClientHandler);
            var groupId = "groupId_example";  // string | Group ID
            var accountId = "accountId_example";  // string | WhatsApp social account ID

            try
            {
                // List join requests
                ListWhatsAppGroupJoinRequests200Response result = apiInstance.ListWhatsAppGroupJoinRequests(groupId, accountId);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling WhatsAppApi.ListWhatsAppGroupJoinRequests: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the ListWhatsAppGroupJoinRequestsWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // List join requests
    ApiResponse<ListWhatsAppGroupJoinRequests200Response> response = apiInstance.ListWhatsAppGroupJoinRequestsWithHttpInfo(groupId, accountId);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling WhatsAppApi.ListWhatsAppGroupJoinRequestsWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **groupId** | **string** | Group ID |  |
| **accountId** | **string** | WhatsApp social account ID |  |

### Return type

[**ListWhatsAppGroupJoinRequests200Response**](ListWhatsAppGroupJoinRequests200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Join requests |  -  |
| **401** | Unauthorized |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="rejectwhatsappgroupjoinrequests"></a>
# **RejectWhatsAppGroupJoinRequests**
> UnpublishPost200Response RejectWhatsAppGroupJoinRequests (string groupId, string accountId, RejectWhatsAppGroupJoinRequestsRequest rejectWhatsAppGroupJoinRequestsRequest)

Reject join requests

Reject pending join requests for a WhatsApp group. 

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
    public class RejectWhatsAppGroupJoinRequestsExample
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
            var apiInstance = new WhatsAppApi(httpClient, config, httpClientHandler);
            var groupId = "groupId_example";  // string | Group ID
            var accountId = "accountId_example";  // string | WhatsApp social account ID
            var rejectWhatsAppGroupJoinRequestsRequest = new RejectWhatsAppGroupJoinRequestsRequest(); // RejectWhatsAppGroupJoinRequestsRequest | 

            try
            {
                // Reject join requests
                UnpublishPost200Response result = apiInstance.RejectWhatsAppGroupJoinRequests(groupId, accountId, rejectWhatsAppGroupJoinRequestsRequest);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling WhatsAppApi.RejectWhatsAppGroupJoinRequests: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the RejectWhatsAppGroupJoinRequestsWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Reject join requests
    ApiResponse<UnpublishPost200Response> response = apiInstance.RejectWhatsAppGroupJoinRequestsWithHttpInfo(groupId, accountId, rejectWhatsAppGroupJoinRequestsRequest);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling WhatsAppApi.RejectWhatsAppGroupJoinRequestsWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **groupId** | **string** | Group ID |  |
| **accountId** | **string** | WhatsApp social account ID |  |
| **rejectWhatsAppGroupJoinRequestsRequest** | [**RejectWhatsAppGroupJoinRequestsRequest**](RejectWhatsAppGroupJoinRequestsRequest.md) |  |  |

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
| **200** | Requests rejected |  -  |
| **401** | Unauthorized |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="removewhatsappgroupparticipants"></a>
# **RemoveWhatsAppGroupParticipants**
> UnpublishPost200Response RemoveWhatsAppGroupParticipants (string groupId, string accountId, RemoveWhatsAppGroupParticipantsRequest removeWhatsAppGroupParticipantsRequest)

Remove participants

Remove participants from a WhatsApp group. 

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
    public class RemoveWhatsAppGroupParticipantsExample
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
            var apiInstance = new WhatsAppApi(httpClient, config, httpClientHandler);
            var groupId = "groupId_example";  // string | Group ID
            var accountId = "accountId_example";  // string | WhatsApp social account ID
            var removeWhatsAppGroupParticipantsRequest = new RemoveWhatsAppGroupParticipantsRequest(); // RemoveWhatsAppGroupParticipantsRequest | 

            try
            {
                // Remove participants
                UnpublishPost200Response result = apiInstance.RemoveWhatsAppGroupParticipants(groupId, accountId, removeWhatsAppGroupParticipantsRequest);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling WhatsAppApi.RemoveWhatsAppGroupParticipants: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the RemoveWhatsAppGroupParticipantsWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Remove participants
    ApiResponse<UnpublishPost200Response> response = apiInstance.RemoveWhatsAppGroupParticipantsWithHttpInfo(groupId, accountId, removeWhatsAppGroupParticipantsRequest);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling WhatsAppApi.RemoveWhatsAppGroupParticipantsWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **groupId** | **string** | Group ID |  |
| **accountId** | **string** | WhatsApp social account ID |  |
| **removeWhatsAppGroupParticipantsRequest** | [**RemoveWhatsAppGroupParticipantsRequest**](RemoveWhatsAppGroupParticipantsRequest.md) |  |  |

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
| **200** | Participants removed |  -  |
| **401** | Unauthorized |  -  |

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
            config.BasePath = "https://zernio.com/api";
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

<a id="updatewhatsappdisplayname"></a>
# **UpdateWhatsAppDisplayName**
> UpdateWhatsAppDisplayName200Response UpdateWhatsAppDisplayName (UpdateWhatsAppDisplayNameRequest updateWhatsAppDisplayNameRequest)

Request display name change

Submit a display name change request for the WhatsApp Business account. The new name must follow WhatsApp naming guidelines (3-512 characters, must represent your business). Changes require Meta review and approval, which typically takes 1-3 business days. 

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
    public class UpdateWhatsAppDisplayNameExample
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
            var apiInstance = new WhatsAppApi(httpClient, config, httpClientHandler);
            var updateWhatsAppDisplayNameRequest = new UpdateWhatsAppDisplayNameRequest(); // UpdateWhatsAppDisplayNameRequest | 

            try
            {
                // Request display name change
                UpdateWhatsAppDisplayName200Response result = apiInstance.UpdateWhatsAppDisplayName(updateWhatsAppDisplayNameRequest);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling WhatsAppApi.UpdateWhatsAppDisplayName: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the UpdateWhatsAppDisplayNameWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Request display name change
    ApiResponse<UpdateWhatsAppDisplayName200Response> response = apiInstance.UpdateWhatsAppDisplayNameWithHttpInfo(updateWhatsAppDisplayNameRequest);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling WhatsAppApi.UpdateWhatsAppDisplayNameWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **updateWhatsAppDisplayNameRequest** | [**UpdateWhatsAppDisplayNameRequest**](UpdateWhatsAppDisplayNameRequest.md) |  |  |

### Return type

[**UpdateWhatsAppDisplayName200Response**](UpdateWhatsAppDisplayName200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Display name change submitted for review |  -  |
| **400** | Invalid display name (too short |  -  |
| **401** | Unauthorized |  -  |
| **404** | WhatsApp account not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="updatewhatsappgroupchat"></a>
# **UpdateWhatsAppGroupChat**
> UnpublishPost200Response UpdateWhatsAppGroupChat (string groupId, string accountId, UpdateWhatsAppGroupChatRequest updateWhatsAppGroupChatRequest)

Update group settings

Update the subject, description, or join approval mode of a WhatsApp group. 

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
    public class UpdateWhatsAppGroupChatExample
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
            var apiInstance = new WhatsAppApi(httpClient, config, httpClientHandler);
            var groupId = "groupId_example";  // string | Group ID
            var accountId = "accountId_example";  // string | WhatsApp social account ID
            var updateWhatsAppGroupChatRequest = new UpdateWhatsAppGroupChatRequest(); // UpdateWhatsAppGroupChatRequest | 

            try
            {
                // Update group settings
                UnpublishPost200Response result = apiInstance.UpdateWhatsAppGroupChat(groupId, accountId, updateWhatsAppGroupChatRequest);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling WhatsAppApi.UpdateWhatsAppGroupChat: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the UpdateWhatsAppGroupChatWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Update group settings
    ApiResponse<UnpublishPost200Response> response = apiInstance.UpdateWhatsAppGroupChatWithHttpInfo(groupId, accountId, updateWhatsAppGroupChatRequest);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling WhatsAppApi.UpdateWhatsAppGroupChatWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **groupId** | **string** | Group ID |  |
| **accountId** | **string** | WhatsApp social account ID |  |
| **updateWhatsAppGroupChatRequest** | [**UpdateWhatsAppGroupChatRequest**](UpdateWhatsAppGroupChatRequest.md) |  |  |

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
| **200** | Group updated |  -  |
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
            config.BasePath = "https://zernio.com/api";
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

<a id="uploadwhatsappprofilephoto"></a>
# **UploadWhatsAppProfilePhoto**
> UnpublishPost200Response UploadWhatsAppProfilePhoto (string accountId, FileParameter file)

Upload profile picture

Upload a new profile picture for the WhatsApp Business Profile. Uses Meta's resumable upload API under the hood: creates an upload session, uploads the image bytes, then updates the business profile with the resulting handle. 

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
    public class UploadWhatsAppProfilePhotoExample
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
            var apiInstance = new WhatsAppApi(httpClient, config, httpClientHandler);
            var accountId = "accountId_example";  // string | WhatsApp social account ID
            var file = new System.IO.MemoryStream(System.IO.File.ReadAllBytes("/path/to/file.txt"));  // FileParameter | Image file (JPEG or PNG, max 5MB, recommended 640x640)

            try
            {
                // Upload profile picture
                UnpublishPost200Response result = apiInstance.UploadWhatsAppProfilePhoto(accountId, file);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling WhatsAppApi.UploadWhatsAppProfilePhoto: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the UploadWhatsAppProfilePhotoWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Upload profile picture
    ApiResponse<UnpublishPost200Response> response = apiInstance.UploadWhatsAppProfilePhotoWithHttpInfo(accountId, file);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling WhatsAppApi.UploadWhatsAppProfilePhotoWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **accountId** | **string** | WhatsApp social account ID |  |
| **file** | **FileParameter****FileParameter** | Image file (JPEG or PNG, max 5MB, recommended 640x640) |  |

### Return type

[**UnpublishPost200Response**](UnpublishPost200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: multipart/form-data
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Profile picture updated successfully |  -  |
| **400** | Invalid file type |  -  |
| **401** | Unauthorized |  -  |
| **404** | WhatsApp account not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

