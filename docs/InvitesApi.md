# Late.Api.InvitesApi

All URIs are relative to *https://getlate.dev/api*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**CreateInviteToken**](InvitesApi.md#createinvitetoken) | **POST** /v1/invite/tokens | Create a team member invite token |

<a id="createinvitetoken"></a>
# **CreateInviteToken**
> CreateInviteToken201Response CreateInviteToken (CreateInviteTokenRequest createInviteTokenRequest)

Create a team member invite token

Generate a secure invite link to grant team members access to your profiles. Invites expire after 7 days and are single-use. 

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
    public class CreateInviteTokenExample
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
            var apiInstance = new InvitesApi(httpClient, config, httpClientHandler);
            var createInviteTokenRequest = new CreateInviteTokenRequest(); // CreateInviteTokenRequest | 

            try
            {
                // Create a team member invite token
                CreateInviteToken201Response result = apiInstance.CreateInviteToken(createInviteTokenRequest);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling InvitesApi.CreateInviteToken: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the CreateInviteTokenWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Create a team member invite token
    ApiResponse<CreateInviteToken201Response> response = apiInstance.CreateInviteTokenWithHttpInfo(createInviteTokenRequest);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling InvitesApi.CreateInviteTokenWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **createInviteTokenRequest** | [**CreateInviteTokenRequest**](CreateInviteTokenRequest.md) |  |  |

### Return type

[**CreateInviteToken201Response**](CreateInviteToken201Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Invite token created |  -  |
| **400** | Invalid request |  -  |
| **401** | Unauthorized |  -  |
| **403** | One or more profiles not found or not owned |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

