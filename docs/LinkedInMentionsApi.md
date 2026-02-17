# Late.Api.LinkedInMentionsApi

All URIs are relative to *https://getlate.dev/api*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**GetLinkedInMentions**](LinkedInMentionsApi.md#getlinkedinmentions) | **GET** /v1/accounts/{accountId}/linkedin-mentions | Resolve LinkedIn mention |

<a id="getlinkedinmentions"></a>
# **GetLinkedInMentions**
> GetLinkedInMentions200Response GetLinkedInMentions (string accountId, string url, string? displayName = null)

Resolve LinkedIn mention

Converts a LinkedIn profile or company URL to a URN for @mentions in posts. Person mentions require org admin access. Use the returned mentionFormat in post content.

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
    public class GetLinkedInMentionsExample
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
            var apiInstance = new LinkedInMentionsApi(httpClient, config, httpClientHandler);
            var accountId = "accountId_example";  // string | The LinkedIn account ID
            var url = miquelpalet;  // string | LinkedIn profile URL, company URL, or vanity name.
            var displayName = Miquel Palet;  // string? | Exact display name as shown on LinkedIn. Required for person mentions to be clickable. Optional for org mentions. (optional) 

            try
            {
                // Resolve LinkedIn mention
                GetLinkedInMentions200Response result = apiInstance.GetLinkedInMentions(accountId, url, displayName);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling LinkedInMentionsApi.GetLinkedInMentions: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the GetLinkedInMentionsWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Resolve LinkedIn mention
    ApiResponse<GetLinkedInMentions200Response> response = apiInstance.GetLinkedInMentionsWithHttpInfo(accountId, url, displayName);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling LinkedInMentionsApi.GetLinkedInMentionsWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **accountId** | **string** | The LinkedIn account ID |  |
| **url** | **string** | LinkedIn profile URL, company URL, or vanity name. |  |
| **displayName** | **string?** | Exact display name as shown on LinkedIn. Required for person mentions to be clickable. Optional for org mentions. | [optional]  |

### Return type

[**GetLinkedInMentions200Response**](GetLinkedInMentions200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | URN resolved successfully |  -  |
| **400** | Invalid request or no organization found (for person mentions) |  -  |
| **401** | Unauthorized |  -  |
| **404** | Person or organization not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

