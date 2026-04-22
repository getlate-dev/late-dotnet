# Zernio.Api.MessagesApi

All URIs are relative to *https://zernio.com/api*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**AddMessageReaction**](MessagesApi.md#addmessagereaction) | **POST** /v1/inbox/conversations/{conversationId}/messages/{messageId}/reactions | Add reaction |
| [**CreateInboxConversation**](MessagesApi.md#createinboxconversation) | **POST** /v1/inbox/conversations | Create conversation |
| [**DeleteInboxMessage**](MessagesApi.md#deleteinboxmessage) | **DELETE** /v1/inbox/conversations/{conversationId}/messages/{messageId} | Delete message |
| [**EditInboxMessage**](MessagesApi.md#editinboxmessage) | **PATCH** /v1/inbox/conversations/{conversationId}/messages/{messageId} | Edit message |
| [**GetInboxConversation**](MessagesApi.md#getinboxconversation) | **GET** /v1/inbox/conversations/{conversationId} | Get conversation |
| [**GetInboxConversationMessages**](MessagesApi.md#getinboxconversationmessages) | **GET** /v1/inbox/conversations/{conversationId}/messages | List messages |
| [**ListInboxConversations**](MessagesApi.md#listinboxconversations) | **GET** /v1/inbox/conversations | List conversations |
| [**RemoveMessageReaction**](MessagesApi.md#removemessagereaction) | **DELETE** /v1/inbox/conversations/{conversationId}/messages/{messageId}/reactions | Remove reaction |
| [**SendInboxMessage**](MessagesApi.md#sendinboxmessage) | **POST** /v1/inbox/conversations/{conversationId}/messages | Send message |
| [**SendTypingIndicator**](MessagesApi.md#sendtypingindicator) | **POST** /v1/inbox/conversations/{conversationId}/typing | Send typing indicator |
| [**UpdateInboxConversation**](MessagesApi.md#updateinboxconversation) | **PUT** /v1/inbox/conversations/{conversationId} | Update conversation status |
| [**UploadMediaDirect**](MessagesApi.md#uploadmediadirect) | **POST** /v1/media/upload-direct | Upload media file |

<a id="addmessagereaction"></a>
# **AddMessageReaction**
> UpdateYoutubeDefaultPlaylist200Response AddMessageReaction (string conversationId, string messageId, AddMessageReactionRequest addMessageReactionRequest)

Add reaction

Add an emoji reaction to a message. Platform support: - Telegram: Supports a subset of Unicode emoji reactions - WhatsApp: Supports any standard emoji (one reaction per message per sender) - All others: Returns 400 (not supported) 

### Example
```csharp
using System.Collections.Generic;
using System.Diagnostics;
using System.Net.Http;
using Zernio.Api;
using Zernio.Client;
using Zernio.Model;

namespace Example
{
    public class AddMessageReactionExample
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
            var apiInstance = new MessagesApi(httpClient, config, httpClientHandler);
            var conversationId = "conversationId_example";  // string | The conversation ID
            var messageId = "messageId_example";  // string | The platform message ID to react to
            var addMessageReactionRequest = new AddMessageReactionRequest(); // AddMessageReactionRequest | 

            try
            {
                // Add reaction
                UpdateYoutubeDefaultPlaylist200Response result = apiInstance.AddMessageReaction(conversationId, messageId, addMessageReactionRequest);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling MessagesApi.AddMessageReaction: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the AddMessageReactionWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Add reaction
    ApiResponse<UpdateYoutubeDefaultPlaylist200Response> response = apiInstance.AddMessageReactionWithHttpInfo(conversationId, messageId, addMessageReactionRequest);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling MessagesApi.AddMessageReactionWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **conversationId** | **string** | The conversation ID |  |
| **messageId** | **string** | The platform message ID to react to |  |
| **addMessageReactionRequest** | [**AddMessageReactionRequest**](AddMessageReactionRequest.md) |  |  |

### Return type

[**UpdateYoutubeDefaultPlaylist200Response**](UpdateYoutubeDefaultPlaylist200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Reaction added |  -  |
| **400** | Platform does not support reactions or invalid request |  -  |
| **401** | Unauthorized |  -  |
| **403** | Inbox addon required |  -  |
| **404** | Account or conversation not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="createinboxconversation"></a>
# **CreateInboxConversation**
> CreateInboxConversation201Response CreateInboxConversation (CreateInboxConversationRequest createInboxConversationRequest)

Create conversation

Initiate a new direct message conversation with a specified user. If a conversation already exists with the recipient, the message is added to the existing thread.  Currently supported platforms: Twitter/X only. Other platforms will return PLATFORM_NOT_SUPPORTED.  DM eligibility: Before sending, the endpoint checks if the recipient accepts DMs from your account (via the receives_your_dm field). If not, a 422 error with code DM_NOT_ALLOWED is returned. You can skip this check with skipDmCheck: true if you have already verified eligibility.  X API tier requirement: DM write endpoints require X API Pro tier ($5,000/month) or Enterprise access. This applies to BYOK (Bring Your Own Key) users who provide their own X API credentials.  Rate limits: 200 requests per 15 minutes, 1,000 per 24 hours per user, 15,000 per 24 hours per app (shared across all DM endpoints). 

### Example
```csharp
using System.Collections.Generic;
using System.Diagnostics;
using System.Net.Http;
using Zernio.Api;
using Zernio.Client;
using Zernio.Model;

namespace Example
{
    public class CreateInboxConversationExample
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
            var apiInstance = new MessagesApi(httpClient, config, httpClientHandler);
            var createInboxConversationRequest = new CreateInboxConversationRequest(); // CreateInboxConversationRequest | 

            try
            {
                // Create conversation
                CreateInboxConversation201Response result = apiInstance.CreateInboxConversation(createInboxConversationRequest);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling MessagesApi.CreateInboxConversation: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the CreateInboxConversationWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Create conversation
    ApiResponse<CreateInboxConversation201Response> response = apiInstance.CreateInboxConversationWithHttpInfo(createInboxConversationRequest);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling MessagesApi.CreateInboxConversationWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **createInboxConversationRequest** | [**CreateInboxConversationRequest**](CreateInboxConversationRequest.md) |  |  |

### Return type

[**CreateInboxConversation201Response**](CreateInboxConversation201Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json, multipart/form-data
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Conversation created successfully |  -  |
| **400** | Validation error or platform not supported |  -  |
| **401** | Unauthorized |  -  |
| **403** | Inbox addon required or profile limit reached |  -  |
| **404** | Account or recipient user not found |  -  |
| **422** | Recipient does not accept DMs from this account |  -  |
| **429** | X API rate limit exceeded |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="deleteinboxmessage"></a>
# **DeleteInboxMessage**
> UpdateYoutubeDefaultPlaylist200Response DeleteInboxMessage (string conversationId, string messageId, string accountId)

Delete message

Delete a message from a conversation. Platform support varies: - Telegram: Full delete (bot's own messages anytime, others if admin) - X/Twitter: Full delete (own DM events only) - Bluesky: Delete for self only (recipient still sees it) - Reddit: Delete from sender's view only - Facebook, Instagram, WhatsApp: Not supported (returns 400) 

### Example
```csharp
using System.Collections.Generic;
using System.Diagnostics;
using System.Net.Http;
using Zernio.Api;
using Zernio.Client;
using Zernio.Model;

namespace Example
{
    public class DeleteInboxMessageExample
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
            var apiInstance = new MessagesApi(httpClient, config, httpClientHandler);
            var conversationId = "conversationId_example";  // string | The conversation ID
            var messageId = "messageId_example";  // string | The platform message ID to delete
            var accountId = "accountId_example";  // string | Social account ID

            try
            {
                // Delete message
                UpdateYoutubeDefaultPlaylist200Response result = apiInstance.DeleteInboxMessage(conversationId, messageId, accountId);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling MessagesApi.DeleteInboxMessage: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the DeleteInboxMessageWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Delete message
    ApiResponse<UpdateYoutubeDefaultPlaylist200Response> response = apiInstance.DeleteInboxMessageWithHttpInfo(conversationId, messageId, accountId);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling MessagesApi.DeleteInboxMessageWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **conversationId** | **string** | The conversation ID |  |
| **messageId** | **string** | The platform message ID to delete |  |
| **accountId** | **string** | Social account ID |  |

### Return type

[**UpdateYoutubeDefaultPlaylist200Response**](UpdateYoutubeDefaultPlaylist200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Message deleted |  -  |
| **400** | Platform does not support deletion or invalid request |  -  |
| **401** | Unauthorized |  -  |
| **403** | Inbox addon required |  -  |
| **404** | Account or conversation not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

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
using Zernio.Api;
using Zernio.Client;
using Zernio.Model;

namespace Example
{
    public class EditInboxMessageExample
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
using Zernio.Api;
using Zernio.Client;
using Zernio.Model;

namespace Example
{
    public class GetInboxConversationExample
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

Fetch messages for a specific conversation. Requires accountId query parameter.  Twitter/X limitation: X's encrypted \"X Chat\" messages are not accessible via the API. Conversations where the other participant uses encrypted X Chat may only show your outgoing messages. See the list conversations endpoint for more details. 

### Example
```csharp
using System.Collections.Generic;
using System.Diagnostics;
using System.Net.Http;
using Zernio.Api;
using Zernio.Client;
using Zernio.Model;

namespace Example
{
    public class GetInboxConversationMessagesExample
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

Fetch conversations (DMs) from all connected messaging accounts in a single API call. Supports filtering by profile and platform. Results are aggregated and deduplicated. Supported platforms: Facebook, Instagram, Twitter/X, Bluesky, Reddit, Telegram.  Twitter/X limitation: X has replaced traditional DMs with encrypted \"X Chat\" for many accounts. Messages sent or received through encrypted X Chat are not accessible via X's API (the /2/dm_events endpoint only returns legacy unencrypted DMs). This means some Twitter/X conversations may show only outgoing messages or appear empty. This is an X platform limitation that affects all third-party applications. See X's docs on encrypted messaging for more details. 

### Example
```csharp
using System.Collections.Generic;
using System.Diagnostics;
using System.Net.Http;
using Zernio.Api;
using Zernio.Client;
using Zernio.Model;

namespace Example
{
    public class ListInboxConversationsExample
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

<a id="removemessagereaction"></a>
# **RemoveMessageReaction**
> UpdateYoutubeDefaultPlaylist200Response RemoveMessageReaction (string conversationId, string messageId, string accountId)

Remove reaction

Remove a reaction from a message. Platform support: - Telegram: Send empty reaction array to clear - WhatsApp: Send empty emoji to remove - All others: Returns 400 (not supported) 

### Example
```csharp
using System.Collections.Generic;
using System.Diagnostics;
using System.Net.Http;
using Zernio.Api;
using Zernio.Client;
using Zernio.Model;

namespace Example
{
    public class RemoveMessageReactionExample
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
            var apiInstance = new MessagesApi(httpClient, config, httpClientHandler);
            var conversationId = "conversationId_example";  // string | The conversation ID
            var messageId = "messageId_example";  // string | The platform message ID
            var accountId = "accountId_example";  // string | Social account ID

            try
            {
                // Remove reaction
                UpdateYoutubeDefaultPlaylist200Response result = apiInstance.RemoveMessageReaction(conversationId, messageId, accountId);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling MessagesApi.RemoveMessageReaction: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the RemoveMessageReactionWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Remove reaction
    ApiResponse<UpdateYoutubeDefaultPlaylist200Response> response = apiInstance.RemoveMessageReactionWithHttpInfo(conversationId, messageId, accountId);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling MessagesApi.RemoveMessageReactionWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **conversationId** | **string** | The conversation ID |  |
| **messageId** | **string** | The platform message ID |  |
| **accountId** | **string** | Social account ID |  |

### Return type

[**UpdateYoutubeDefaultPlaylist200Response**](UpdateYoutubeDefaultPlaylist200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Reaction removed |  -  |
| **400** | Platform does not support reactions or invalid request |  -  |
| **401** | Unauthorized |  -  |
| **403** | Inbox addon required |  -  |
| **404** | Account or conversation not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="sendinboxmessage"></a>
# **SendInboxMessage**
> SendInboxMessage200Response SendInboxMessage (string conversationId, SendInboxMessageRequest sendInboxMessageRequest)

Send message

Send a message in a conversation. Supports text, attachments, quick replies, buttons, templates, and message tags. Attachment and interactive message support varies by platform.  WhatsApp rich interactive messages (list, CTA URL, Flow) are available via the `interactive` field. Tap events are delivered through the `message.received` webhook with WhatsApp-specific `metadata` fields (`interactiveType`, `interactiveId`, `flowResponseJson`, `flowResponseData`). 

### Example
```csharp
using System.Collections.Generic;
using System.Diagnostics;
using System.Net.Http;
using Zernio.Api;
using Zernio.Client;
using Zernio.Model;

namespace Example
{
    public class SendInboxMessageExample
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

<a id="sendtypingindicator"></a>
# **SendTypingIndicator**
> UpdateYoutubeDefaultPlaylist200Response SendTypingIndicator (string conversationId, SendTypingIndicatorRequest sendTypingIndicatorRequest)

Send typing indicator

Show a typing indicator in a conversation. Platform support: - Facebook Messenger: Shows \"Page is typing...\" for 20 seconds - Telegram: Shows \"Bot is typing...\" for 5 seconds - All others: Returns 200 but no-op (platform doesn't support it)  Typing indicators are best-effort. The endpoint always returns 200 even if the platform call fails. 

### Example
```csharp
using System.Collections.Generic;
using System.Diagnostics;
using System.Net.Http;
using Zernio.Api;
using Zernio.Client;
using Zernio.Model;

namespace Example
{
    public class SendTypingIndicatorExample
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
            var apiInstance = new MessagesApi(httpClient, config, httpClientHandler);
            var conversationId = "conversationId_example";  // string | The conversation ID
            var sendTypingIndicatorRequest = new SendTypingIndicatorRequest(); // SendTypingIndicatorRequest | 

            try
            {
                // Send typing indicator
                UpdateYoutubeDefaultPlaylist200Response result = apiInstance.SendTypingIndicator(conversationId, sendTypingIndicatorRequest);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling MessagesApi.SendTypingIndicator: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the SendTypingIndicatorWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Send typing indicator
    ApiResponse<UpdateYoutubeDefaultPlaylist200Response> response = apiInstance.SendTypingIndicatorWithHttpInfo(conversationId, sendTypingIndicatorRequest);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling MessagesApi.SendTypingIndicatorWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **conversationId** | **string** | The conversation ID |  |
| **sendTypingIndicatorRequest** | [**SendTypingIndicatorRequest**](SendTypingIndicatorRequest.md) |  |  |

### Return type

[**UpdateYoutubeDefaultPlaylist200Response**](UpdateYoutubeDefaultPlaylist200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Typing indicator sent (or no-op on unsupported platforms) |  -  |
| **401** | Unauthorized |  -  |
| **403** | Inbox addon required |  -  |
| **404** | Account or conversation not found |  -  |

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
using Zernio.Api;
using Zernio.Client;
using Zernio.Model;

namespace Example
{
    public class UpdateInboxConversationExample
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
| **404** | Conversation not found (WhatsApp only; other platforms upsert) |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="uploadmediadirect"></a>
# **UploadMediaDirect**
> UploadMediaDirect200Response UploadMediaDirect (FileParameter file, string? contentType = null)

Upload media file

Upload a media file using API key authentication and get back a publicly accessible URL. The URL can be used as attachmentUrl when sending inbox messages.  Files are stored in temporary storage and auto-delete after 7 days. Maximum file size is 25MB.  Unlike /v1/media/upload (which uses upload tokens for end-user flows), this endpoint uses standard Bearer token authentication for programmatic use. 

### Example
```csharp
using System.Collections.Generic;
using System.Diagnostics;
using System.Net.Http;
using Zernio.Api;
using Zernio.Client;
using Zernio.Model;

namespace Example
{
    public class UploadMediaDirectExample
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
            var apiInstance = new MessagesApi(httpClient, config, httpClientHandler);
            var file = new System.IO.MemoryStream(System.IO.File.ReadAllBytes("/path/to/file.txt"));  // FileParameter | The file to upload (max 25MB)
            var contentType = "contentType_example";  // string? | Override MIME type (e.g. \\\"image/jpeg\\\"). Auto-detected from file if not provided. (optional) 

            try
            {
                // Upload media file
                UploadMediaDirect200Response result = apiInstance.UploadMediaDirect(file, contentType);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling MessagesApi.UploadMediaDirect: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the UploadMediaDirectWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Upload media file
    ApiResponse<UploadMediaDirect200Response> response = apiInstance.UploadMediaDirectWithHttpInfo(file, contentType);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling MessagesApi.UploadMediaDirectWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **file** | **FileParameter****FileParameter** | The file to upload (max 25MB) |  |
| **contentType** | **string?** | Override MIME type (e.g. \\\&quot;image/jpeg\\\&quot;). Auto-detected from file if not provided. | [optional]  |

### Return type

[**UploadMediaDirect200Response**](UploadMediaDirect200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: multipart/form-data
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | File uploaded successfully |  -  |
| **400** | No file provided or file too large |  -  |
| **401** | Unauthorized |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

