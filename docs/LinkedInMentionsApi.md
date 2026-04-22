# Zernio.Api.LinkedInMentionsApi

All URIs are relative to *https://zernio.com/api*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**GetLinkedInMentions**](LinkedInMentionsApi.md#getlinkedinmentions) | **GET** /v1/accounts/{accountId}/linkedin-mentions | Resolve LinkedIn mention |

<a id="getlinkedinmentions"></a>
# **GetLinkedInMentions**
> GetLinkedInMentions200Response GetLinkedInMentions (string accountId, string url, string? displayName = null)

Resolve LinkedIn mention

Converts a LinkedIn profile or company URL to a URN for @mentions in posts.  How to use LinkedIn @mentions (2-step workflow):  1. Call this endpoint with the LinkedIn profile/company URL to get the mention URN and format. 2. Embed the returned mentionFormat (e.g. @[Vincent Jong](urn:li:person:xxx)) directly in your post's content field.  Example: - Resolve: GET /v1/accounts/{id}/linkedin-mentions?url=linkedin.com/in/vincentjong&displayName=Vincent Jong - Returns: mentionFormat: \"@[Vincent Jong](urn:li:person:xxx)\" - Use in post content: \"Great talk with @[Vincent Jong](urn:li:person:xxx) today!\"  Important: The mentions array field in POST /v1/posts is stored for reference only and does NOT trigger @mentions on LinkedIn. You must embed the mention format directly in the content text.  Requirements: - Person mentions require the LinkedIn account to be admin of at least one organization. This is a LinkedIn API limitation: the only endpoints that resolve profile URLs to member URNs (vanityUrl, peopleTypeahead) are scoped to organization followers. There is no public LinkedIn API to resolve a vanity URL without organization context. - Organization mentions (e.g. @Microsoft) work without this requirement. - For person mentions to be clickable, the displayName parameter must exactly match the name shown on their LinkedIn profile. - Person mentions DO work when published from personal profiles (the URN just needs to be valid). The limitation is only in the resolution step (URL to URN), not in publishing. 

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
    public class GetLinkedInMentionsExample
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

