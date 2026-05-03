# Zernio.Api.WebhookEventsApi

All URIs are relative to *https://zernio.com/api*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**OnAccountAdsInitialSyncCompleted**](WebhookEventsApi.md#onaccountadsinitialsynccompleted) | **POST** /account.ads.initial_sync_completed | Ads initial sync completed event |
| [**OnAccountConnected**](WebhookEventsApi.md#onaccountconnected) | **POST** /account.connected | Account connected event |
| [**OnAccountDisconnected**](WebhookEventsApi.md#onaccountdisconnected) | **POST** /account.disconnected | Account disconnected event |
| [**OnCommentReceived**](WebhookEventsApi.md#oncommentreceived) | **POST** /comment.received | Comment received event |
| [**OnMessageDeleted**](WebhookEventsApi.md#onmessagedeleted) | **POST** /message.deleted | Message deleted event |
| [**OnMessageDelivered**](WebhookEventsApi.md#onmessagedelivered) | **POST** /message.delivered | Message delivered event |
| [**OnMessageEdited**](WebhookEventsApi.md#onmessageedited) | **POST** /message.edited | Message edited event |
| [**OnMessageFailed**](WebhookEventsApi.md#onmessagefailed) | **POST** /message.failed | Message delivery failed event |
| [**OnMessageRead**](WebhookEventsApi.md#onmessageread) | **POST** /message.read | Message read event |
| [**OnMessageReceived**](WebhookEventsApi.md#onmessagereceived) | **POST** /message.received | Message received event |
| [**OnMessageSent**](WebhookEventsApi.md#onmessagesent) | **POST** /message.sent | Message sent event |
| [**OnPostCancelled**](WebhookEventsApi.md#onpostcancelled) | **POST** /post.cancelled | Post cancelled event |
| [**OnPostFailed**](WebhookEventsApi.md#onpostfailed) | **POST** /post.failed | Post failed event |
| [**OnPostPartial**](WebhookEventsApi.md#onpostpartial) | **POST** /post.partial | Post partial event |
| [**OnPostPublished**](WebhookEventsApi.md#onpostpublished) | **POST** /post.published | Post published event |
| [**OnPostRecycled**](WebhookEventsApi.md#onpostrecycled) | **POST** /post.recycled | Post recycled event |
| [**OnPostScheduled**](WebhookEventsApi.md#onpostscheduled) | **POST** /post.scheduled | Post scheduled event |
| [**OnReviewNew**](WebhookEventsApi.md#onreviewnew) | **POST** /review.new | Review new event |
| [**OnReviewUpdated**](WebhookEventsApi.md#onreviewupdated) | **POST** /review.updated | Review updated event |
| [**OnWebhookTest**](WebhookEventsApi.md#onwebhooktest) | **POST** /webhook.test | Webhook test event |

<a id="onaccountadsinitialsynccompleted"></a>
# **OnAccountAdsInitialSyncCompleted**
> void OnAccountAdsInitialSyncCompleted (WebhookPayloadAccountAdsInitialSyncCompleted webhookPayloadAccountAdsInitialSyncCompleted)

Ads initial sync completed event

Fired once per ads-enabled account when the initial sync (ad-account discovery + 90-day historical ad backfill) completes. The `sync` block reports whether the backfill succeeded and how many ads were synced. 

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
    public class OnAccountAdsInitialSyncCompletedExample
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
            var apiInstance = new WebhookEventsApi(httpClient, config, httpClientHandler);
            var webhookPayloadAccountAdsInitialSyncCompleted = new WebhookPayloadAccountAdsInitialSyncCompleted(); // WebhookPayloadAccountAdsInitialSyncCompleted | 

            try
            {
                // Ads initial sync completed event
                apiInstance.OnAccountAdsInitialSyncCompleted(webhookPayloadAccountAdsInitialSyncCompleted);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling WebhookEventsApi.OnAccountAdsInitialSyncCompleted: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the OnAccountAdsInitialSyncCompletedWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Ads initial sync completed event
    apiInstance.OnAccountAdsInitialSyncCompletedWithHttpInfo(webhookPayloadAccountAdsInitialSyncCompleted);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling WebhookEventsApi.OnAccountAdsInitialSyncCompletedWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **webhookPayloadAccountAdsInitialSyncCompleted** | [**WebhookPayloadAccountAdsInitialSyncCompleted**](WebhookPayloadAccountAdsInitialSyncCompleted.md) |  |  |

### Return type

void (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: Not defined


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Webhook received successfully |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="onaccountconnected"></a>
# **OnAccountConnected**
> void OnAccountConnected (WebhookPayloadAccountConnected webhookPayloadAccountConnected)

Account connected event

Fired when a social account is successfully connected.

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
    public class OnAccountConnectedExample
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
            var apiInstance = new WebhookEventsApi(httpClient, config, httpClientHandler);
            var webhookPayloadAccountConnected = new WebhookPayloadAccountConnected(); // WebhookPayloadAccountConnected | 

            try
            {
                // Account connected event
                apiInstance.OnAccountConnected(webhookPayloadAccountConnected);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling WebhookEventsApi.OnAccountConnected: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the OnAccountConnectedWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Account connected event
    apiInstance.OnAccountConnectedWithHttpInfo(webhookPayloadAccountConnected);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling WebhookEventsApi.OnAccountConnectedWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **webhookPayloadAccountConnected** | [**WebhookPayloadAccountConnected**](WebhookPayloadAccountConnected.md) |  |  |

### Return type

void (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: Not defined


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Webhook received successfully |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="onaccountdisconnected"></a>
# **OnAccountDisconnected**
> void OnAccountDisconnected (WebhookPayloadAccountDisconnected webhookPayloadAccountDisconnected)

Account disconnected event

Fired when a connected social account becomes disconnected.

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
    public class OnAccountDisconnectedExample
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
            var apiInstance = new WebhookEventsApi(httpClient, config, httpClientHandler);
            var webhookPayloadAccountDisconnected = new WebhookPayloadAccountDisconnected(); // WebhookPayloadAccountDisconnected | 

            try
            {
                // Account disconnected event
                apiInstance.OnAccountDisconnected(webhookPayloadAccountDisconnected);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling WebhookEventsApi.OnAccountDisconnected: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the OnAccountDisconnectedWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Account disconnected event
    apiInstance.OnAccountDisconnectedWithHttpInfo(webhookPayloadAccountDisconnected);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling WebhookEventsApi.OnAccountDisconnectedWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **webhookPayloadAccountDisconnected** | [**WebhookPayloadAccountDisconnected**](WebhookPayloadAccountDisconnected.md) |  |  |

### Return type

void (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: Not defined


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Webhook received successfully |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="oncommentreceived"></a>
# **OnCommentReceived**
> void OnCommentReceived (WebhookPayloadComment webhookPayloadComment)

Comment received event

Fired when a new comment is received on a tracked post.

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
    public class OnCommentReceivedExample
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
            var apiInstance = new WebhookEventsApi(httpClient, config, httpClientHandler);
            var webhookPayloadComment = new WebhookPayloadComment(); // WebhookPayloadComment | 

            try
            {
                // Comment received event
                apiInstance.OnCommentReceived(webhookPayloadComment);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling WebhookEventsApi.OnCommentReceived: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the OnCommentReceivedWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Comment received event
    apiInstance.OnCommentReceivedWithHttpInfo(webhookPayloadComment);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling WebhookEventsApi.OnCommentReceivedWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **webhookPayloadComment** | [**WebhookPayloadComment**](WebhookPayloadComment.md) |  |  |

### Return type

void (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: Not defined


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Webhook received successfully |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="onmessagedeleted"></a>
# **OnMessageDeleted**
> void OnMessageDeleted (WebhookPayloadMessageDeleted webhookPayloadMessageDeleted)

Message deleted event

Fired when a sender deletes (unsends) a message. Supported on Instagram (incoming unsend) and WhatsApp (when the business deletes an outgoing message via the Cloud API). The payload retains the pre-delete text and attachments so API consumers can access the original content for moderation or compliance — the Zernio dashboard UI hides it. 

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
    public class OnMessageDeletedExample
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
            var apiInstance = new WebhookEventsApi(httpClient, config, httpClientHandler);
            var webhookPayloadMessageDeleted = new WebhookPayloadMessageDeleted(); // WebhookPayloadMessageDeleted | 

            try
            {
                // Message deleted event
                apiInstance.OnMessageDeleted(webhookPayloadMessageDeleted);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling WebhookEventsApi.OnMessageDeleted: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the OnMessageDeletedWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Message deleted event
    apiInstance.OnMessageDeletedWithHttpInfo(webhookPayloadMessageDeleted);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling WebhookEventsApi.OnMessageDeletedWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **webhookPayloadMessageDeleted** | [**WebhookPayloadMessageDeleted**](WebhookPayloadMessageDeleted.md) |  |  |

### Return type

void (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: Not defined


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Webhook received successfully |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="onmessagedelivered"></a>
# **OnMessageDelivered**
> void OnMessageDelivered (WebhookPayloadMessageDeliveryStatus webhookPayloadMessageDeliveryStatus)

Message delivered event

Fired when an outgoing message is delivered to the recipient. Supported on WhatsApp and Facebook Messenger. 

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
    public class OnMessageDeliveredExample
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
            var apiInstance = new WebhookEventsApi(httpClient, config, httpClientHandler);
            var webhookPayloadMessageDeliveryStatus = new WebhookPayloadMessageDeliveryStatus(); // WebhookPayloadMessageDeliveryStatus | 

            try
            {
                // Message delivered event
                apiInstance.OnMessageDelivered(webhookPayloadMessageDeliveryStatus);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling WebhookEventsApi.OnMessageDelivered: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the OnMessageDeliveredWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Message delivered event
    apiInstance.OnMessageDeliveredWithHttpInfo(webhookPayloadMessageDeliveryStatus);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling WebhookEventsApi.OnMessageDeliveredWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **webhookPayloadMessageDeliveryStatus** | [**WebhookPayloadMessageDeliveryStatus**](WebhookPayloadMessageDeliveryStatus.md) |  |  |

### Return type

void (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: Not defined


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Webhook received successfully |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="onmessageedited"></a>
# **OnMessageEdited**
> void OnMessageEdited (WebhookPayloadMessageEdited webhookPayloadMessageEdited)

Message edited event

Fired when a sender edits a previously-sent message. Supported on Instagram, Facebook Messenger, and Telegram. The payload includes the full editHistory so consumers can show prior versions. 

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
    public class OnMessageEditedExample
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
            var apiInstance = new WebhookEventsApi(httpClient, config, httpClientHandler);
            var webhookPayloadMessageEdited = new WebhookPayloadMessageEdited(); // WebhookPayloadMessageEdited | 

            try
            {
                // Message edited event
                apiInstance.OnMessageEdited(webhookPayloadMessageEdited);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling WebhookEventsApi.OnMessageEdited: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the OnMessageEditedWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Message edited event
    apiInstance.OnMessageEditedWithHttpInfo(webhookPayloadMessageEdited);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling WebhookEventsApi.OnMessageEditedWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **webhookPayloadMessageEdited** | [**WebhookPayloadMessageEdited**](WebhookPayloadMessageEdited.md) |  |  |

### Return type

void (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: Not defined


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Webhook received successfully |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="onmessagefailed"></a>
# **OnMessageFailed**
> void OnMessageFailed (WebhookPayloadMessageDeliveryStatus webhookPayloadMessageDeliveryStatus)

Message delivery failed event

Fired when an outgoing message fails to deliver. Currently only emitted for WhatsApp (other platforms don't expose per-message failure via webhook). The payload error object contains code, title, and message from the platform. 

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
    public class OnMessageFailedExample
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
            var apiInstance = new WebhookEventsApi(httpClient, config, httpClientHandler);
            var webhookPayloadMessageDeliveryStatus = new WebhookPayloadMessageDeliveryStatus(); // WebhookPayloadMessageDeliveryStatus | 

            try
            {
                // Message delivery failed event
                apiInstance.OnMessageFailed(webhookPayloadMessageDeliveryStatus);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling WebhookEventsApi.OnMessageFailed: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the OnMessageFailedWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Message delivery failed event
    apiInstance.OnMessageFailedWithHttpInfo(webhookPayloadMessageDeliveryStatus);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling WebhookEventsApi.OnMessageFailedWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **webhookPayloadMessageDeliveryStatus** | [**WebhookPayloadMessageDeliveryStatus**](WebhookPayloadMessageDeliveryStatus.md) |  |  |

### Return type

void (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: Not defined


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Webhook received successfully |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="onmessageread"></a>
# **OnMessageRead**
> void OnMessageRead (WebhookPayloadMessageDeliveryStatus webhookPayloadMessageDeliveryStatus)

Message read event

Fired when an outgoing message is read by the recipient. Supported on WhatsApp, Facebook Messenger, and Instagram. 

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
    public class OnMessageReadExample
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
            var apiInstance = new WebhookEventsApi(httpClient, config, httpClientHandler);
            var webhookPayloadMessageDeliveryStatus = new WebhookPayloadMessageDeliveryStatus(); // WebhookPayloadMessageDeliveryStatus | 

            try
            {
                // Message read event
                apiInstance.OnMessageRead(webhookPayloadMessageDeliveryStatus);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling WebhookEventsApi.OnMessageRead: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the OnMessageReadWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Message read event
    apiInstance.OnMessageReadWithHttpInfo(webhookPayloadMessageDeliveryStatus);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling WebhookEventsApi.OnMessageReadWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **webhookPayloadMessageDeliveryStatus** | [**WebhookPayloadMessageDeliveryStatus**](WebhookPayloadMessageDeliveryStatus.md) |  |  |

### Return type

void (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: Not defined


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Webhook received successfully |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="onmessagereceived"></a>
# **OnMessageReceived**
> void OnMessageReceived (WebhookPayloadMessage webhookPayloadMessage)

Message received event

Fired when a new inbox message is received.

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
    public class OnMessageReceivedExample
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
            var apiInstance = new WebhookEventsApi(httpClient, config, httpClientHandler);
            var webhookPayloadMessage = new WebhookPayloadMessage(); // WebhookPayloadMessage | 

            try
            {
                // Message received event
                apiInstance.OnMessageReceived(webhookPayloadMessage);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling WebhookEventsApi.OnMessageReceived: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the OnMessageReceivedWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Message received event
    apiInstance.OnMessageReceivedWithHttpInfo(webhookPayloadMessage);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling WebhookEventsApi.OnMessageReceivedWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **webhookPayloadMessage** | [**WebhookPayloadMessage**](WebhookPayloadMessage.md) |  |  |

### Return type

void (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: Not defined


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Webhook received successfully |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="onmessagesent"></a>
# **OnMessageSent**
> void OnMessageSent (WebhookPayloadMessageSent webhookPayloadMessageSent)

Message sent event

Fired when a message is sent via the API.

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
    public class OnMessageSentExample
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
            var apiInstance = new WebhookEventsApi(httpClient, config, httpClientHandler);
            var webhookPayloadMessageSent = new WebhookPayloadMessageSent(); // WebhookPayloadMessageSent | 

            try
            {
                // Message sent event
                apiInstance.OnMessageSent(webhookPayloadMessageSent);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling WebhookEventsApi.OnMessageSent: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the OnMessageSentWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Message sent event
    apiInstance.OnMessageSentWithHttpInfo(webhookPayloadMessageSent);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling WebhookEventsApi.OnMessageSentWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **webhookPayloadMessageSent** | [**WebhookPayloadMessageSent**](WebhookPayloadMessageSent.md) |  |  |

### Return type

void (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: Not defined


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Webhook received successfully |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="onpostcancelled"></a>
# **OnPostCancelled**
> void OnPostCancelled (WebhookPayloadPost webhookPayloadPost)

Post cancelled event

Fired when a post publishing job is cancelled.

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
    public class OnPostCancelledExample
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
            var apiInstance = new WebhookEventsApi(httpClient, config, httpClientHandler);
            var webhookPayloadPost = new WebhookPayloadPost(); // WebhookPayloadPost | 

            try
            {
                // Post cancelled event
                apiInstance.OnPostCancelled(webhookPayloadPost);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling WebhookEventsApi.OnPostCancelled: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the OnPostCancelledWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Post cancelled event
    apiInstance.OnPostCancelledWithHttpInfo(webhookPayloadPost);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling WebhookEventsApi.OnPostCancelledWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **webhookPayloadPost** | [**WebhookPayloadPost**](WebhookPayloadPost.md) |  |  |

### Return type

void (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: Not defined


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Webhook received successfully |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="onpostfailed"></a>
# **OnPostFailed**
> void OnPostFailed (WebhookPayloadPost webhookPayloadPost)

Post failed event

Fired when a post fails to publish on all target platforms.

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
    public class OnPostFailedExample
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
            var apiInstance = new WebhookEventsApi(httpClient, config, httpClientHandler);
            var webhookPayloadPost = new WebhookPayloadPost(); // WebhookPayloadPost | 

            try
            {
                // Post failed event
                apiInstance.OnPostFailed(webhookPayloadPost);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling WebhookEventsApi.OnPostFailed: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the OnPostFailedWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Post failed event
    apiInstance.OnPostFailedWithHttpInfo(webhookPayloadPost);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling WebhookEventsApi.OnPostFailedWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **webhookPayloadPost** | [**WebhookPayloadPost**](WebhookPayloadPost.md) |  |  |

### Return type

void (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: Not defined


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Webhook received successfully |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="onpostpartial"></a>
# **OnPostPartial**
> void OnPostPartial (WebhookPayloadPost webhookPayloadPost)

Post partial event

Fired when a post publishes on some platforms and fails on others.

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
    public class OnPostPartialExample
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
            var apiInstance = new WebhookEventsApi(httpClient, config, httpClientHandler);
            var webhookPayloadPost = new WebhookPayloadPost(); // WebhookPayloadPost | 

            try
            {
                // Post partial event
                apiInstance.OnPostPartial(webhookPayloadPost);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling WebhookEventsApi.OnPostPartial: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the OnPostPartialWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Post partial event
    apiInstance.OnPostPartialWithHttpInfo(webhookPayloadPost);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling WebhookEventsApi.OnPostPartialWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **webhookPayloadPost** | [**WebhookPayloadPost**](WebhookPayloadPost.md) |  |  |

### Return type

void (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: Not defined


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Webhook received successfully |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="onpostpublished"></a>
# **OnPostPublished**
> void OnPostPublished (WebhookPayloadPost webhookPayloadPost)

Post published event

Fired when a post is successfully published.

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
    public class OnPostPublishedExample
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
            var apiInstance = new WebhookEventsApi(httpClient, config, httpClientHandler);
            var webhookPayloadPost = new WebhookPayloadPost(); // WebhookPayloadPost | 

            try
            {
                // Post published event
                apiInstance.OnPostPublished(webhookPayloadPost);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling WebhookEventsApi.OnPostPublished: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the OnPostPublishedWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Post published event
    apiInstance.OnPostPublishedWithHttpInfo(webhookPayloadPost);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling WebhookEventsApi.OnPostPublishedWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **webhookPayloadPost** | [**WebhookPayloadPost**](WebhookPayloadPost.md) |  |  |

### Return type

void (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: Not defined


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Webhook received successfully |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="onpostrecycled"></a>
# **OnPostRecycled**
> void OnPostRecycled (WebhookPayloadPost webhookPayloadPost)

Post recycled event

Fired when a post is recycled (cloned and re-scheduled for publishing).

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
    public class OnPostRecycledExample
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
            var apiInstance = new WebhookEventsApi(httpClient, config, httpClientHandler);
            var webhookPayloadPost = new WebhookPayloadPost(); // WebhookPayloadPost | 

            try
            {
                // Post recycled event
                apiInstance.OnPostRecycled(webhookPayloadPost);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling WebhookEventsApi.OnPostRecycled: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the OnPostRecycledWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Post recycled event
    apiInstance.OnPostRecycledWithHttpInfo(webhookPayloadPost);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling WebhookEventsApi.OnPostRecycledWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **webhookPayloadPost** | [**WebhookPayloadPost**](WebhookPayloadPost.md) |  |  |

### Return type

void (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: Not defined


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Webhook received successfully |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="onpostscheduled"></a>
# **OnPostScheduled**
> void OnPostScheduled (WebhookPayloadPost webhookPayloadPost)

Post scheduled event

Fired when a post is created and scheduled for publishing.

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
    public class OnPostScheduledExample
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
            var apiInstance = new WebhookEventsApi(httpClient, config, httpClientHandler);
            var webhookPayloadPost = new WebhookPayloadPost(); // WebhookPayloadPost | 

            try
            {
                // Post scheduled event
                apiInstance.OnPostScheduled(webhookPayloadPost);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling WebhookEventsApi.OnPostScheduled: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the OnPostScheduledWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Post scheduled event
    apiInstance.OnPostScheduledWithHttpInfo(webhookPayloadPost);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling WebhookEventsApi.OnPostScheduledWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **webhookPayloadPost** | [**WebhookPayloadPost**](WebhookPayloadPost.md) |  |  |

### Return type

void (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: Not defined


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Webhook received successfully |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="onreviewnew"></a>
# **OnReviewNew**
> void OnReviewNew (WebhookPayloadReviewNew webhookPayloadReviewNew)

Review new event

Fired when a new review is posted on a connected account. Currently supported for Google Business Profile (real-time via Pub/Sub). Requires the Inbox add-on. 

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
    public class OnReviewNewExample
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
            var apiInstance = new WebhookEventsApi(httpClient, config, httpClientHandler);
            var webhookPayloadReviewNew = new WebhookPayloadReviewNew(); // WebhookPayloadReviewNew | 

            try
            {
                // Review new event
                apiInstance.OnReviewNew(webhookPayloadReviewNew);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling WebhookEventsApi.OnReviewNew: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the OnReviewNewWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Review new event
    apiInstance.OnReviewNewWithHttpInfo(webhookPayloadReviewNew);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling WebhookEventsApi.OnReviewNewWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **webhookPayloadReviewNew** | [**WebhookPayloadReviewNew**](WebhookPayloadReviewNew.md) |  |  |

### Return type

void (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: Not defined


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Webhook received successfully |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="onreviewupdated"></a>
# **OnReviewUpdated**
> void OnReviewUpdated (WebhookPayloadReviewUpdated webhookPayloadReviewUpdated)

Review updated event

Fired when a review changes: the reviewer edits their text or rating, or a reply is added (via the API or directly through the Google Business dashboard). Payload shape matches review.new. Requires the Inbox add-on. 

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
    public class OnReviewUpdatedExample
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
            var apiInstance = new WebhookEventsApi(httpClient, config, httpClientHandler);
            var webhookPayloadReviewUpdated = new WebhookPayloadReviewUpdated(); // WebhookPayloadReviewUpdated | 

            try
            {
                // Review updated event
                apiInstance.OnReviewUpdated(webhookPayloadReviewUpdated);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling WebhookEventsApi.OnReviewUpdated: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the OnReviewUpdatedWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Review updated event
    apiInstance.OnReviewUpdatedWithHttpInfo(webhookPayloadReviewUpdated);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling WebhookEventsApi.OnReviewUpdatedWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **webhookPayloadReviewUpdated** | [**WebhookPayloadReviewUpdated**](WebhookPayloadReviewUpdated.md) |  |  |

### Return type

void (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: Not defined


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Webhook received successfully |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="onwebhooktest"></a>
# **OnWebhookTest**
> void OnWebhookTest (WebhookPayloadTest webhookPayloadTest)

Webhook test event

Fired when sending a test webhook to verify the endpoint configuration.

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
    public class OnWebhookTestExample
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
            var apiInstance = new WebhookEventsApi(httpClient, config, httpClientHandler);
            var webhookPayloadTest = new WebhookPayloadTest(); // WebhookPayloadTest | 

            try
            {
                // Webhook test event
                apiInstance.OnWebhookTest(webhookPayloadTest);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling WebhookEventsApi.OnWebhookTest: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the OnWebhookTestWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Webhook test event
    apiInstance.OnWebhookTestWithHttpInfo(webhookPayloadTest);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling WebhookEventsApi.OnWebhookTestWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **webhookPayloadTest** | [**WebhookPayloadTest**](WebhookPayloadTest.md) |  |  |

### Return type

void (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: Not defined


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Webhook received successfully |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

