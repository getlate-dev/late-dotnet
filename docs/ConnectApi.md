# Late.Api.ConnectApi

All URIs are relative to *https://getlate.dev/api*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**CompleteTelegramConnect**](ConnectApi.md#completetelegramconnect) | **PATCH** /v1/connect/telegram | Check Telegram status |
| [**ConnectBlueskyCredentials**](ConnectApi.md#connectblueskycredentials) | **POST** /v1/connect/bluesky/credentials | Connect Bluesky account |
| [**GetConnectUrl**](ConnectApi.md#getconnecturl) | **GET** /v1/connect/{platform} | Get OAuth connect URL |
| [**GetFacebookPages**](ConnectApi.md#getfacebookpages) | **GET** /v1/accounts/{accountId}/facebook-page | List Facebook pages |
| [**GetGmbLocations**](ConnectApi.md#getgmblocations) | **GET** /v1/accounts/{accountId}/gmb-locations | List GBP locations |
| [**GetLinkedInOrganizations**](ConnectApi.md#getlinkedinorganizations) | **GET** /v1/accounts/{accountId}/linkedin-organizations | List LinkedIn orgs |
| [**GetPendingOAuthData**](ConnectApi.md#getpendingoauthdata) | **GET** /v1/connect/pending-data | Get pending OAuth data |
| [**GetPinterestBoards**](ConnectApi.md#getpinterestboards) | **GET** /v1/accounts/{accountId}/pinterest-boards | List Pinterest boards |
| [**GetRedditFlairs**](ConnectApi.md#getredditflairs) | **GET** /v1/accounts/{accountId}/reddit-flairs | List subreddit flairs |
| [**GetRedditSubreddits**](ConnectApi.md#getredditsubreddits) | **GET** /v1/accounts/{accountId}/reddit-subreddits | List Reddit subreddits |
| [**GetTelegramConnectStatus**](ConnectApi.md#gettelegramconnectstatus) | **GET** /v1/connect/telegram | Generate Telegram code |
| [**HandleOAuthCallback**](ConnectApi.md#handleoauthcallback) | **POST** /v1/connect/{platform} | Complete OAuth callback |
| [**InitiateTelegramConnect**](ConnectApi.md#initiatetelegramconnect) | **POST** /v1/connect/telegram | Connect Telegram directly |
| [**ListFacebookPages**](ConnectApi.md#listfacebookpages) | **GET** /v1/connect/facebook/select-page | List Facebook pages |
| [**ListGoogleBusinessLocations**](ConnectApi.md#listgooglebusinesslocations) | **GET** /v1/connect/googlebusiness/locations | List GBP locations |
| [**ListLinkedInOrganizations**](ConnectApi.md#listlinkedinorganizations) | **GET** /v1/connect/linkedin/organizations | List LinkedIn orgs |
| [**ListPinterestBoardsForSelection**](ConnectApi.md#listpinterestboardsforselection) | **GET** /v1/connect/pinterest/select-board | List Pinterest boards |
| [**ListSnapchatProfiles**](ConnectApi.md#listsnapchatprofiles) | **GET** /v1/connect/snapchat/select-profile | List Snapchat profiles |
| [**SelectFacebookPage**](ConnectApi.md#selectfacebookpage) | **POST** /v1/connect/facebook/select-page | Select Facebook page |
| [**SelectGoogleBusinessLocation**](ConnectApi.md#selectgooglebusinesslocation) | **POST** /v1/connect/googlebusiness/select-location | Select GBP location |
| [**SelectLinkedInOrganization**](ConnectApi.md#selectlinkedinorganization) | **POST** /v1/connect/linkedin/select-organization | Select LinkedIn org |
| [**SelectPinterestBoard**](ConnectApi.md#selectpinterestboard) | **POST** /v1/connect/pinterest/select-board | Select Pinterest board |
| [**SelectSnapchatProfile**](ConnectApi.md#selectsnapchatprofile) | **POST** /v1/connect/snapchat/select-profile | Select Snapchat profile |
| [**UpdateFacebookPage**](ConnectApi.md#updatefacebookpage) | **PUT** /v1/accounts/{accountId}/facebook-page | Update Facebook page |
| [**UpdateGmbLocation**](ConnectApi.md#updategmblocation) | **PUT** /v1/accounts/{accountId}/gmb-locations | Update GBP location |
| [**UpdateLinkedInOrganization**](ConnectApi.md#updatelinkedinorganization) | **PUT** /v1/accounts/{accountId}/linkedin-organization | Switch LinkedIn account type |
| [**UpdatePinterestBoards**](ConnectApi.md#updatepinterestboards) | **PUT** /v1/accounts/{accountId}/pinterest-boards | Set default Pinterest board |
| [**UpdateRedditSubreddits**](ConnectApi.md#updateredditsubreddits) | **PUT** /v1/accounts/{accountId}/reddit-subreddits | Set default subreddit |

<a id="completetelegramconnect"></a>
# **CompleteTelegramConnect**
> CompleteTelegramConnect200Response CompleteTelegramConnect (string code)

Check Telegram status

Poll this endpoint to check if a Telegram access code has been used to connect a channel/group. Recommended polling interval: 3 seconds. Status values: pending (waiting for user), connected (channel/group linked), expired (generate a new code). 

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
    public class CompleteTelegramConnectExample
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
            var apiInstance = new ConnectApi(httpClient, config, httpClientHandler);
            var code = LATE-ABC123;  // string | The access code to check status for

            try
            {
                // Check Telegram status
                CompleteTelegramConnect200Response result = apiInstance.CompleteTelegramConnect(code);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling ConnectApi.CompleteTelegramConnect: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the CompleteTelegramConnectWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Check Telegram status
    ApiResponse<CompleteTelegramConnect200Response> response = apiInstance.CompleteTelegramConnectWithHttpInfo(code);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling ConnectApi.CompleteTelegramConnectWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **code** | **string** | The access code to check status for |  |

### Return type

[**CompleteTelegramConnect200Response**](CompleteTelegramConnect200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Connection status |  -  |
| **401** | Unauthorized |  -  |
| **404** | Code not found |  -  |
| **500** | Internal error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="connectblueskycredentials"></a>
# **ConnectBlueskyCredentials**
> ConnectBlueskyCredentials200Response ConnectBlueskyCredentials (ConnectBlueskyCredentialsRequest connectBlueskyCredentialsRequest)

Connect Bluesky account

Connect a Bluesky account using identifier (handle or email) and an app password. To get your userId for the state parameter, call GET /v1/users which includes a currentUserId field. 

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
    public class ConnectBlueskyCredentialsExample
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
            var apiInstance = new ConnectApi(httpClient, config, httpClientHandler);
            var connectBlueskyCredentialsRequest = new ConnectBlueskyCredentialsRequest(); // ConnectBlueskyCredentialsRequest | 

            try
            {
                // Connect Bluesky account
                ConnectBlueskyCredentials200Response result = apiInstance.ConnectBlueskyCredentials(connectBlueskyCredentialsRequest);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling ConnectApi.ConnectBlueskyCredentials: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the ConnectBlueskyCredentialsWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Connect Bluesky account
    ApiResponse<ConnectBlueskyCredentials200Response> response = apiInstance.ConnectBlueskyCredentialsWithHttpInfo(connectBlueskyCredentialsRequest);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling ConnectApi.ConnectBlueskyCredentialsWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **connectBlueskyCredentialsRequest** | [**ConnectBlueskyCredentialsRequest**](ConnectBlueskyCredentialsRequest.md) |  |  |

### Return type

[**ConnectBlueskyCredentials200Response**](ConnectBlueskyCredentials200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Bluesky connected successfully |  -  |
| **400** | Invalid request - missing fields or invalid state format |  -  |
| **401** | Unauthorized |  -  |
| **500** | Internal error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="getconnecturl"></a>
# **GetConnectUrl**
> GetConnectUrl200Response GetConnectUrl (string platform, string profileId, string? redirectUrl = null)

Get OAuth connect URL

Initiate an OAuth connection flow for any supported platform. Standard flow: call this endpoint, redirect user to the returned authUrl, Late hosts the selection UI, then redirects to your redirect_url. Headless mode (Facebook, LinkedIn, Pinterest, Google Business, Snapchat): add headless=true to this endpoint. After OAuth, the user is redirected to your redirect_url with OAuth data (profileId, tempToken, userProfile, connect_token, platform, step). Use the platform-specific selection endpoints to fetch options and save the selection. LinkedIn uses pendingDataToken instead of tempToken; call GET /v1/connect/pending-data?token=TOKEN to retrieve OAuth data (one-time use, expires in 10 minutes). 

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
    public class GetConnectUrlExample
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
            var apiInstance = new ConnectApi(httpClient, config, httpClientHandler);
            var platform = "facebook";  // string | Social media platform to connect
            var profileId = "profileId_example";  // string | Your Late profile ID (get from /v1/profiles)
            var redirectUrl = "redirectUrl_example";  // string? | Your custom redirect URL after connection completes. Standard mode: Late redirects here with ?connected={platform}&profileId=X&username=Y. Headless mode: pass headless=true on this endpoint. User is redirected to your URL with OAuth data (profileId, tempToken, userProfile, connect_token, platform, step). See endpoint description for details.  (optional) 

            try
            {
                // Get OAuth connect URL
                GetConnectUrl200Response result = apiInstance.GetConnectUrl(platform, profileId, redirectUrl);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling ConnectApi.GetConnectUrl: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the GetConnectUrlWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Get OAuth connect URL
    ApiResponse<GetConnectUrl200Response> response = apiInstance.GetConnectUrlWithHttpInfo(platform, profileId, redirectUrl);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling ConnectApi.GetConnectUrlWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **platform** | **string** | Social media platform to connect |  |
| **profileId** | **string** | Your Late profile ID (get from /v1/profiles) |  |
| **redirectUrl** | **string?** | Your custom redirect URL after connection completes. Standard mode: Late redirects here with ?connected&#x3D;{platform}&amp;profileId&#x3D;X&amp;username&#x3D;Y. Headless mode: pass headless&#x3D;true on this endpoint. User is redirected to your URL with OAuth data (profileId, tempToken, userProfile, connect_token, platform, step). See endpoint description for details.  | [optional]  |

### Return type

[**GetConnectUrl200Response**](GetConnectUrl200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OAuth authorization URL to redirect user to |  -  |
| **400** | Missing/invalid parameters (e.g., invalid profileId format) |  -  |
| **401** | Unauthorized |  -  |
| **403** | No access to profile, or BYOK required for AppSumo Twitter |  -  |
| **404** | Profile not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="getfacebookpages"></a>
# **GetFacebookPages**
> GetFacebookPages200Response GetFacebookPages (string accountId)

List Facebook pages

Returns all Facebook pages the connected account has access to, including the currently selected page.

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
    public class GetFacebookPagesExample
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
            var apiInstance = new ConnectApi(httpClient, config, httpClientHandler);
            var accountId = "accountId_example";  // string | 

            try
            {
                // List Facebook pages
                GetFacebookPages200Response result = apiInstance.GetFacebookPages(accountId);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling ConnectApi.GetFacebookPages: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the GetFacebookPagesWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // List Facebook pages
    ApiResponse<GetFacebookPages200Response> response = apiInstance.GetFacebookPagesWithHttpInfo(accountId);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling ConnectApi.GetFacebookPagesWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **accountId** | **string** |  |  |

### Return type

[**GetFacebookPages200Response**](GetFacebookPages200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Pages list |  -  |
| **401** | Unauthorized |  -  |
| **404** | Account not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="getgmblocations"></a>
# **GetGmbLocations**
> GetGmbLocations200Response GetGmbLocations (string accountId)

List GBP locations

Returns all Google Business Profile locations the connected account has access to, including the currently selected location.

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
    public class GetGmbLocationsExample
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
            var apiInstance = new ConnectApi(httpClient, config, httpClientHandler);
            var accountId = "accountId_example";  // string | 

            try
            {
                // List GBP locations
                GetGmbLocations200Response result = apiInstance.GetGmbLocations(accountId);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling ConnectApi.GetGmbLocations: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the GetGmbLocationsWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // List GBP locations
    ApiResponse<GetGmbLocations200Response> response = apiInstance.GetGmbLocationsWithHttpInfo(accountId);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling ConnectApi.GetGmbLocationsWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **accountId** | **string** |  |  |

### Return type

[**GetGmbLocations200Response**](GetGmbLocations200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Locations list |  -  |
| **401** | Unauthorized |  -  |
| **404** | Account not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="getlinkedinorganizations"></a>
# **GetLinkedInOrganizations**
> GetLinkedInOrganizations200Response GetLinkedInOrganizations (string accountId)

List LinkedIn orgs

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
    public class GetLinkedInOrganizationsExample
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
            var apiInstance = new ConnectApi(httpClient, config, httpClientHandler);
            var accountId = "accountId_example";  // string | 

            try
            {
                // List LinkedIn orgs
                GetLinkedInOrganizations200Response result = apiInstance.GetLinkedInOrganizations(accountId);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling ConnectApi.GetLinkedInOrganizations: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the GetLinkedInOrganizationsWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // List LinkedIn orgs
    ApiResponse<GetLinkedInOrganizations200Response> response = apiInstance.GetLinkedInOrganizationsWithHttpInfo(accountId);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling ConnectApi.GetLinkedInOrganizationsWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **accountId** | **string** |  |  |

### Return type

[**GetLinkedInOrganizations200Response**](GetLinkedInOrganizations200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Organizations list |  -  |
| **401** | Unauthorized |  -  |
| **404** | Account not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="getpendingoauthdata"></a>
# **GetPendingOAuthData**
> GetPendingOAuthData200Response GetPendingOAuthData (string token)

Get pending OAuth data

Fetch pending OAuth data for headless mode. Platforms like LinkedIn store OAuth selection data (organizations, pages, etc.) server-side to prevent URI_TOO_LONG errors. After OAuth redirect, use the pendingDataToken from the URL to fetch the stored data. This endpoint is one-time use (data is deleted after fetch) and expires after 10 minutes. No authentication required, just the token. 

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
    public class GetPendingOAuthDataExample
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
            var apiInstance = new ConnectApi(httpClient, config, httpClientHandler);
            var token = "token_example";  // string | The pending data token from the OAuth redirect URL (pendingDataToken parameter)

            try
            {
                // Get pending OAuth data
                GetPendingOAuthData200Response result = apiInstance.GetPendingOAuthData(token);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling ConnectApi.GetPendingOAuthData: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the GetPendingOAuthDataWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Get pending OAuth data
    ApiResponse<GetPendingOAuthData200Response> response = apiInstance.GetPendingOAuthDataWithHttpInfo(token);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling ConnectApi.GetPendingOAuthDataWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **token** | **string** | The pending data token from the OAuth redirect URL (pendingDataToken parameter) |  |

### Return type

[**GetPendingOAuthData200Response**](GetPendingOAuthData200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OAuth data fetched successfully |  -  |
| **400** | Missing token parameter |  -  |
| **404** | Token not found or expired |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="getpinterestboards"></a>
# **GetPinterestBoards**
> GetPinterestBoards200Response GetPinterestBoards (string accountId)

List Pinterest boards

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
    public class GetPinterestBoardsExample
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
            var apiInstance = new ConnectApi(httpClient, config, httpClientHandler);
            var accountId = "accountId_example";  // string | 

            try
            {
                // List Pinterest boards
                GetPinterestBoards200Response result = apiInstance.GetPinterestBoards(accountId);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling ConnectApi.GetPinterestBoards: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the GetPinterestBoardsWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // List Pinterest boards
    ApiResponse<GetPinterestBoards200Response> response = apiInstance.GetPinterestBoardsWithHttpInfo(accountId);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling ConnectApi.GetPinterestBoardsWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **accountId** | **string** |  |  |

### Return type

[**GetPinterestBoards200Response**](GetPinterestBoards200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Boards list |  -  |
| **400** | Not a Pinterest account |  -  |
| **401** | Unauthorized |  -  |
| **404** | Account not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="getredditflairs"></a>
# **GetRedditFlairs**
> GetRedditFlairs200Response GetRedditFlairs (string accountId, string subreddit)

List subreddit flairs

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
    public class GetRedditFlairsExample
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
            var apiInstance = new ConnectApi(httpClient, config, httpClientHandler);
            var accountId = "accountId_example";  // string | 
            var subreddit = "subreddit_example";  // string | Subreddit name (without \"r/\" prefix) to fetch flairs for

            try
            {
                // List subreddit flairs
                GetRedditFlairs200Response result = apiInstance.GetRedditFlairs(accountId, subreddit);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling ConnectApi.GetRedditFlairs: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the GetRedditFlairsWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // List subreddit flairs
    ApiResponse<GetRedditFlairs200Response> response = apiInstance.GetRedditFlairsWithHttpInfo(accountId, subreddit);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling ConnectApi.GetRedditFlairsWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **accountId** | **string** |  |  |
| **subreddit** | **string** | Subreddit name (without \&quot;r/\&quot; prefix) to fetch flairs for |  |

### Return type

[**GetRedditFlairs200Response**](GetRedditFlairs200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Flairs list |  -  |
| **400** | Not a Reddit account or missing subreddit parameter |  -  |
| **401** | Unauthorized |  -  |
| **404** | Account not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="getredditsubreddits"></a>
# **GetRedditSubreddits**
> GetRedditSubreddits200Response GetRedditSubreddits (string accountId)

List Reddit subreddits

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
    public class GetRedditSubredditsExample
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
            var apiInstance = new ConnectApi(httpClient, config, httpClientHandler);
            var accountId = "accountId_example";  // string | 

            try
            {
                // List Reddit subreddits
                GetRedditSubreddits200Response result = apiInstance.GetRedditSubreddits(accountId);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling ConnectApi.GetRedditSubreddits: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the GetRedditSubredditsWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // List Reddit subreddits
    ApiResponse<GetRedditSubreddits200Response> response = apiInstance.GetRedditSubredditsWithHttpInfo(accountId);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling ConnectApi.GetRedditSubredditsWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **accountId** | **string** |  |  |

### Return type

[**GetRedditSubreddits200Response**](GetRedditSubreddits200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Subreddits list |  -  |
| **400** | Not a Reddit account |  -  |
| **401** | Unauthorized |  -  |
| **404** | Account not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="gettelegramconnectstatus"></a>
# **GetTelegramConnectStatus**
> GetTelegramConnectStatus200Response GetTelegramConnectStatus (string profileId)

Generate Telegram code

Generate a unique access code for connecting a Telegram channel or group. Flow: get an access code (valid 15 minutes), add the bot as admin in your channel/group, open a private chat with the bot, send the code + @yourchannel (e.g. LATE-ABC123 @mychannel), then poll PATCH /v1/connect/telegram?code={CODE} to check connection status. For private channels without a public username, forward any message from the channel to the bot along with the access code. 

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
    public class GetTelegramConnectStatusExample
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
            var apiInstance = new ConnectApi(httpClient, config, httpClientHandler);
            var profileId = "profileId_example";  // string | The profile ID to connect the Telegram account to

            try
            {
                // Generate Telegram code
                GetTelegramConnectStatus200Response result = apiInstance.GetTelegramConnectStatus(profileId);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling ConnectApi.GetTelegramConnectStatus: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the GetTelegramConnectStatusWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Generate Telegram code
    ApiResponse<GetTelegramConnectStatus200Response> response = apiInstance.GetTelegramConnectStatusWithHttpInfo(profileId);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling ConnectApi.GetTelegramConnectStatusWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **profileId** | **string** | The profile ID to connect the Telegram account to |  |

### Return type

[**GetTelegramConnectStatus200Response**](GetTelegramConnectStatus200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Access code generated |  -  |
| **400** | Profile ID required or invalid format |  -  |
| **401** | Unauthorized |  -  |
| **403** | No access to this profile |  -  |
| **404** | Profile not found |  -  |
| **500** | Internal error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="handleoauthcallback"></a>
# **HandleOAuthCallback**
> void HandleOAuthCallback (string platform, HandleOAuthCallbackRequest handleOAuthCallbackRequest)

Complete OAuth callback

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
    public class HandleOAuthCallbackExample
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
            var apiInstance = new ConnectApi(httpClient, config, httpClientHandler);
            var platform = "platform_example";  // string | 
            var handleOAuthCallbackRequest = new HandleOAuthCallbackRequest(); // HandleOAuthCallbackRequest | 

            try
            {
                // Complete OAuth callback
                apiInstance.HandleOAuthCallback(platform, handleOAuthCallbackRequest);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling ConnectApi.HandleOAuthCallback: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the HandleOAuthCallbackWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Complete OAuth callback
    apiInstance.HandleOAuthCallbackWithHttpInfo(platform, handleOAuthCallbackRequest);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling ConnectApi.HandleOAuthCallbackWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **platform** | **string** |  |  |
| **handleOAuthCallbackRequest** | [**HandleOAuthCallbackRequest**](HandleOAuthCallbackRequest.md) |  |  |

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
| **200** | Account connected |  -  |
| **400** | Invalid params |  -  |
| **401** | Unauthorized |  -  |
| **403** | BYOK required for AppSumo Twitter |  -  |
| **500** | Failed to connect account |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="initiatetelegramconnect"></a>
# **InitiateTelegramConnect**
> InitiateTelegramConnect200Response InitiateTelegramConnect (InitiateTelegramConnectRequest initiateTelegramConnectRequest)

Connect Telegram directly

Connect a Telegram channel/group directly using the chat ID.  This is an alternative to the access code flow for power users who know their Telegram chat ID. The bot must already be added as an administrator in the channel/group. 

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
    public class InitiateTelegramConnectExample
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
            var apiInstance = new ConnectApi(httpClient, config, httpClientHandler);
            var initiateTelegramConnectRequest = new InitiateTelegramConnectRequest(); // InitiateTelegramConnectRequest | 

            try
            {
                // Connect Telegram directly
                InitiateTelegramConnect200Response result = apiInstance.InitiateTelegramConnect(initiateTelegramConnectRequest);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling ConnectApi.InitiateTelegramConnect: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the InitiateTelegramConnectWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Connect Telegram directly
    ApiResponse<InitiateTelegramConnect200Response> response = apiInstance.InitiateTelegramConnectWithHttpInfo(initiateTelegramConnectRequest);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling ConnectApi.InitiateTelegramConnectWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **initiateTelegramConnectRequest** | [**InitiateTelegramConnectRequest**](InitiateTelegramConnectRequest.md) |  |  |

### Return type

[**InitiateTelegramConnect200Response**](InitiateTelegramConnect200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Telegram channel connected successfully |  -  |
| **400** | Chat ID required |  -  |
| **401** | Unauthorized |  -  |
| **403** | No access to this profile |  -  |
| **404** | Profile not found |  -  |
| **500** | Internal error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="listfacebookpages"></a>
# **ListFacebookPages**
> ListFacebookPages200Response ListFacebookPages (string profileId, string tempToken)

List Facebook pages

Returns the list of Facebook Pages the user can manage after OAuth. Extract tempToken and userProfile from the OAuth redirect params and pass them here. Use the X-Connect-Token header if connecting via API key.

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
    public class ListFacebookPagesExample
    {
        public static void Main()
        {
            Configuration config = new Configuration();
            config.BasePath = "https://getlate.dev/api";
            // Configure API key authorization: connectToken
            config.AddApiKey("X-Connect-Token", "YOUR_API_KEY");
            // Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
            // config.AddApiKeyPrefix("X-Connect-Token", "Bearer");
            // Configure Bearer token for authorization: bearerAuth
            config.AccessToken = "YOUR_BEARER_TOKEN";

            // create instances of HttpClient, HttpClientHandler to be reused later with different Api classes
            HttpClient httpClient = new HttpClient();
            HttpClientHandler httpClientHandler = new HttpClientHandler();
            var apiInstance = new ConnectApi(httpClient, config, httpClientHandler);
            var profileId = "profileId_example";  // string | Profile ID from your connection flow
            var tempToken = "tempToken_example";  // string | Temporary Facebook access token from the OAuth callback redirect

            try
            {
                // List Facebook pages
                ListFacebookPages200Response result = apiInstance.ListFacebookPages(profileId, tempToken);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling ConnectApi.ListFacebookPages: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the ListFacebookPagesWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // List Facebook pages
    ApiResponse<ListFacebookPages200Response> response = apiInstance.ListFacebookPagesWithHttpInfo(profileId, tempToken);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling ConnectApi.ListFacebookPagesWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **profileId** | **string** | Profile ID from your connection flow |  |
| **tempToken** | **string** | Temporary Facebook access token from the OAuth callback redirect |  |

### Return type

[**ListFacebookPages200Response**](ListFacebookPages200Response.md)

### Authorization

[connectToken](../README.md#connectToken), [bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | List of Facebook Pages available for connection |  -  |
| **400** | Missing required parameters (profileId or tempToken) |  -  |
| **401** | Unauthorized |  -  |
| **500** | Failed to fetch pages (e.g., invalid token, insufficient permissions) |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="listgooglebusinesslocations"></a>
# **ListGoogleBusinessLocations**
> ListGoogleBusinessLocations200Response ListGoogleBusinessLocations (string profileId, string tempToken)

List GBP locations

For headless/whitelabel flows. After Google Business OAuth with headless=true, you'll be redirected to your redirect_url with tempToken and userProfile params. Call this endpoint to retrieve the list of locations the user can manage, then build your own UI to let them select one. Use the X-Connect-Token header if you initiated the connection via API key. 

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
    public class ListGoogleBusinessLocationsExample
    {
        public static void Main()
        {
            Configuration config = new Configuration();
            config.BasePath = "https://getlate.dev/api";
            // Configure API key authorization: connectToken
            config.AddApiKey("X-Connect-Token", "YOUR_API_KEY");
            // Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
            // config.AddApiKeyPrefix("X-Connect-Token", "Bearer");
            // Configure Bearer token for authorization: bearerAuth
            config.AccessToken = "YOUR_BEARER_TOKEN";

            // create instances of HttpClient, HttpClientHandler to be reused later with different Api classes
            HttpClient httpClient = new HttpClient();
            HttpClientHandler httpClientHandler = new HttpClientHandler();
            var apiInstance = new ConnectApi(httpClient, config, httpClientHandler);
            var profileId = "profileId_example";  // string | Profile ID from your connection flow
            var tempToken = "tempToken_example";  // string | Temporary Google access token from the OAuth callback redirect

            try
            {
                // List GBP locations
                ListGoogleBusinessLocations200Response result = apiInstance.ListGoogleBusinessLocations(profileId, tempToken);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling ConnectApi.ListGoogleBusinessLocations: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the ListGoogleBusinessLocationsWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // List GBP locations
    ApiResponse<ListGoogleBusinessLocations200Response> response = apiInstance.ListGoogleBusinessLocationsWithHttpInfo(profileId, tempToken);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling ConnectApi.ListGoogleBusinessLocationsWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **profileId** | **string** | Profile ID from your connection flow |  |
| **tempToken** | **string** | Temporary Google access token from the OAuth callback redirect |  |

### Return type

[**ListGoogleBusinessLocations200Response**](ListGoogleBusinessLocations200Response.md)

### Authorization

[connectToken](../README.md#connectToken), [bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | List of Google Business locations available for connection |  -  |
| **400** | Missing required parameters (profileId or tempToken) |  -  |
| **401** | Unauthorized |  -  |
| **500** | Failed to fetch locations (e.g., invalid token, insufficient permissions) |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="listlinkedinorganizations"></a>
# **ListLinkedInOrganizations**
> ListLinkedInOrganizations200Response ListLinkedInOrganizations (string tempToken, string orgIds)

List LinkedIn orgs

Fetch full organization details for custom UI. After LinkedIn OAuth in headless mode, the redirect URL only contains id, urn, and name fields. Use this endpoint to fetch full details including logos, vanity names, websites, and more. No authentication required, just the tempToken from the OAuth redirect. 

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
    public class ListLinkedInOrganizationsExample
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
            var apiInstance = new ConnectApi(httpClient, config, httpClientHandler);
            var tempToken = "tempToken_example";  // string | The temporary LinkedIn access token from the OAuth redirect
            var orgIds = 12345678,87654321,11111111;  // string | Comma-separated list of organization IDs to fetch details for (max 100)

            try
            {
                // List LinkedIn orgs
                ListLinkedInOrganizations200Response result = apiInstance.ListLinkedInOrganizations(tempToken, orgIds);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling ConnectApi.ListLinkedInOrganizations: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the ListLinkedInOrganizationsWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // List LinkedIn orgs
    ApiResponse<ListLinkedInOrganizations200Response> response = apiInstance.ListLinkedInOrganizationsWithHttpInfo(tempToken, orgIds);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling ConnectApi.ListLinkedInOrganizationsWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **tempToken** | **string** | The temporary LinkedIn access token from the OAuth redirect |  |
| **orgIds** | **string** | Comma-separated list of organization IDs to fetch details for (max 100) |  |

### Return type

[**ListLinkedInOrganizations200Response**](ListLinkedInOrganizations200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Organization details fetched successfully |  -  |
| **400** | Missing required parameters or too many organization IDs |  -  |
| **500** | Failed to fetch organization details |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="listpinterestboardsforselection"></a>
# **ListPinterestBoardsForSelection**
> ListPinterestBoardsForSelection200Response ListPinterestBoardsForSelection (string xConnectToken, string profileId, string tempToken)

List Pinterest boards

Retrieve Pinterest boards for headless selection UI. After Pinterest OAuth with headless=true, you'll be redirected to your redirect_url with tempToken and userProfile params. Call this endpoint to retrieve the list of boards the user can post to, then build your UI and call POST /v1/connect/pinterest/select-board to save the selection. Use X-Connect-Token header with the connect_token from the redirect URL. 

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
    public class ListPinterestBoardsForSelectionExample
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
            var apiInstance = new ConnectApi(httpClient, config, httpClientHandler);
            var xConnectToken = "xConnectToken_example";  // string | Short-lived connect token from the OAuth redirect
            var profileId = "profileId_example";  // string | Your Late profile ID
            var tempToken = "tempToken_example";  // string | Temporary Pinterest access token from the OAuth callback redirect

            try
            {
                // List Pinterest boards
                ListPinterestBoardsForSelection200Response result = apiInstance.ListPinterestBoardsForSelection(xConnectToken, profileId, tempToken);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling ConnectApi.ListPinterestBoardsForSelection: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the ListPinterestBoardsForSelectionWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // List Pinterest boards
    ApiResponse<ListPinterestBoardsForSelection200Response> response = apiInstance.ListPinterestBoardsForSelectionWithHttpInfo(xConnectToken, profileId, tempToken);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling ConnectApi.ListPinterestBoardsForSelectionWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **xConnectToken** | **string** | Short-lived connect token from the OAuth redirect |  |
| **profileId** | **string** | Your Late profile ID |  |
| **tempToken** | **string** | Temporary Pinterest access token from the OAuth callback redirect |  |

### Return type

[**ListPinterestBoardsForSelection200Response**](ListPinterestBoardsForSelection200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | List of Pinterest Boards available for connection |  -  |
| **400** | Missing required parameters |  -  |
| **401** | Unauthorized |  -  |
| **403** | No access to profile |  -  |
| **500** | Failed to fetch boards |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="listsnapchatprofiles"></a>
# **ListSnapchatProfiles**
> ListSnapchatProfiles200Response ListSnapchatProfiles (string xConnectToken, string profileId, string tempToken)

List Snapchat profiles

For headless/whitelabel flows. After Snapchat OAuth with headless=true, you'll be redirected to your redirect_url with tempToken, userProfile, and publicProfiles params. Call this endpoint to retrieve the list of Snapchat Public Profiles the user can post to, then build your UI and call POST /v1/connect/snapchat/select-profile to save the selection. Use X-Connect-Token header with the connect_token from the redirect URL. 

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
    public class ListSnapchatProfilesExample
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
            var apiInstance = new ConnectApi(httpClient, config, httpClientHandler);
            var xConnectToken = "xConnectToken_example";  // string | Short-lived connect token from the OAuth redirect
            var profileId = "profileId_example";  // string | Your Late profile ID
            var tempToken = "tempToken_example";  // string | Temporary Snapchat access token from the OAuth callback redirect

            try
            {
                // List Snapchat profiles
                ListSnapchatProfiles200Response result = apiInstance.ListSnapchatProfiles(xConnectToken, profileId, tempToken);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling ConnectApi.ListSnapchatProfiles: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the ListSnapchatProfilesWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // List Snapchat profiles
    ApiResponse<ListSnapchatProfiles200Response> response = apiInstance.ListSnapchatProfilesWithHttpInfo(xConnectToken, profileId, tempToken);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling ConnectApi.ListSnapchatProfilesWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **xConnectToken** | **string** | Short-lived connect token from the OAuth redirect |  |
| **profileId** | **string** | Your Late profile ID |  |
| **tempToken** | **string** | Temporary Snapchat access token from the OAuth callback redirect |  |

### Return type

[**ListSnapchatProfiles200Response**](ListSnapchatProfiles200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | List of Snapchat Public Profiles available for connection |  -  |
| **400** | Missing required parameters (profileId or tempToken) |  -  |
| **401** | Unauthorized |  -  |
| **403** | No access to profile |  -  |
| **500** | Failed to fetch public profiles |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="selectfacebookpage"></a>
# **SelectFacebookPage**
> SelectFacebookPage200Response SelectFacebookPage (SelectFacebookPageRequest selectFacebookPageRequest)

Select Facebook page

Complete the headless flow. After displaying your custom UI with the list of pages from the GET endpoint, call this endpoint to finalize the connection with the user's selected page. The userProfile should be the decoded JSON object from the userProfile query param in the OAuth callback redirect URL. Use the X-Connect-Token header if you initiated the connection via API key. 

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
    public class SelectFacebookPageExample
    {
        public static void Main()
        {
            Configuration config = new Configuration();
            config.BasePath = "https://getlate.dev/api";
            // Configure API key authorization: connectToken
            config.AddApiKey("X-Connect-Token", "YOUR_API_KEY");
            // Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
            // config.AddApiKeyPrefix("X-Connect-Token", "Bearer");
            // Configure Bearer token for authorization: bearerAuth
            config.AccessToken = "YOUR_BEARER_TOKEN";

            // create instances of HttpClient, HttpClientHandler to be reused later with different Api classes
            HttpClient httpClient = new HttpClient();
            HttpClientHandler httpClientHandler = new HttpClientHandler();
            var apiInstance = new ConnectApi(httpClient, config, httpClientHandler);
            var selectFacebookPageRequest = new SelectFacebookPageRequest(); // SelectFacebookPageRequest | 

            try
            {
                // Select Facebook page
                SelectFacebookPage200Response result = apiInstance.SelectFacebookPage(selectFacebookPageRequest);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling ConnectApi.SelectFacebookPage: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the SelectFacebookPageWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Select Facebook page
    ApiResponse<SelectFacebookPage200Response> response = apiInstance.SelectFacebookPageWithHttpInfo(selectFacebookPageRequest);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling ConnectApi.SelectFacebookPageWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **selectFacebookPageRequest** | [**SelectFacebookPageRequest**](SelectFacebookPageRequest.md) |  |  |

### Return type

[**SelectFacebookPage200Response**](SelectFacebookPage200Response.md)

### Authorization

[connectToken](../README.md#connectToken), [bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Facebook Page connected successfully |  -  |
| **400** | Missing required fields (profileId, pageId, or tempToken) |  -  |
| **401** | Unauthorized |  -  |
| **403** | User does not have access to the specified profile |  -  |
| **404** | Selected page not found in available pages |  -  |
| **500** | Failed to save Facebook connection |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="selectgooglebusinesslocation"></a>
# **SelectGoogleBusinessLocation**
> SelectGoogleBusinessLocation200Response SelectGoogleBusinessLocation (SelectGoogleBusinessLocationRequest selectGoogleBusinessLocationRequest)

Select GBP location

Complete the headless flow. After displaying your custom UI with the list of locations from the GET /v1/connect/googlebusiness/locations endpoint, call this endpoint to finalize the connection with the user's selected location. The userProfile should be the decoded JSON object from the userProfile query param in the OAuth callback redirect URL. It contains important token information including the refresh token. Use the X-Connect-Token header if you initiated the connection via API key. 

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
    public class SelectGoogleBusinessLocationExample
    {
        public static void Main()
        {
            Configuration config = new Configuration();
            config.BasePath = "https://getlate.dev/api";
            // Configure API key authorization: connectToken
            config.AddApiKey("X-Connect-Token", "YOUR_API_KEY");
            // Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
            // config.AddApiKeyPrefix("X-Connect-Token", "Bearer");
            // Configure Bearer token for authorization: bearerAuth
            config.AccessToken = "YOUR_BEARER_TOKEN";

            // create instances of HttpClient, HttpClientHandler to be reused later with different Api classes
            HttpClient httpClient = new HttpClient();
            HttpClientHandler httpClientHandler = new HttpClientHandler();
            var apiInstance = new ConnectApi(httpClient, config, httpClientHandler);
            var selectGoogleBusinessLocationRequest = new SelectGoogleBusinessLocationRequest(); // SelectGoogleBusinessLocationRequest | 

            try
            {
                // Select GBP location
                SelectGoogleBusinessLocation200Response result = apiInstance.SelectGoogleBusinessLocation(selectGoogleBusinessLocationRequest);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling ConnectApi.SelectGoogleBusinessLocation: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the SelectGoogleBusinessLocationWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Select GBP location
    ApiResponse<SelectGoogleBusinessLocation200Response> response = apiInstance.SelectGoogleBusinessLocationWithHttpInfo(selectGoogleBusinessLocationRequest);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling ConnectApi.SelectGoogleBusinessLocationWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **selectGoogleBusinessLocationRequest** | [**SelectGoogleBusinessLocationRequest**](SelectGoogleBusinessLocationRequest.md) |  |  |

### Return type

[**SelectGoogleBusinessLocation200Response**](SelectGoogleBusinessLocation200Response.md)

### Authorization

[connectToken](../README.md#connectToken), [bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Google Business location connected successfully |  -  |
| **400** | Missing required fields (profileId, locationId, or tempToken) |  -  |
| **401** | Unauthorized |  -  |
| **403** | User does not have access to the specified profile |  -  |
| **404** | Selected location not found in available locations |  -  |
| **500** | Failed to save Google Business connection |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="selectlinkedinorganization"></a>
# **SelectLinkedInOrganization**
> SelectLinkedInOrganization200Response SelectLinkedInOrganization (SelectLinkedInOrganizationRequest selectLinkedInOrganizationRequest)

Select LinkedIn org

Complete the LinkedIn connection flow. After OAuth, the user is redirected with organizations in the URL params (if they have org admin access). Use this data to build your UI, then call this endpoint to save the selection. Set accountType to \"personal\" for a personal profile (omit selectedOrganization), or \"organization\" to connect as a company page. Use the X-Connect-Token header if you initiated the connection via API key. 

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
    public class SelectLinkedInOrganizationExample
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
            var apiInstance = new ConnectApi(httpClient, config, httpClientHandler);
            var selectLinkedInOrganizationRequest = new SelectLinkedInOrganizationRequest(); // SelectLinkedInOrganizationRequest | 

            try
            {
                // Select LinkedIn org
                SelectLinkedInOrganization200Response result = apiInstance.SelectLinkedInOrganization(selectLinkedInOrganizationRequest);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling ConnectApi.SelectLinkedInOrganization: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the SelectLinkedInOrganizationWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Select LinkedIn org
    ApiResponse<SelectLinkedInOrganization200Response> response = apiInstance.SelectLinkedInOrganizationWithHttpInfo(selectLinkedInOrganizationRequest);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling ConnectApi.SelectLinkedInOrganizationWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **selectLinkedInOrganizationRequest** | [**SelectLinkedInOrganizationRequest**](SelectLinkedInOrganizationRequest.md) |  |  |

### Return type

[**SelectLinkedInOrganization200Response**](SelectLinkedInOrganization200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | LinkedIn account connected |  -  |
| **400** | Missing required fields |  -  |
| **401** | Unauthorized |  -  |
| **500** | Failed to connect LinkedIn account |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="selectpinterestboard"></a>
# **SelectPinterestBoard**
> SelectPinterestBoard200Response SelectPinterestBoard (SelectPinterestBoardRequest selectPinterestBoardRequest)

Select Pinterest board

Complete the Pinterest connection flow. After OAuth, use this endpoint to save the selected board and complete the account connection. Use the X-Connect-Token header if you initiated the connection via API key. 

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
    public class SelectPinterestBoardExample
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
            var apiInstance = new ConnectApi(httpClient, config, httpClientHandler);
            var selectPinterestBoardRequest = new SelectPinterestBoardRequest(); // SelectPinterestBoardRequest | 

            try
            {
                // Select Pinterest board
                SelectPinterestBoard200Response result = apiInstance.SelectPinterestBoard(selectPinterestBoardRequest);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling ConnectApi.SelectPinterestBoard: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the SelectPinterestBoardWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Select Pinterest board
    ApiResponse<SelectPinterestBoard200Response> response = apiInstance.SelectPinterestBoardWithHttpInfo(selectPinterestBoardRequest);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling ConnectApi.SelectPinterestBoardWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **selectPinterestBoardRequest** | [**SelectPinterestBoardRequest**](SelectPinterestBoardRequest.md) |  |  |

### Return type

[**SelectPinterestBoard200Response**](SelectPinterestBoard200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Pinterest Board connected successfully |  -  |
| **400** | Missing required fields |  -  |
| **401** | Unauthorized |  -  |
| **403** | No access to profile or profile limit exceeded |  -  |
| **500** | Failed to save Pinterest connection |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="selectsnapchatprofile"></a>
# **SelectSnapchatProfile**
> SelectSnapchatProfile200Response SelectSnapchatProfile (SelectSnapchatProfileRequest selectSnapchatProfileRequest, string? xConnectToken = null)

Select Snapchat profile

Complete the Snapchat connection flow. Save the selected Public Profile and complete the account connection. Snapchat requires a Public Profile to publish Stories, Saved Stories, and Spotlight content. After Snapchat OAuth with headless=true, you'll be redirected with tempToken, userProfile, publicProfiles, connect_token, platform=snapchat, and step=select_public_profile in the URL. Parse publicProfiles to build your custom selector UI, then call this endpoint with the selected profile. Use the X-Connect-Token header if you initiated the connection via API key. 

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
    public class SelectSnapchatProfileExample
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
            var apiInstance = new ConnectApi(httpClient, config, httpClientHandler);
            var selectSnapchatProfileRequest = new SelectSnapchatProfileRequest(); // SelectSnapchatProfileRequest | 
            var xConnectToken = "xConnectToken_example";  // string? | Short-lived connect token from the OAuth redirect (for API users) (optional) 

            try
            {
                // Select Snapchat profile
                SelectSnapchatProfile200Response result = apiInstance.SelectSnapchatProfile(selectSnapchatProfileRequest, xConnectToken);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling ConnectApi.SelectSnapchatProfile: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the SelectSnapchatProfileWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Select Snapchat profile
    ApiResponse<SelectSnapchatProfile200Response> response = apiInstance.SelectSnapchatProfileWithHttpInfo(selectSnapchatProfileRequest, xConnectToken);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling ConnectApi.SelectSnapchatProfileWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **selectSnapchatProfileRequest** | [**SelectSnapchatProfileRequest**](SelectSnapchatProfileRequest.md) |  |  |
| **xConnectToken** | **string?** | Short-lived connect token from the OAuth redirect (for API users) | [optional]  |

### Return type

[**SelectSnapchatProfile200Response**](SelectSnapchatProfile200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Snapchat Public Profile connected successfully |  -  |
| **400** | Missing required fields |  -  |
| **401** | Unauthorized |  -  |
| **403** | No access to profile or profile limit exceeded |  -  |
| **500** | Failed to connect Snapchat account |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="updatefacebookpage"></a>
# **UpdateFacebookPage**
> UpdateFacebookPage200Response UpdateFacebookPage (string accountId, UpdateFacebookPageRequest updateFacebookPageRequest)

Update Facebook page

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
    public class UpdateFacebookPageExample
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
            var apiInstance = new ConnectApi(httpClient, config, httpClientHandler);
            var accountId = "accountId_example";  // string | 
            var updateFacebookPageRequest = new UpdateFacebookPageRequest(); // UpdateFacebookPageRequest | 

            try
            {
                // Update Facebook page
                UpdateFacebookPage200Response result = apiInstance.UpdateFacebookPage(accountId, updateFacebookPageRequest);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling ConnectApi.UpdateFacebookPage: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the UpdateFacebookPageWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Update Facebook page
    ApiResponse<UpdateFacebookPage200Response> response = apiInstance.UpdateFacebookPageWithHttpInfo(accountId, updateFacebookPageRequest);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling ConnectApi.UpdateFacebookPageWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **accountId** | **string** |  |  |
| **updateFacebookPageRequest** | [**UpdateFacebookPageRequest**](UpdateFacebookPageRequest.md) |  |  |

### Return type

[**UpdateFacebookPage200Response**](UpdateFacebookPage200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Page updated |  -  |
| **400** | Page not in available pages |  -  |
| **401** | Unauthorized |  -  |
| **404** | Account not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="updategmblocation"></a>
# **UpdateGmbLocation**
> UpdateGmbLocation200Response UpdateGmbLocation (string accountId, UpdateGmbLocationRequest updateGmbLocationRequest)

Update GBP location

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
    public class UpdateGmbLocationExample
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
            var apiInstance = new ConnectApi(httpClient, config, httpClientHandler);
            var accountId = "accountId_example";  // string | 
            var updateGmbLocationRequest = new UpdateGmbLocationRequest(); // UpdateGmbLocationRequest | 

            try
            {
                // Update GBP location
                UpdateGmbLocation200Response result = apiInstance.UpdateGmbLocation(accountId, updateGmbLocationRequest);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling ConnectApi.UpdateGmbLocation: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the UpdateGmbLocationWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Update GBP location
    ApiResponse<UpdateGmbLocation200Response> response = apiInstance.UpdateGmbLocationWithHttpInfo(accountId, updateGmbLocationRequest);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling ConnectApi.UpdateGmbLocationWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **accountId** | **string** |  |  |
| **updateGmbLocationRequest** | [**UpdateGmbLocationRequest**](UpdateGmbLocationRequest.md) |  |  |

### Return type

[**UpdateGmbLocation200Response**](UpdateGmbLocation200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Location updated |  -  |
| **400** | Location not in available locations |  -  |
| **401** | Unauthorized |  -  |
| **404** | Account not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="updatelinkedinorganization"></a>
# **UpdateLinkedInOrganization**
> ConnectBlueskyCredentials200Response UpdateLinkedInOrganization (string accountId, UpdateLinkedInOrganizationRequest updateLinkedInOrganizationRequest)

Switch LinkedIn account type

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
    public class UpdateLinkedInOrganizationExample
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
            var apiInstance = new ConnectApi(httpClient, config, httpClientHandler);
            var accountId = "accountId_example";  // string | 
            var updateLinkedInOrganizationRequest = new UpdateLinkedInOrganizationRequest(); // UpdateLinkedInOrganizationRequest | 

            try
            {
                // Switch LinkedIn account type
                ConnectBlueskyCredentials200Response result = apiInstance.UpdateLinkedInOrganization(accountId, updateLinkedInOrganizationRequest);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling ConnectApi.UpdateLinkedInOrganization: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the UpdateLinkedInOrganizationWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Switch LinkedIn account type
    ApiResponse<ConnectBlueskyCredentials200Response> response = apiInstance.UpdateLinkedInOrganizationWithHttpInfo(accountId, updateLinkedInOrganizationRequest);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling ConnectApi.UpdateLinkedInOrganizationWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **accountId** | **string** |  |  |
| **updateLinkedInOrganizationRequest** | [**UpdateLinkedInOrganizationRequest**](UpdateLinkedInOrganizationRequest.md) |  |  |

### Return type

[**ConnectBlueskyCredentials200Response**](ConnectBlueskyCredentials200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Account updated |  -  |
| **400** | Invalid request |  -  |
| **401** | Unauthorized |  -  |
| **404** | Account not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="updatepinterestboards"></a>
# **UpdatePinterestBoards**
> ConnectBlueskyCredentials200Response UpdatePinterestBoards (string accountId, UpdatePinterestBoardsRequest updatePinterestBoardsRequest)

Set default Pinterest board

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
    public class UpdatePinterestBoardsExample
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
            var apiInstance = new ConnectApi(httpClient, config, httpClientHandler);
            var accountId = "accountId_example";  // string | 
            var updatePinterestBoardsRequest = new UpdatePinterestBoardsRequest(); // UpdatePinterestBoardsRequest | 

            try
            {
                // Set default Pinterest board
                ConnectBlueskyCredentials200Response result = apiInstance.UpdatePinterestBoards(accountId, updatePinterestBoardsRequest);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling ConnectApi.UpdatePinterestBoards: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the UpdatePinterestBoardsWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Set default Pinterest board
    ApiResponse<ConnectBlueskyCredentials200Response> response = apiInstance.UpdatePinterestBoardsWithHttpInfo(accountId, updatePinterestBoardsRequest);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling ConnectApi.UpdatePinterestBoardsWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **accountId** | **string** |  |  |
| **updatePinterestBoardsRequest** | [**UpdatePinterestBoardsRequest**](UpdatePinterestBoardsRequest.md) |  |  |

### Return type

[**ConnectBlueskyCredentials200Response**](ConnectBlueskyCredentials200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Default board set |  -  |
| **400** | Invalid request |  -  |
| **401** | Unauthorized |  -  |
| **404** | Account not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="updateredditsubreddits"></a>
# **UpdateRedditSubreddits**
> UpdateRedditSubreddits200Response UpdateRedditSubreddits (string accountId, UpdateRedditSubredditsRequest updateRedditSubredditsRequest)

Set default subreddit

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
    public class UpdateRedditSubredditsExample
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
            var apiInstance = new ConnectApi(httpClient, config, httpClientHandler);
            var accountId = "accountId_example";  // string | 
            var updateRedditSubredditsRequest = new UpdateRedditSubredditsRequest(); // UpdateRedditSubredditsRequest | 

            try
            {
                // Set default subreddit
                UpdateRedditSubreddits200Response result = apiInstance.UpdateRedditSubreddits(accountId, updateRedditSubredditsRequest);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling ConnectApi.UpdateRedditSubreddits: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the UpdateRedditSubredditsWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Set default subreddit
    ApiResponse<UpdateRedditSubreddits200Response> response = apiInstance.UpdateRedditSubredditsWithHttpInfo(accountId, updateRedditSubredditsRequest);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling ConnectApi.UpdateRedditSubredditsWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **accountId** | **string** |  |  |
| **updateRedditSubredditsRequest** | [**UpdateRedditSubredditsRequest**](UpdateRedditSubredditsRequest.md) |  |  |

### Return type

[**UpdateRedditSubreddits200Response**](UpdateRedditSubreddits200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Default subreddit set |  -  |
| **400** | Invalid request |  -  |
| **401** | Unauthorized |  -  |
| **404** | Account not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

