# Late.Api.LinkedInMentionsApi

All URIs are relative to *https://getlate.dev/api*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**GetLinkedInMentions**](LinkedInMentionsApi.md#getlinkedinmentions) | **GET** /v1/accounts/{accountId}/linkedin-mentions | Resolve a LinkedIn profile or company URL to a URN for @mentions |

<a id="getlinkedinmentions"></a>
# **GetLinkedInMentions**
> GetLinkedInMentions200Response GetLinkedInMentions (string accountId, string url, string? displayName = null)

Resolve a LinkedIn profile or company URL to a URN for @mentions

Converts a LinkedIn profile URL (person) or company page URL (organization) to a URN that can be used to @mention them in posts.  **Supports both:** - **Person mentions:** `linkedin.com/in/username` or just `username` - **Organization mentions:** `linkedin.com/company/company-name` or `company/company-name`  **⚠️ Organization Admin Required for Person Mentions Only:** Person mentions require the connected LinkedIn account to have admin access to at least one LinkedIn Organization (Company Page). Organization mentions do NOT have this requirement - any LinkedIn account can tag companies.  **IMPORTANT - Display Name Requirement:** For **person mentions** to be clickable, the display name must **exactly match** what appears on their LinkedIn profile. - Organization mentions automatically retrieve the company name from LinkedIn API - Person mentions require the exact name, so provide the `displayName` parameter  **Mention Format:** Use the returned `mentionFormat` value directly in your post content: ``` Great insights from @[Miquel Palet](urn:li:person:4qj5ox-agD) on this topic! Excited to partner with @[Microsoft](urn:li:organization:1035)! ``` 

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
            var url = miquelpalet;  // string | LinkedIn profile URL, company URL, or vanity name. - Person: `miquelpalet`, `linkedin.com/in/miquelpalet` - Organization: `company/microsoft`, `linkedin.com/company/microsoft` 
            var displayName = Miquel Palet;  // string? | The exact display name as shown on LinkedIn. - **Person mentions:** Required for clickable mentions. If not provided, a name is derived from the vanity URL which may not match exactly. - **Organization mentions:** Optional. If not provided, the company name is automatically retrieved from LinkedIn.  (optional) 

            try
            {
                // Resolve a LinkedIn profile or company URL to a URN for @mentions
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
    // Resolve a LinkedIn profile or company URL to a URN for @mentions
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
| **url** | **string** | LinkedIn profile URL, company URL, or vanity name. - Person: &#x60;miquelpalet&#x60;, &#x60;linkedin.com/in/miquelpalet&#x60; - Organization: &#x60;company/microsoft&#x60;, &#x60;linkedin.com/company/microsoft&#x60;  |  |
| **displayName** | **string?** | The exact display name as shown on LinkedIn. - **Person mentions:** Required for clickable mentions. If not provided, a name is derived from the vanity URL which may not match exactly. - **Organization mentions:** Optional. If not provided, the company name is automatically retrieved from LinkedIn.  | [optional]  |

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

