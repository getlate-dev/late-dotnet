# Late.Api.MessagesApi

All URIs are relative to *https://getlate.dev/api*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**EditInboxMessage**](MessagesApi.md#editinboxmessage) | **PATCH** /v1/inbox/conversations/{conversationId}/messages/{messageId} | Edit message |
| [**GetInboxConversation**](MessagesApi.md#getinboxconversation) | **GET** /v1/inbox/conversations/{conversationId} | Get conversation |
| [**GetInboxConversationMessages**](MessagesApi.md#getinboxconversationmessages) | **GET** /v1/inbox/conversations/{conversationId}/messages | List messages |
| [**ListInboxConversations**](MessagesApi.md#listinboxconversations) | **GET** /v1/inbox/conversations | List conversations |
| [**SendInboxMessage**](MessagesApi.md#sendinboxmessage) | **POST** /v1/inbox/conversations/{conversationId}/messages | Send message |
| [**UpdateInboxConversation**](MessagesApi.md#updateinboxconversation) | **PUT** /v1/inbox/conversations/{conversationId} | Update conversation status |

<a id="editinboxmessage"></a>
# **EditInboxMessage**
> EditInboxMessage200Response EditInboxMessage (string conversationId, string messageId, EditInboxMessageRequest editInboxMessageRequest)

Edit message

Edit the text and/or reply markup of a previously sent Telegram message. Only supported for Telegram. Returns 400 for other platforms. 

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
    public class EditInboxMessageExample
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
            var apiInstance = new MessagesApi(httpClient, config, httpClientHandler);
            var conversationId = "conversationId_example";  // string | The conversation ID
            var messageId = "messageId_example";  // string | The Telegram message ID to edit
            var editInboxMessageRequest = new EditInboxMessageRequest(); // EditInboxMessageRequest | 

            try
            {
                // Edit message
                EditInboxMessage200Response result = apiInstance.EditInboxMessage(conversationId, messageId, editInboxMessageRequest);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling MessagesApi.EditInboxMessage: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the EditInboxMessageWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Edit message
    ApiResponse<EditInboxMessage200Response> response = apiInstance.EditInboxMessageWithHttpInfo(conversationId, messageId, editInboxMessageRequest);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling MessagesApi.EditInboxMessageWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **conversationId** | **string** | The conversation ID |  |
| **messageId** | **string** | The Telegram message ID to edit |  |
| **editInboxMessageRequest** | [**EditInboxMessageRequest**](EditInboxMessageRequest.md) |  |  |

### Return type

[**EditInboxMessage200Response**](EditInboxMessage200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Message edited |  -  |
| **400** | Not supported or invalid request |  -  |
| **401** | Unauthorized |  -  |
| **403** | Inbox addon required |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="getinboxconversation"></a>
# **GetInboxConversation**
> GetInboxConversation200Response GetInboxConversation (string conversationId, string accountId)

Get conversation

Retrieve details and metadata for a specific conversation. Requires accountId query parameter.

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
    public class GetInboxConversationExample
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
            var apiInstance = new MessagesApi(httpClient, config, httpClientHandler);
            var conversationId = "conversationId_example";  // string | The conversation ID (id field from list conversations endpoint). This is the platform-specific conversation identifier, not an internal database ID.
            var accountId = "accountId_example";  // string | The social account ID

            try
            {
                // Get conversation
                GetInboxConversation200Response result = apiInstance.GetInboxConversation(conversationId, accountId);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling MessagesApi.GetInboxConversation: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the GetInboxConversationWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Get conversation
    ApiResponse<GetInboxConversation200Response> response = apiInstance.GetInboxConversationWithHttpInfo(conversationId, accountId);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling MessagesApi.GetInboxConversationWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **conversationId** | **string** | The conversation ID (id field from list conversations endpoint). This is the platform-specific conversation identifier, not an internal database ID. |  |
| **accountId** | **string** | The social account ID |  |

### Return type

[**GetInboxConversation200Response**](GetInboxConversation200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Conversation details |  -  |
| **401** | Unauthorized |  -  |
| **403** | Inbox addon required |  -  |
| **404** | Conversation not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="getinboxconversationmessages"></a>
# **GetInboxConversationMessages**
> GetInboxConversationMessages200Response GetInboxConversationMessages (string conversationId, string accountId)

List messages

Fetch messages for a specific conversation. Requires accountId query parameter.

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
    public class GetInboxConversationMessagesExample
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
            var apiInstance = new MessagesApi(httpClient, config, httpClientHandler);
            var conversationId = "conversationId_example";  // string | The conversation ID (id field from list conversations endpoint). This is the platform-specific conversation identifier, not an internal database ID.
            var accountId = "accountId_example";  // string | Social account ID

            try
            {
                // List messages
                GetInboxConversationMessages200Response result = apiInstance.GetInboxConversationMessages(conversationId, accountId);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling MessagesApi.GetInboxConversationMessages: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the GetInboxConversationMessagesWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // List messages
    ApiResponse<GetInboxConversationMessages200Response> response = apiInstance.GetInboxConversationMessagesWithHttpInfo(conversationId, accountId);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling MessagesApi.GetInboxConversationMessagesWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **conversationId** | **string** | The conversation ID (id field from list conversations endpoint). This is the platform-specific conversation identifier, not an internal database ID. |  |
| **accountId** | **string** | Social account ID |  |

### Return type

[**GetInboxConversationMessages200Response**](GetInboxConversationMessages200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Messages in conversation |  -  |
| **401** | Unauthorized |  -  |
| **403** | Inbox addon required |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="listinboxconversations"></a>
# **ListInboxConversations**
> ListInboxConversations200Response ListInboxConversations (string? profileId = null, string? platform = null, string? status = null, string? sortOrder = null, int? limit = null, string? cursor = null, string? accountId = null)

List conversations

Fetch conversations (DMs) from all connected messaging accounts in a single API call. Supports filtering by profile and platform. Results are aggregated and deduplicated. Supported platforms: Facebook, Instagram, Twitter/X, Bluesky, Reddit, Telegram. 

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
    public class ListInboxConversationsExample
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
            var apiInstance = new MessagesApi(httpClient, config, httpClientHandler);
            var profileId = "profileId_example";  // string? | Filter by profile ID (optional) 
            var platform = "facebook";  // string? | Filter by platform (optional) 
            var status = "active";  // string? | Filter by conversation status (optional) 
            var sortOrder = "asc";  // string? | Sort order by updated time (optional)  (default to desc)
            var limit = 50;  // int? | Maximum number of conversations to return (optional)  (default to 50)
            var cursor = "cursor_example";  // string? | Pagination cursor for next page (optional) 
            var accountId = "accountId_example";  // string? | Filter by specific social account ID (optional) 

            try
            {
                // List conversations
                ListInboxConversations200Response result = apiInstance.ListInboxConversations(profileId, platform, status, sortOrder, limit, cursor, accountId);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling MessagesApi.ListInboxConversations: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the ListInboxConversationsWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // List conversations
    ApiResponse<ListInboxConversations200Response> response = apiInstance.ListInboxConversationsWithHttpInfo(profileId, platform, status, sortOrder, limit, cursor, accountId);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling MessagesApi.ListInboxConversationsWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **profileId** | **string?** | Filter by profile ID | [optional]  |
| **platform** | **string?** | Filter by platform | [optional]  |
| **status** | **string?** | Filter by conversation status | [optional]  |
| **sortOrder** | **string?** | Sort order by updated time | [optional] [default to desc] |
| **limit** | **int?** | Maximum number of conversations to return | [optional] [default to 50] |
| **cursor** | **string?** | Pagination cursor for next page | [optional]  |
| **accountId** | **string?** | Filter by specific social account ID | [optional]  |

### Return type

[**ListInboxConversations200Response**](ListInboxConversations200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Aggregated conversations |  -  |
| **401** | Unauthorized |  -  |
| **403** | Inbox addon required |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="sendinboxmessage"></a>
# **SendInboxMessage**
> SendInboxMessage200Response SendInboxMessage (string conversationId, SendInboxMessageRequest sendInboxMessageRequest)

Send message

Send a message in a conversation. Supports text, attachments, quick replies, buttons, carousels, and message tags. Attachments: Telegram (images, videos, docs up to 50MB), Facebook (images, videos, audio, files), Instagram (images, videos, audio via URL), Twitter/X (images, videos). Not supported on Bluesky/Reddit. Interactive messages (quick replies, buttons, templates, reply markup) vary by platform. Unsupported fields are silently ignored. 

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
    public class SendInboxMessageExample
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
            var apiInstance = new MessagesApi(httpClient, config, httpClientHandler);
            var conversationId = "conversationId_example";  // string | The conversation ID (id field from list conversations endpoint). This is the platform-specific conversation identifier, not an internal database ID.
            var sendInboxMessageRequest = new SendInboxMessageRequest(); // SendInboxMessageRequest | 

            try
            {
                // Send message
                SendInboxMessage200Response result = apiInstance.SendInboxMessage(conversationId, sendInboxMessageRequest);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling MessagesApi.SendInboxMessage: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the SendInboxMessageWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Send message
    ApiResponse<SendInboxMessage200Response> response = apiInstance.SendInboxMessageWithHttpInfo(conversationId, sendInboxMessageRequest);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling MessagesApi.SendInboxMessageWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **conversationId** | **string** | The conversation ID (id field from list conversations endpoint). This is the platform-specific conversation identifier, not an internal database ID. |  |
| **sendInboxMessageRequest** | [**SendInboxMessageRequest**](SendInboxMessageRequest.md) |  |  |

### Return type

[**SendInboxMessage200Response**](SendInboxMessage200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json, multipart/form-data
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Message sent |  -  |
| **400** | Bad request (e.g., attachment not supported for platform, validation error) |  -  |
| **401** | Unauthorized |  -  |
| **403** | Inbox addon required |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="updateinboxconversation"></a>
# **UpdateInboxConversation**
> UpdateInboxConversation200Response UpdateInboxConversation (string conversationId, UpdateInboxConversationRequest updateInboxConversationRequest)

Update conversation status

Archive or activate a conversation. Requires accountId in request body.

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
    public class UpdateInboxConversationExample
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
            var apiInstance = new MessagesApi(httpClient, config, httpClientHandler);
            var conversationId = "conversationId_example";  // string | The conversation ID (id field from list conversations endpoint). This is the platform-specific conversation identifier, not an internal database ID.
            var updateInboxConversationRequest = new UpdateInboxConversationRequest(); // UpdateInboxConversationRequest | 

            try
            {
                // Update conversation status
                UpdateInboxConversation200Response result = apiInstance.UpdateInboxConversation(conversationId, updateInboxConversationRequest);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling MessagesApi.UpdateInboxConversation: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the UpdateInboxConversationWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Update conversation status
    ApiResponse<UpdateInboxConversation200Response> response = apiInstance.UpdateInboxConversationWithHttpInfo(conversationId, updateInboxConversationRequest);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling MessagesApi.UpdateInboxConversationWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **conversationId** | **string** | The conversation ID (id field from list conversations endpoint). This is the platform-specific conversation identifier, not an internal database ID. |  |
| **updateInboxConversationRequest** | [**UpdateInboxConversationRequest**](UpdateInboxConversationRequest.md) |  |  |

### Return type

[**UpdateInboxConversation200Response**](UpdateInboxConversation200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Conversation updated |  -  |
| **401** | Unauthorized |  -  |
| **403** | Inbox addon required |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

