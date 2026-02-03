# Late.Api.ConnectApi

All URIs are relative to *https://getlate.dev/api*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**CompleteTelegramConnect**](ConnectApi.md#completetelegramconnect) | **PATCH** /v1/connect/telegram | Check Telegram connection status |
| [**ConnectBlueskyCredentials**](ConnectApi.md#connectblueskycredentials) | **POST** /v1/connect/bluesky/credentials | Connect Bluesky using app password |
| [**GetConnectUrl**](ConnectApi.md#getconnecturl) | **GET** /v1/connect/{platform} | Start OAuth connection for a platform |
| [**GetFacebookPages**](ConnectApi.md#getfacebookpages) | **GET** /v1/accounts/{accountId}/facebook-page | List available Facebook pages for a connected account |
| [**GetGmbLocations**](ConnectApi.md#getgmblocations) | **GET** /v1/accounts/{accountId}/gmb-locations | List available Google Business Profile locations for a connected account |
| [**GetLinkedInOrganizations**](ConnectApi.md#getlinkedinorganizations) | **GET** /v1/accounts/{accountId}/linkedin-organizations | Get available LinkedIn organizations for a connected account |
| [**GetPendingOAuthData**](ConnectApi.md#getpendingoauthdata) | **GET** /v1/connect/pending-data | Fetch pending OAuth selection data (Headless Mode) |
| [**GetPinterestBoards**](ConnectApi.md#getpinterestboards) | **GET** /v1/accounts/{accountId}/pinterest-boards | List Pinterest boards for a connected account |
| [**GetRedditSubreddits**](ConnectApi.md#getredditsubreddits) | **GET** /v1/accounts/{accountId}/reddit-subreddits | List Reddit subreddits for a connected account |
| [**GetTelegramConnectStatus**](ConnectApi.md#gettelegramconnectstatus) | **GET** /v1/connect/telegram | Generate Telegram access code |
| [**HandleOAuthCallback**](ConnectApi.md#handleoauthcallback) | **POST** /v1/connect/{platform} | Complete OAuth token exchange manually (for server-side flows) |
| [**InitiateTelegramConnect**](ConnectApi.md#initiatetelegramconnect) | **POST** /v1/connect/telegram | Direct Telegram connection (power users) |
| [**ListFacebookPages**](ConnectApi.md#listfacebookpages) | **GET** /v1/connect/facebook/select-page | List Facebook Pages after OAuth (Headless Mode) |
| [**ListGoogleBusinessLocations**](ConnectApi.md#listgooglebusinesslocations) | **GET** /v1/connect/googlebusiness/locations | List Google Business Locations after OAuth (Headless Mode) |
| [**ListLinkedInOrganizations**](ConnectApi.md#listlinkedinorganizations) | **GET** /v1/connect/linkedin/organizations | Fetch full LinkedIn organization details (Headless Mode) |
| [**ListPinterestBoardsForSelection**](ConnectApi.md#listpinterestboardsforselection) | **GET** /v1/connect/pinterest/select-board | List Pinterest Boards after OAuth (Headless Mode) |
| [**ListSnapchatProfiles**](ConnectApi.md#listsnapchatprofiles) | **GET** /v1/connect/snapchat/select-profile | List Snapchat Public Profiles after OAuth (Headless Mode) |
| [**SelectFacebookPage**](ConnectApi.md#selectfacebookpage) | **POST** /v1/connect/facebook/select-page | Select a Facebook Page to complete the connection (Headless Mode) |
| [**SelectGoogleBusinessLocation**](ConnectApi.md#selectgooglebusinesslocation) | **POST** /v1/connect/googlebusiness/select-location | Select a Google Business location to complete the connection (Headless Mode) |
| [**SelectLinkedInOrganization**](ConnectApi.md#selectlinkedinorganization) | **POST** /v1/connect/linkedin/select-organization | Select LinkedIn organization or personal account after OAuth |
| [**SelectPinterestBoard**](ConnectApi.md#selectpinterestboard) | **POST** /v1/connect/pinterest/select-board | Select a Pinterest Board to complete the connection (Headless Mode) |
| [**SelectSnapchatProfile**](ConnectApi.md#selectsnapchatprofile) | **POST** /v1/connect/snapchat/select-profile | Select a Snapchat Public Profile to complete the connection (Headless Mode) |
| [**UpdateFacebookPage**](ConnectApi.md#updatefacebookpage) | **PUT** /v1/accounts/{accountId}/facebook-page | Update selected Facebook page for a connected account |
| [**UpdateGmbLocation**](ConnectApi.md#updategmblocation) | **PUT** /v1/accounts/{accountId}/gmb-locations | Update selected Google Business Profile location for a connected account |
| [**UpdateLinkedInOrganization**](ConnectApi.md#updatelinkedinorganization) | **PUT** /v1/accounts/{accountId}/linkedin-organization | Switch LinkedIn account type (personal/organization) |
| [**UpdatePinterestBoards**](ConnectApi.md#updatepinterestboards) | **PUT** /v1/accounts/{accountId}/pinterest-boards | Set default Pinterest board on the connection |
| [**UpdateRedditSubreddits**](ConnectApi.md#updateredditsubreddits) | **PUT** /v1/accounts/{accountId}/reddit-subreddits | Set default subreddit on the connection |

<a id="completetelegramconnect"></a>
# **CompleteTelegramConnect**
> CompleteTelegramConnect200Response CompleteTelegramConnect (string code)

Check Telegram connection status

Poll this endpoint to check if a Telegram access code has been used to connect a channel/group.  **Recommended polling interval:** 3 seconds  **Status values:** - `pending`: Code is valid, waiting for user to complete connection - `connected`: Connection successful - channel/group is now linked - `expired`: Code has expired, generate a new one 

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
                // Check Telegram connection status
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
    // Check Telegram connection status
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

Connect Bluesky using app password

Connect a Bluesky account using identifier (handle or email) and an app password.  To get your userId for the state parameter, call `GET /v1/users` - the response includes a `currentUserId` field. 

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
                // Connect Bluesky using app password
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
    // Connect Bluesky using app password
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

Start OAuth connection for a platform

Initiate an OAuth connection flow for any supported social media platform.  **Standard Flow (Hosted UI):** For Facebook connections, Late hosts the page selection UI:  1. Call this endpoint with your API key and `redirect_url` (optional) 2. Redirect your user to the returned `authUrl` 3. After OAuth, the user is redirected to Late’s hosted page selector at      `/connect/facebook/select-page?profileId=X&tempToken=Y&userProfile=Z&redirect_url=YOUR_URL&connect_token=CT` 4. After they pick a page, Late saves the connection and finally redirects to your `redirect_url` (if provided)  **Headless/Whitelabel Mode (Facebook, LinkedIn, Pinterest & Google Business Profile):** Build your own fully branded selection UI while Late handles OAuth:  **Facebook:** 1. Call this endpoint with your API key and add `&headless=true`, e.g.      `GET /v1/connect/facebook?profileId=PROFILE_ID&redirect_url=https://yourapp.com/callback&headless=true` 2. Redirect your user to the returned `authUrl` 3. After OAuth, the user is redirected directly to **your** `redirect_url` with:    - `profileId` – your Late profile ID      - `tempToken` – temporary Facebook access token      - `userProfile` – URL‑encoded JSON user profile      - `connect_token` – short‑lived connect token (for API auth)      - `platform=facebook`      - `step=select_page` 4. Use `tempToken`, `userProfile`, and the `X-Connect-Token` header with:    - `GET /v1/connect/facebook/select-page` to fetch pages    - `POST /v1/connect/facebook/select-page` to save the selected page 5. In this mode, users never see Late's hosted page selector – only your UI.  **LinkedIn:** 1. Call this endpoint with `&headless=true`, e.g.    `GET /v1/connect/linkedin?profileId=PROFILE_ID&redirect_url=https://yourapp.com/callback&headless=true` 2. Redirect your user to the returned `authUrl` 3. After OAuth, the user is redirected directly to **your** `redirect_url` with:    - `profileId` – your Late profile ID    - `pendingDataToken` – token to fetch OAuth data via API (see step 4)    - `connect_token` – short-lived connect token (for API auth)    - `platform=linkedin`    - `step=select_organization` 4. Call `GET /v1/connect/pending-data?token=PENDING_DATA_TOKEN` to fetch the OAuth data:    - `tempToken` – temporary LinkedIn access token    - `userProfile` – JSON object with `id`, `username`, `displayName`, `profilePicture`    - `organizations` – JSON array with `id`, `urn`, `name`, `vanityName` for each org    - `refreshToken` / `expiresIn` – token metadata    This endpoint is one-time use and data expires after 10 minutes. 5. **Optional:** To fetch full organization details (logos, website, industry, description), call `GET /v1/connect/linkedin/organizations?tempToken=X&orgIds=id1,id2,...` 6. Call `POST /v1/connect/linkedin/select-organization` with the `X-Connect-Token` header to save the selection. 7. In this mode, users never see Late's hosted organization selector – only your UI. 8. Note: If the user has no organization admin access, `step=select_organization` will NOT be present,    and the account will be connected directly as a personal account.  **Pinterest:** 1. Call this endpoint with `&headless=true`, e.g.    `GET /v1/connect/pinterest?profileId=PROFILE_ID&redirect_url=https://yourapp.com/callback&headless=true` 2. Redirect your user to the returned `authUrl` 3. After OAuth, the user is redirected directly to **your** `redirect_url` with:    - `profileId` – your Late profile ID    - `tempToken` – temporary Pinterest access token    - `userProfile` – URL‑encoded JSON user profile    - `connect_token` – short‑lived connect token (for API auth)    - `platform=pinterest`    - `step=select_board` 4. Use `tempToken`, `userProfile`, and the `X-Connect-Token` header with:    - `GET /v1/connect/pinterest/select-board` to fetch boards    - `POST /v1/connect/pinterest/select-board` to save the selected board 5. In this mode, users never see Late's hosted board selector – only your UI.  **Google Business Profile:** 1. Call this endpoint with `&headless=true`, e.g.    `GET /v1/connect/googlebusiness?profileId=PROFILE_ID&redirect_url=https://yourapp.com/callback&headless=true` 2. Redirect your user to the returned `authUrl` 3. After OAuth, the user is redirected directly to **your** `redirect_url` with:    - `profileId` – your Late profile ID    - `tempToken` – temporary Google access token    - `userProfile` – URL‑encoded JSON user profile (includes refresh token info)    - `connect_token` – short‑lived connect token (for API auth)    - `platform=googlebusiness`    - `step=select_location` 4. Use `tempToken`, `userProfile`, and the `X-Connect-Token` header with:    - `GET /v1/connect/googlebusiness/locations` to fetch business locations    - `POST /v1/connect/googlebusiness/select-location` to save the selected location 5. In this mode, users never see Late's hosted location selector – only your UI. 

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
            var redirectUrl = "redirectUrl_example";  // string? | Optional: Your custom redirect URL after connection completes.  **Standard Mode:** Omit `headless=true` to use our hosted page selection UI.   After the user selects a Facebook Page, Late redirects here with:   `?connected=facebook&profileId=X&username=Y`  **Headless Mode (Facebook, LinkedIn, Pinterest, Google Business Profile & Snapchat):** Pass `headless=true` as a query parameter on this endpoint (not inside `redirect_url`), e.g.: `GET /v1/connect/facebook?profileId=PROFILE_ID&redirect_url=https://yourapp.com/callback&headless=true` `GET /v1/connect/linkedin?profileId=PROFILE_ID&redirect_url=https://yourapp.com/callback&headless=true` `GET /v1/connect/pinterest?profileId=PROFILE_ID&redirect_url=https://yourapp.com/callback&headless=true` `GET /v1/connect/googlebusiness?profileId=PROFILE_ID&redirect_url=https://yourapp.com/callback&headless=true` `GET /v1/connect/snapchat?profileId=PROFILE_ID&redirect_url=https://yourapp.com/callback&headless=true`  After OAuth, the user is redirected directly to your `redirect_url` with OAuth data: - **Facebook:** `?profileId=X&tempToken=Y&userProfile=Z&connect_token=CT&platform=facebook&step=select_page` - **LinkedIn:** `?profileId=X&pendingDataToken=TOKEN&connect_token=CT&platform=linkedin&step=select_organization`   Use `GET /v1/connect/pending-data?token=TOKEN` to fetch tempToken, userProfile, organizations, refreshToken. - **Pinterest:** `?profileId=X&tempToken=Y&userProfile=Z&connect_token=CT&platform=pinterest&step=select_board` - **Google Business:** `?profileId=X&tempToken=Y&userProfile=Z&connect_token=CT&platform=googlebusiness&step=select_location` - **Snapchat:** `?profileId=X&tempToken=Y&userProfile=Z&publicProfiles=PROFILES&connect_token=CT&platform=snapchat&step=select_public_profile`   (publicProfiles contains `id`, `display_name`, `username`, `profile_image_url`, `subscriber_count`)  Then use the respective endpoints to build your custom UI: - Facebook: `/v1/connect/facebook/select-page` (GET to fetch, POST to save) - LinkedIn: `/v1/connect/linkedin/organizations` (GET to fetch logos), `/v1/connect/linkedin/select-organization` (POST to save) - Pinterest: `/v1/connect/pinterest/select-board` (GET to fetch, POST to save) - Google Business: `/v1/connect/googlebusiness/locations` (GET) and `/v1/connect/googlebusiness/select-location` (POST) - Snapchat: `/v1/connect/snapchat/select-profile` (POST to save selected public profile)  Example: `https://yourdomain.com/integrations/callback`  (optional) 

            try
            {
                // Start OAuth connection for a platform
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
    // Start OAuth connection for a platform
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
| **redirectUrl** | **string?** | Optional: Your custom redirect URL after connection completes.  **Standard Mode:** Omit &#x60;headless&#x3D;true&#x60; to use our hosted page selection UI.   After the user selects a Facebook Page, Late redirects here with:   &#x60;?connected&#x3D;facebook&amp;profileId&#x3D;X&amp;username&#x3D;Y&#x60;  **Headless Mode (Facebook, LinkedIn, Pinterest, Google Business Profile &amp; Snapchat):** Pass &#x60;headless&#x3D;true&#x60; as a query parameter on this endpoint (not inside &#x60;redirect_url&#x60;), e.g.: &#x60;GET /v1/connect/facebook?profileId&#x3D;PROFILE_ID&amp;redirect_url&#x3D;https://yourapp.com/callback&amp;headless&#x3D;true&#x60; &#x60;GET /v1/connect/linkedin?profileId&#x3D;PROFILE_ID&amp;redirect_url&#x3D;https://yourapp.com/callback&amp;headless&#x3D;true&#x60; &#x60;GET /v1/connect/pinterest?profileId&#x3D;PROFILE_ID&amp;redirect_url&#x3D;https://yourapp.com/callback&amp;headless&#x3D;true&#x60; &#x60;GET /v1/connect/googlebusiness?profileId&#x3D;PROFILE_ID&amp;redirect_url&#x3D;https://yourapp.com/callback&amp;headless&#x3D;true&#x60; &#x60;GET /v1/connect/snapchat?profileId&#x3D;PROFILE_ID&amp;redirect_url&#x3D;https://yourapp.com/callback&amp;headless&#x3D;true&#x60;  After OAuth, the user is redirected directly to your &#x60;redirect_url&#x60; with OAuth data: - **Facebook:** &#x60;?profileId&#x3D;X&amp;tempToken&#x3D;Y&amp;userProfile&#x3D;Z&amp;connect_token&#x3D;CT&amp;platform&#x3D;facebook&amp;step&#x3D;select_page&#x60; - **LinkedIn:** &#x60;?profileId&#x3D;X&amp;pendingDataToken&#x3D;TOKEN&amp;connect_token&#x3D;CT&amp;platform&#x3D;linkedin&amp;step&#x3D;select_organization&#x60;   Use &#x60;GET /v1/connect/pending-data?token&#x3D;TOKEN&#x60; to fetch tempToken, userProfile, organizations, refreshToken. - **Pinterest:** &#x60;?profileId&#x3D;X&amp;tempToken&#x3D;Y&amp;userProfile&#x3D;Z&amp;connect_token&#x3D;CT&amp;platform&#x3D;pinterest&amp;step&#x3D;select_board&#x60; - **Google Business:** &#x60;?profileId&#x3D;X&amp;tempToken&#x3D;Y&amp;userProfile&#x3D;Z&amp;connect_token&#x3D;CT&amp;platform&#x3D;googlebusiness&amp;step&#x3D;select_location&#x60; - **Snapchat:** &#x60;?profileId&#x3D;X&amp;tempToken&#x3D;Y&amp;userProfile&#x3D;Z&amp;publicProfiles&#x3D;PROFILES&amp;connect_token&#x3D;CT&amp;platform&#x3D;snapchat&amp;step&#x3D;select_public_profile&#x60;   (publicProfiles contains &#x60;id&#x60;, &#x60;display_name&#x60;, &#x60;username&#x60;, &#x60;profile_image_url&#x60;, &#x60;subscriber_count&#x60;)  Then use the respective endpoints to build your custom UI: - Facebook: &#x60;/v1/connect/facebook/select-page&#x60; (GET to fetch, POST to save) - LinkedIn: &#x60;/v1/connect/linkedin/organizations&#x60; (GET to fetch logos), &#x60;/v1/connect/linkedin/select-organization&#x60; (POST to save) - Pinterest: &#x60;/v1/connect/pinterest/select-board&#x60; (GET to fetch, POST to save) - Google Business: &#x60;/v1/connect/googlebusiness/locations&#x60; (GET) and &#x60;/v1/connect/googlebusiness/select-location&#x60; (POST) - Snapchat: &#x60;/v1/connect/snapchat/select-profile&#x60; (POST to save selected public profile)  Example: &#x60;https://yourdomain.com/integrations/callback&#x60;  | [optional]  |

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

List available Facebook pages for a connected account

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
                // List available Facebook pages for a connected account
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
    // List available Facebook pages for a connected account
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

List available Google Business Profile locations for a connected account

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
                // List available Google Business Profile locations for a connected account
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
    // List available Google Business Profile locations for a connected account
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

Get available LinkedIn organizations for a connected account

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
                // Get available LinkedIn organizations for a connected account
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
    // Get available LinkedIn organizations for a connected account
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

Fetch pending OAuth selection data (Headless Mode)

**Fetch Pending OAuth Data for Headless Mode**  In headless mode, platforms like LinkedIn store OAuth selection data (organizations, pages, etc.) in the database instead of passing it via URL parameters. This prevents URI_TOO_LONG errors when users have many organizations/pages to select from.  After OAuth redirect, use the `pendingDataToken` from the URL to fetch the stored data.  **Important:** - This endpoint is one-time use: data is deleted after being fetched - Data expires automatically after 10 minutes if not fetched - No authentication required, just the token from the redirect URL 

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
            var token = "token_example";  // string | The pending data token from the OAuth redirect URL (`pendingDataToken` parameter)

            try
            {
                // Fetch pending OAuth selection data (Headless Mode)
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
    // Fetch pending OAuth selection data (Headless Mode)
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
| **token** | **string** | The pending data token from the OAuth redirect URL (&#x60;pendingDataToken&#x60; parameter) |  |

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

List Pinterest boards for a connected account

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
                // List Pinterest boards for a connected account
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
    // List Pinterest boards for a connected account
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

<a id="getredditsubreddits"></a>
# **GetRedditSubreddits**
> GetRedditSubreddits200Response GetRedditSubreddits (string accountId)

List Reddit subreddits for a connected account

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
                // List Reddit subreddits for a connected account
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
    // List Reddit subreddits for a connected account
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

Generate Telegram access code

Generate a unique access code for connecting a Telegram channel or group.  **Connection Flow:** 1. Call this endpoint to get an access code (valid for 15 minutes) 2. Add the bot (@LateScheduleBot or your configured bot) as an administrator in your Telegram channel/group 3. Open a private chat with the bot 4. Send: `{CODE} @yourchannel` (e.g., `LATE-ABC123 @mychannel`) 5. Poll `PATCH /v1/connect/telegram?code={CODE}` to check connection status  **Alternative for private channels:** If your channel has no public username, forward any message from the channel to the bot along with the access code. 

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
                // Generate Telegram access code
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
    // Generate Telegram access code
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

Complete OAuth token exchange manually (for server-side flows)

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
                // Complete OAuth token exchange manually (for server-side flows)
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
    // Complete OAuth token exchange manually (for server-side flows)
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

Direct Telegram connection (power users)

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
                // Direct Telegram connection (power users)
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
    // Direct Telegram connection (power users)
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

List Facebook Pages after OAuth (Headless Mode)

**Headless Mode for Custom UI**  After initiating Facebook OAuth via `/v1/connect/facebook`, you'll be redirected to  `/connect/facebook/select-page` with query params including `tempToken` and `userProfile`.  For a **headless/whitelabeled flow**, extract these params from the URL and call this  endpoint to retrieve the list of Facebook Pages the user can manage. Then build your  own UI to let users select a page.  **Note:** Use the `X-Connect-Token` header if you initiated the connection via API key  (rather than a browser session). 

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
                // List Facebook Pages after OAuth (Headless Mode)
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
    // List Facebook Pages after OAuth (Headless Mode)
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

List Google Business Locations after OAuth (Headless Mode)

**Headless Mode for Custom UI**  After initiating Google Business OAuth via `/v1/connect/googlebusiness?headless=true`, you'll be redirected  to your `redirect_url` with query params including `tempToken` and `userProfile`.  For a **headless/whitelabeled flow**, extract these params from the URL and call this  endpoint to retrieve the list of Google Business locations the user can manage. Then build your  own UI to let users select a location.  **Note:** Use the `X-Connect-Token` header if you initiated the connection via API key  (rather than a browser session). 

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
                // List Google Business Locations after OAuth (Headless Mode)
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
    // List Google Business Locations after OAuth (Headless Mode)
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

Fetch full LinkedIn organization details (Headless Mode)

**Fetch Full Organization Details for Custom UI**  After LinkedIn OAuth in headless mode, the redirect URL contains organization data with only `id`, `urn`, and `name` fields (additional details are excluded to prevent URL length issues with many organizations).  Use this endpoint to fetch full organization details including logos, vanity names, websites, and more if you want to display them in your custom selection UI.  **Note:** This endpoint requires no authentication - just the `tempToken` from the OAuth redirect. Details are fetched directly from LinkedIn's API in parallel for fast response times. 

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
                // Fetch full LinkedIn organization details (Headless Mode)
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
    // Fetch full LinkedIn organization details (Headless Mode)
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

List Pinterest Boards after OAuth (Headless Mode)

**Retrieve Pinterest Boards for Selection UI**  After initiating Pinterest OAuth via `/v1/connect/pinterest` with `headless=true`, you'll be redirected to your `redirect_url` with query params including `tempToken` and `userProfile`.  If you want to build your own fully-branded board selector (instead of Late's hosted UI), call this endpoint to retrieve the list of Pinterest Boards the user can post to. Then build your UI and call `POST /v1/connect/pinterest/select-board` to save the selection.  **Authentication:** Use `X-Connect-Token` header with the `connect_token` from the redirect URL. 

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
                // List Pinterest Boards after OAuth (Headless Mode)
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
    // List Pinterest Boards after OAuth (Headless Mode)
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

List Snapchat Public Profiles after OAuth (Headless Mode)

**Headless Mode for Custom UI**  After initiating Snapchat OAuth via `/v1/connect/snapchat?headless=true`, you'll be redirected to your `redirect_url` with query params including `tempToken`, `userProfile`, and `publicProfiles`.  If you want to build your own fully-branded profile selector (instead of Late's hosted UI), call this endpoint to retrieve the list of Snapchat Public Profiles the user can post to. Then build your UI and call `POST /v1/connect/snapchat/select-profile` to save the selection.  **Authentication:** Use `X-Connect-Token` header with the `connect_token` from the redirect URL. 

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
                // List Snapchat Public Profiles after OAuth (Headless Mode)
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
    // List Snapchat Public Profiles after OAuth (Headless Mode)
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

Select a Facebook Page to complete the connection (Headless Mode)

**Complete the Headless Flow**  After displaying your custom UI with the list of pages from the GET endpoint, call this  endpoint to finalize the connection with the user's selected page.  The `userProfile` should be the decoded JSON object from the `userProfile` query param  in the OAuth callback redirect URL.  **Note:** Use the `X-Connect-Token` header if you initiated the connection via API key. 

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
                // Select a Facebook Page to complete the connection (Headless Mode)
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
    // Select a Facebook Page to complete the connection (Headless Mode)
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

Select a Google Business location to complete the connection (Headless Mode)

**Complete the Headless Flow**  After displaying your custom UI with the list of locations from the GET `/v1/connect/googlebusiness/locations`  endpoint, call this endpoint to finalize the connection with the user's selected location.  The `userProfile` should be the decoded JSON object from the `userProfile` query param  in the OAuth callback redirect URL. It contains important token information (including refresh token).  **Note:** Use the `X-Connect-Token` header if you initiated the connection via API key. 

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
                // Select a Google Business location to complete the connection (Headless Mode)
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
    // Select a Google Business location to complete the connection (Headless Mode)
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

Select LinkedIn organization or personal account after OAuth

**Complete the LinkedIn Connection Flow**  After OAuth, the user is redirected with `organizations` in the URL params (if they have org admin access). The organizations array contains `id`, `urn`, and `name` fields. Use this data to build your UI,  then call this endpoint to save the selection.  Set `accountType` to `personal` to connect as the user's personal LinkedIn profile, or `organization` to connect as a company page (requires `selectedOrganization` object).  **Personal Profile:** To connect a personal LinkedIn account, set `accountType` to `\"personal\"` and **omit** the `selectedOrganization` field entirely. This is the simplest flow.  **Headless Mode:** Use the `X-Connect-Token` header if you initiated the connection via API key. 

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
                // Select LinkedIn organization or personal account after OAuth
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
    // Select LinkedIn organization or personal account after OAuth
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

Select a Pinterest Board to complete the connection (Headless Mode)

**Complete the Pinterest Connection Flow**  After OAuth, use this endpoint to save the selected board and complete the Pinterest account connection.  **Headless Mode:** Use the `X-Connect-Token` header if you initiated the connection via API key. 

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
                // Select a Pinterest Board to complete the connection (Headless Mode)
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
    // Select a Pinterest Board to complete the connection (Headless Mode)
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

Select a Snapchat Public Profile to complete the connection (Headless Mode)

**Complete the Snapchat Connection Flow**  After OAuth, use this endpoint to save the selected Public Profile and complete the Snapchat account connection. Snapchat requires a Public Profile to publish Stories, Saved Stories, and Spotlight content.  **Headless Mode:** Use the `X-Connect-Token` header if you initiated the connection via API key.  After initiating Snapchat OAuth via `/v1/connect/snapchat?headless=true`, you'll be redirected to your `redirect_url` with query params including: - `tempToken` - Temporary access token - `userProfile` - URL-encoded JSON with user info - `publicProfiles` - URL-encoded JSON array of available public profiles - `connect_token` - Short-lived token for API authentication - `platform=snapchat` - `step=select_public_profile`  Parse `publicProfiles` to build your custom selector UI, then call this endpoint with the selected profile. 

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
                // Select a Snapchat Public Profile to complete the connection (Headless Mode)
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
    // Select a Snapchat Public Profile to complete the connection (Headless Mode)
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

Update selected Facebook page for a connected account

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
                // Update selected Facebook page for a connected account
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
    // Update selected Facebook page for a connected account
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

Update selected Google Business Profile location for a connected account

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
                // Update selected Google Business Profile location for a connected account
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
    // Update selected Google Business Profile location for a connected account
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

Switch LinkedIn account type (personal/organization)

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
                // Switch LinkedIn account type (personal/organization)
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
    // Switch LinkedIn account type (personal/organization)
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

Set default Pinterest board on the connection

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
                // Set default Pinterest board on the connection
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
    // Set default Pinterest board on the connection
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

Set default subreddit on the connection

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
                // Set default subreddit on the connection
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
    // Set default subreddit on the connection
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

