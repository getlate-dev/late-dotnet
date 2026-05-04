# Zernio.Api.ConnectApi

All URIs are relative to *https://zernio.com/api*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**CompleteTelegramConnect**](ConnectApi.md#completetelegramconnect) | **PATCH** /v1/connect/telegram | Check Telegram status |
| [**CompleteWhatsAppPhoneSelection**](ConnectApi.md#completewhatsappphoneselection) | **POST** /v1/connect/whatsapp/select-phone-number | Complete WhatsApp phone number selection |
| [**ConfigureTikTokAdsBrandIdentity**](ConnectApi.md#configuretiktokadsbrandidentity) | **PATCH** /v1/connect/tiktok-ads | Configure TikTok Ads Brand Identity |
| [**ConnectAds**](ConnectApi.md#connectads) | **GET** /v1/connect/{platform}/ads | Connect ads for a platform |
| [**ConnectBlueskyCredentials**](ConnectApi.md#connectblueskycredentials) | **POST** /v1/connect/bluesky/credentials | Connect Bluesky account |
| [**ConnectWhatsAppCredentials**](ConnectApi.md#connectwhatsappcredentials) | **POST** /v1/connect/whatsapp/credentials | Connect WhatsApp via credentials |
| [**GetConnectUrl**](ConnectApi.md#getconnecturl) | **GET** /v1/connect/{platform} | Get OAuth connect URL |
| [**GetFacebookPages**](ConnectApi.md#getfacebookpages) | **GET** /v1/accounts/{accountId}/facebook-page | List Facebook pages |
| [**GetGmbLocations**](ConnectApi.md#getgmblocations) | **GET** /v1/accounts/{accountId}/gmb-locations | List GBP locations |
| [**GetLinkedInOrganizations**](ConnectApi.md#getlinkedinorganizations) | **GET** /v1/accounts/{accountId}/linkedin-organizations | List LinkedIn orgs |
| [**GetPendingOAuthData**](ConnectApi.md#getpendingoauthdata) | **GET** /v1/connect/pending-data | Get pending OAuth data |
| [**GetPinterestBoards**](ConnectApi.md#getpinterestboards) | **GET** /v1/accounts/{accountId}/pinterest-boards | List Pinterest boards |
| [**GetRedditFlairs**](ConnectApi.md#getredditflairs) | **GET** /v1/accounts/{accountId}/reddit-flairs | List subreddit flairs |
| [**GetRedditSubreddits**](ConnectApi.md#getredditsubreddits) | **GET** /v1/accounts/{accountId}/reddit-subreddits | List Reddit subreddits |
| [**GetTelegramConnectStatus**](ConnectApi.md#gettelegramconnectstatus) | **GET** /v1/connect/telegram | Generate Telegram code |
| [**GetYoutubePlaylists**](ConnectApi.md#getyoutubeplaylists) | **GET** /v1/accounts/{accountId}/youtube-playlists | List YouTube playlists |
| [**HandleOAuthCallback**](ConnectApi.md#handleoauthcallback) | **POST** /v1/connect/{platform} | Complete OAuth callback |
| [**InitiateTelegramConnect**](ConnectApi.md#initiatetelegramconnect) | **POST** /v1/connect/telegram | Connect Telegram directly |
| [**ListFacebookPages**](ConnectApi.md#listfacebookpages) | **GET** /v1/connect/facebook/select-page | List Facebook pages |
| [**ListGoogleBusinessLocations**](ConnectApi.md#listgooglebusinesslocations) | **GET** /v1/connect/googlebusiness/locations | List GBP locations |
| [**ListLinkedInOrganizations**](ConnectApi.md#listlinkedinorganizations) | **GET** /v1/connect/linkedin/organizations | List LinkedIn orgs |
| [**ListPinterestBoardsForSelection**](ConnectApi.md#listpinterestboardsforselection) | **GET** /v1/connect/pinterest/select-board | List Pinterest boards |
| [**ListSnapchatProfiles**](ConnectApi.md#listsnapchatprofiles) | **GET** /v1/connect/snapchat/select-profile | List Snapchat profiles |
| [**ListWhatsAppPhoneNumbers**](ConnectApi.md#listwhatsappphonenumbers) | **GET** /v1/connect/whatsapp/select-phone-number | List WhatsApp phone numbers for selection |
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
| [**UpdateYoutubeDefaultPlaylist**](ConnectApi.md#updateyoutubedefaultplaylist) | **PUT** /v1/accounts/{accountId}/youtube-playlists | Set default YouTube playlist |

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
using Zernio.Api;
using Zernio.Client;
using Zernio.Model;

namespace Example
{
    public class CompleteTelegramConnectExample
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
            var apiInstance = new ConnectApi(httpClient, config, httpClientHandler);
            var code = ZRN-ABC123;  // string | The access code to check status for

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

<a id="completewhatsappphoneselection"></a>
# **CompleteWhatsAppPhoneSelection**
> CompleteWhatsAppPhoneSelection200Response CompleteWhatsAppPhoneSelection (CompleteWhatsAppPhoneSelectionRequest completeWhatsAppPhoneSelectionRequest, string? xConnectToken = null)

Complete WhatsApp phone number selection

Bind a specific WhatsApp phone number to the Zernio profile after the user picks one from `listWhatsAppPhoneNumbers`. Exchanges the short-lived OAuth token for a long-lived token, subscribes the WABA to webhooks, and creates the SocialAccount. 

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
    public class CompleteWhatsAppPhoneSelectionExample
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
            var apiInstance = new ConnectApi(httpClient, config, httpClientHandler);
            var completeWhatsAppPhoneSelectionRequest = new CompleteWhatsAppPhoneSelectionRequest(); // CompleteWhatsAppPhoneSelectionRequest | 
            var xConnectToken = "xConnectToken_example";  // string? | Alternative auth for API users' end customers (optional) 

            try
            {
                // Complete WhatsApp phone number selection
                CompleteWhatsAppPhoneSelection200Response result = apiInstance.CompleteWhatsAppPhoneSelection(completeWhatsAppPhoneSelectionRequest, xConnectToken);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling ConnectApi.CompleteWhatsAppPhoneSelection: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the CompleteWhatsAppPhoneSelectionWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Complete WhatsApp phone number selection
    ApiResponse<CompleteWhatsAppPhoneSelection200Response> response = apiInstance.CompleteWhatsAppPhoneSelectionWithHttpInfo(completeWhatsAppPhoneSelectionRequest, xConnectToken);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling ConnectApi.CompleteWhatsAppPhoneSelectionWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **completeWhatsAppPhoneSelectionRequest** | [**CompleteWhatsAppPhoneSelectionRequest**](CompleteWhatsAppPhoneSelectionRequest.md) |  |  |
| **xConnectToken** | **string?** | Alternative auth for API users&#39; end customers | [optional]  |

### Return type

[**CompleteWhatsAppPhoneSelection200Response**](CompleteWhatsAppPhoneSelection200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Phone number connected successfully |  -  |
| **400** | Missing required fields (profileId, phoneNumberId, wabaId, or tempToken) |  -  |
| **401** | Unauthorized |  -  |
| **403** | Profile limit exceeded for the user&#39;s plan (PROFILE_LIMIT_EXCEEDED) |  -  |
| **404** | Selected phone number not found in the specified WABA |  -  |
| **500** | Failed to bind phone number |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="configuretiktokadsbrandidentity"></a>
# **ConfigureTikTokAdsBrandIdentity**
> ConfigureTikTokAdsBrandIdentity200Response ConfigureTikTokAdsBrandIdentity (ConfigureTikTokAdsBrandIdentityRequest configureTikTokAdsBrandIdentityRequest)

Configure TikTok Ads Brand Identity

Set or update the Brand Identity (display name + avatar) for a `tiktokads` SocialAccount. TikTok requires every ad to carry an `identity_id + identity_type` pair. The Brand Identity is the CUSTOMIZED_USER alternative to attributing ads to a real @username (TT_USER). This route uploads the supplied image to TikTok, creates the identity via `/v2/identity/create/`, and caches the resulting `identity_id` on the account so subsequent `POST /v1/ads/create` calls can opt into it via `identityType: 'CUSTOMIZED_USER'`.  Configurable on every `tiktokads` account, including linked-mode ones (those with a posting account on the same profile). Configuration is idempotent and harmless when posting is also connected: the default ad-create path still prefers TT_USER, and CUSTOMIZED_USER is only used per-ad when the caller explicitly opts in.  TikTok identities are immutable post-creation. Re-saving creates a new identity on TikTok and swaps the cached id; the old identity stays orphaned on TikTok's side (harmless, no billing impact).  Alternative: pass `brandIdentity` directly on `POST /v1/ads/create` to configure on first ad creation in a single round-trip. 

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
    public class ConfigureTikTokAdsBrandIdentityExample
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
            var apiInstance = new ConnectApi(httpClient, config, httpClientHandler);
            var configureTikTokAdsBrandIdentityRequest = new ConfigureTikTokAdsBrandIdentityRequest(); // ConfigureTikTokAdsBrandIdentityRequest | 

            try
            {
                // Configure TikTok Ads Brand Identity
                ConfigureTikTokAdsBrandIdentity200Response result = apiInstance.ConfigureTikTokAdsBrandIdentity(configureTikTokAdsBrandIdentityRequest);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling ConnectApi.ConfigureTikTokAdsBrandIdentity: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the ConfigureTikTokAdsBrandIdentityWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Configure TikTok Ads Brand Identity
    ApiResponse<ConfigureTikTokAdsBrandIdentity200Response> response = apiInstance.ConfigureTikTokAdsBrandIdentityWithHttpInfo(configureTikTokAdsBrandIdentityRequest);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling ConnectApi.ConfigureTikTokAdsBrandIdentityWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **configureTikTokAdsBrandIdentityRequest** | [**ConfigureTikTokAdsBrandIdentityRequest**](ConfigureTikTokAdsBrandIdentityRequest.md) |  |  |

### Return type

[**ConfigureTikTokAdsBrandIdentity200Response**](ConfigureTikTokAdsBrandIdentity200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Brand identity configured (or updated) |  -  |
| **400** | Missing fields, invalid lengths, account is in linked mode, or no advertiser found on the account |  -  |
| **401** | Unauthorized |  -  |
| **404** | TikTok Ads account not found |  -  |
| **500** | Failed to create the TikTok identity (TikTok API error) |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="connectads"></a>
# **ConnectAds**
> ConnectAds200Response ConnectAds (string platform, string profileId, string? accountId = null, string? redirectUrl = null, bool? headless = null, string? adAccountId = null, List<string>? adAccountIds = null)

Connect ads for a platform

Unified ads connection endpoint. Creates a dedicated ads SocialAccount for the specified platform.  Same-token platforms (facebook, instagram, linkedin, pinterest): Creates an ads SocialAccount (metaads, linkedinads, pinterestads) with a copied OAuth token from the parent posting account. If the ads account already exists, returns alreadyConnected: true. No extra OAuth needed.  Separate-token platforms (tiktok, twitter): Starts the platform-specific marketing API OAuth flow and creates an ads SocialAccount (tiktokads, xads) with its own token. If the ads account already exists, returns alreadyConnected: true.   - tiktok: accountId is OPTIONAL. With accountId, the new tiktokads account links to that posting account (parentAccountId set) — Spark Ads + standalone ads using the posting TT_USER identity become available. Without accountId, ads-only mode kicks in: the new tiktokads account has parentAccountId=null and standalone ads use a synthetic CUSTOMIZED_USER (\"Brand Identity\"); Spark Ads are unavailable because TikTok requires a posting account for them. The Brand Identity is configured separately via PATCH /v1/connect/tiktok-ads (or inline on POST /v1/ads/create via the brandIdentity field).   - twitter (X Ads): accountId is REQUIRED. There's no ads-only mode — tweets need to be authored by a real X user.  Standalone platforms (googleads): Starts the Google Ads OAuth flow and creates a standalone ads SocialAccount (googleads) with no parent. If the account already exists, returns alreadyConnected: true.  Ads accounts appear as regular SocialAccount documents with ads platform values (e.g., metaads, tiktokads) in GET /v1/accounts. 

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
    public class ConnectAdsExample
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
            var apiInstance = new ConnectApi(httpClient, config, httpClientHandler);
            var platform = "facebook";  // string | Platform to connect ads for. Only platforms with ads support are accepted.
            var profileId = "profileId_example";  // string | Your Zernio profile ID
            var accountId = "accountId_example";  // string? | Existing SocialAccount ID. Required for `twitter` (X Ads). Optional for `tiktok` — omit to enter ads-only mode (no TikTok posting account linked; ad creation uses a Brand Identity instead of a TT_USER). Ignored for same-token (`facebook`, `instagram`, `linkedin`, `pinterest`) and standalone (`googleads`) platforms.  (optional) 
            var redirectUrl = "redirectUrl_example";  // string? | Custom redirect URL after OAuth completes (same-token platforms only) (optional) 
            var headless = false;  // bool? | Enable headless mode (same-token platforms only) (optional)  (default to false)
            var adAccountId = act_1330190928038136;  // string? | (metaads only) Scope ad sync to a single Meta ad account. Without this param, sync covers every `act_*` the connected token can see. Pass this to limit `sync.totalAds` / `synced` and the resulting ads to one ad account. Format: `act_<digits>` (matches what `/me/adaccounts` returns). Validated against the connected token; unreachable IDs return 400. For multiple accounts use `adAccountIds` instead.  (optional) 
            var adAccountIds = new List<string>?(); // List<string>? | (metaads only) Scope ad sync to multiple Meta ad accounts. Repeat the param (`?adAccountIds=act_1&adAccountIds=act_2`) or comma-separate (`?adAccountIds=act_1,act_2`). Validated against the connected token. Persisted server-side; latest call wins. Omitting both `adAccountId` and `adAccountIds` keeps any previously persisted scope unchanged.  (optional) 

            try
            {
                // Connect ads for a platform
                ConnectAds200Response result = apiInstance.ConnectAds(platform, profileId, accountId, redirectUrl, headless, adAccountId, adAccountIds);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling ConnectApi.ConnectAds: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the ConnectAdsWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Connect ads for a platform
    ApiResponse<ConnectAds200Response> response = apiInstance.ConnectAdsWithHttpInfo(platform, profileId, accountId, redirectUrl, headless, adAccountId, adAccountIds);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling ConnectApi.ConnectAdsWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **platform** | **string** | Platform to connect ads for. Only platforms with ads support are accepted. |  |
| **profileId** | **string** | Your Zernio profile ID |  |
| **accountId** | **string?** | Existing SocialAccount ID. Required for &#x60;twitter&#x60; (X Ads). Optional for &#x60;tiktok&#x60; — omit to enter ads-only mode (no TikTok posting account linked; ad creation uses a Brand Identity instead of a TT_USER). Ignored for same-token (&#x60;facebook&#x60;, &#x60;instagram&#x60;, &#x60;linkedin&#x60;, &#x60;pinterest&#x60;) and standalone (&#x60;googleads&#x60;) platforms.  | [optional]  |
| **redirectUrl** | **string?** | Custom redirect URL after OAuth completes (same-token platforms only) | [optional]  |
| **headless** | **bool?** | Enable headless mode (same-token platforms only) | [optional] [default to false] |
| **adAccountId** | **string?** | (metaads only) Scope ad sync to a single Meta ad account. Without this param, sync covers every &#x60;act_*&#x60; the connected token can see. Pass this to limit &#x60;sync.totalAds&#x60; / &#x60;synced&#x60; and the resulting ads to one ad account. Format: &#x60;act_&lt;digits&gt;&#x60; (matches what &#x60;/me/adaccounts&#x60; returns). Validated against the connected token; unreachable IDs return 400. For multiple accounts use &#x60;adAccountIds&#x60; instead.  | [optional]  |
| **adAccountIds** | [**List&lt;string&gt;?**](string.md) | (metaads only) Scope ad sync to multiple Meta ad accounts. Repeat the param (&#x60;?adAccountIds&#x3D;act_1&amp;adAccountIds&#x3D;act_2&#x60;) or comma-separate (&#x60;?adAccountIds&#x3D;act_1,act_2&#x60;). Validated against the connected token. Persisted server-side; latest call wins. Omitting both &#x60;adAccountId&#x60; and &#x60;adAccountIds&#x60; keeps any previously persisted scope unchanged.  | [optional]  |

### Return type

[**ConnectAds200Response**](ConnectAds200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Either an OAuth URL to redirect to, or confirmation that ads are already connected |  -  |
| **400** | Platform doesn&#39;t support ads, or missing accountId for X Ads |  -  |
| **401** | Unauthorized |  -  |
| **403** | Ads add-on required, or no access to profile |  -  |
| **404** | Profile or posting account not found |  -  |

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
using Zernio.Api;
using Zernio.Client;
using Zernio.Model;

namespace Example
{
    public class ConnectBlueskyCredentialsExample
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

<a id="connectwhatsappcredentials"></a>
# **ConnectWhatsAppCredentials**
> ConnectWhatsAppCredentials200Response ConnectWhatsAppCredentials (ConnectWhatsAppCredentialsRequest connectWhatsAppCredentialsRequest)

Connect WhatsApp via credentials

Connect a WhatsApp Business Account by providing Meta credentials directly. This is the headless alternative to the Embedded Signup browser flow.  To get the required credentials: 1. Go to Meta Business Suite (business.facebook.com) 2. Create or select a WhatsApp Business Account 3. In Business Settings > System Users, create a System User 4. Assign it the whatsapp_business_management and whatsapp_business_messaging permissions 5. Generate a permanent access token 6. Get the WABA ID from WhatsApp Manager > Account Tools > Phone Numbers 7. Get the Phone Number ID from the same page (click on the number) 

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
    public class ConnectWhatsAppCredentialsExample
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
            var apiInstance = new ConnectApi(httpClient, config, httpClientHandler);
            var connectWhatsAppCredentialsRequest = new ConnectWhatsAppCredentialsRequest(); // ConnectWhatsAppCredentialsRequest | 

            try
            {
                // Connect WhatsApp via credentials
                ConnectWhatsAppCredentials200Response result = apiInstance.ConnectWhatsAppCredentials(connectWhatsAppCredentialsRequest);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling ConnectApi.ConnectWhatsAppCredentials: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the ConnectWhatsAppCredentialsWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Connect WhatsApp via credentials
    ApiResponse<ConnectWhatsAppCredentials200Response> response = apiInstance.ConnectWhatsAppCredentialsWithHttpInfo(connectWhatsAppCredentialsRequest);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling ConnectApi.ConnectWhatsAppCredentialsWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **connectWhatsAppCredentialsRequest** | [**ConnectWhatsAppCredentialsRequest**](ConnectWhatsAppCredentialsRequest.md) |  |  |

### Return type

[**ConnectWhatsAppCredentials200Response**](ConnectWhatsAppCredentials200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | WhatsApp connected successfully |  -  |
| **400** | Invalid request. Either missing fields or the phoneNumberId was not found in the specified WABA. If the phone was not found, the response includes availablePhoneNumbers to help identify the correct ID.  |  -  |
| **401** | Invalid or expired access token |  -  |
| **403** | Profile limit exceeded for this plan |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="getconnecturl"></a>
# **GetConnectUrl**
> GetConnectUrl200Response GetConnectUrl (string platform, string profileId, string? redirectUrl = null, bool? headless = null)

Get OAuth connect URL

Initiate an OAuth connection flow. Returns an authUrl to redirect the user to. Standard flow: Zernio hosts the selection UI, then redirects to your redirect_url. Headless mode (headless=true): user is redirected to your redirect_url with OAuth data for custom UI. Use the platform-specific selection endpoints to complete. 

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
    public class GetConnectUrlExample
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
            var apiInstance = new ConnectApi(httpClient, config, httpClientHandler);
            var platform = "facebook";  // string | Social media platform to connect
            var profileId = "profileId_example";  // string | Your Zernio profile ID (get from /v1/profiles)
            var redirectUrl = "redirectUrl_example";  // string? | Your custom redirect URL after connection completes. Standard mode appends ?connected={platform}&profileId=X&accountId=Y&username=Z. Headless mode appends OAuth data params for platforms requiring selection (e.g. LinkedIn orgs, Facebook pages). If no selection is needed, the account is created directly and the redirect includes accountId. (optional) 
            var headless = false;  // bool? | When true, the user is redirected to your redirect_url with raw OAuth data (code, state) instead of Zernio's default account selection UI. Use this to build a custom connect experience. (optional)  (default to false)

            try
            {
                // Get OAuth connect URL
                GetConnectUrl200Response result = apiInstance.GetConnectUrl(platform, profileId, redirectUrl, headless);
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
    ApiResponse<GetConnectUrl200Response> response = apiInstance.GetConnectUrlWithHttpInfo(platform, profileId, redirectUrl, headless);
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
| **profileId** | **string** | Your Zernio profile ID (get from /v1/profiles) |  |
| **redirectUrl** | **string?** | Your custom redirect URL after connection completes. Standard mode appends ?connected&#x3D;{platform}&amp;profileId&#x3D;X&amp;accountId&#x3D;Y&amp;username&#x3D;Z. Headless mode appends OAuth data params for platforms requiring selection (e.g. LinkedIn orgs, Facebook pages). If no selection is needed, the account is created directly and the redirect includes accountId. | [optional]  |
| **headless** | **bool?** | When true, the user is redirected to your redirect_url with raw OAuth data (code, state) instead of Zernio&#39;s default account selection UI. Use this to build a custom connect experience. | [optional] [default to false] |

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
| **402** | Payment method or enterprise contract required. The authenticated account hit a billing gate before the connection could proceed. Three reasons:    - &#x60;free_tier_exceeded&#x60;: the team has connected more accounts     than the free tier allows. Add a payment method on the     dashboard to continue (the user will be billed per     additional connected account).    - &#x60;twitter_passthrough&#x60;: connecting an X (Twitter) account     requires a card on file from day one because X API calls     incur real per-call pass-through costs. Applies to the 1st     X account, not just the 3rd+.    - &#x60;enterprise_required&#x60;: the team has reached the public     pricing ceiling (2,000 connected accounts). Beyond that     requires a custom enterprise contract negotiated directly.     &#x60;dashboard_url&#x60; deep-links to the enterprise contact page     rather than the billing tab. The end-user already has a     card on file; this gate is about contract terms, not card     collection.  SDK consumers should switch on &#x60;reason&#x60; to render the right prompt. For &#x60;free_tier_exceeded&#x60; and &#x60;twitter_passthrough&#x60;, redirect the end-user to &#x60;dashboard_url&#x60; to add a payment method via Zernio&#39;s hosted Stripe Setup Checkout. For &#x60;enterprise_required&#x60;, redirect to &#x60;dashboard_url&#x60; (the enterprise contact form) so they can talk to sales.  |  -  |
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
using Zernio.Api;
using Zernio.Client;
using Zernio.Model;

namespace Example
{
    public class GetFacebookPagesExample
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
using Zernio.Api;
using Zernio.Client;
using Zernio.Model;

namespace Example
{
    public class GetGmbLocationsExample
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

Returns LinkedIn organizations (company pages) the connected account has admin access to.

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
    public class GetLinkedInOrganizationsExample
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

Fetch pending OAuth data for headless mode using the pendingDataToken from the redirect URL.  **Scope**: This endpoint is used only for LinkedIn organizations and Snapchat profiles, where the selection list is too large to fit in URL params. WhatsApp, Facebook, Pinterest, Google Business and other platforms pass selection state directly via URL query params on the redirect (`profileId`, `tempToken`, `step`), no pending record is created, so this endpoint will return 404 for those flows. Use the platform-specific selection endpoint instead (e.g. `/v1/connect/whatsapp/select-phone-number`).  Token is one-time use and expires after 10 minutes. No authentication required. 

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
    public class GetPendingOAuthDataExample
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

Returns the boards available for a connected Pinterest account. Use this to get a board ID when creating a Pinterest post.

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
    public class GetPinterestBoardsExample
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

Returns available post flairs for a subreddit. Some subreddits require a flair when posting.

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
    public class GetRedditFlairsExample
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

Returns the subreddits the connected Reddit account can post to. Use this to get a subreddit name when creating a Reddit post.

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
    public class GetRedditSubredditsExample
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

Generate an access code (valid 15 minutes) for connecting a Telegram channel or group. Add the bot as admin, then send the code + @yourchannel to the bot. Poll PATCH /v1/connect/telegram to check status.

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
    public class GetTelegramConnectStatusExample
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

<a id="getyoutubeplaylists"></a>
# **GetYoutubePlaylists**
> GetYoutubePlaylists200Response GetYoutubePlaylists (string accountId)

List YouTube playlists

Returns the playlists available for a connected YouTube account. Use this to get a playlist ID when creating a YouTube post with the playlistId field.

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
    public class GetYoutubePlaylistsExample
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
            var apiInstance = new ConnectApi(httpClient, config, httpClientHandler);
            var accountId = "accountId_example";  // string | 

            try
            {
                // List YouTube playlists
                GetYoutubePlaylists200Response result = apiInstance.GetYoutubePlaylists(accountId);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling ConnectApi.GetYoutubePlaylists: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the GetYoutubePlaylistsWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // List YouTube playlists
    ApiResponse<GetYoutubePlaylists200Response> response = apiInstance.GetYoutubePlaylistsWithHttpInfo(accountId);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling ConnectApi.GetYoutubePlaylistsWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **accountId** | **string** |  |  |

### Return type

[**GetYoutubePlaylists200Response**](GetYoutubePlaylists200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Playlists list |  -  |
| **400** | Not a YouTube account |  -  |
| **401** | Unauthorized |  -  |
| **404** | Account not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="handleoauthcallback"></a>
# **HandleOAuthCallback**
> void HandleOAuthCallback (string platform, HandleOAuthCallbackRequest handleOAuthCallbackRequest)

Complete OAuth callback

Exchange the OAuth authorization code for tokens and connect the account to the specified profile.

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
    public class HandleOAuthCallbackExample
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

Connect a Telegram channel/group directly using the chat ID. Alternative to the access code flow. The bot must already be an admin in the channel/group.

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
    public class InitiateTelegramConnectExample
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
using Zernio.Api;
using Zernio.Client;
using Zernio.Model;

namespace Example
{
    public class ListFacebookPagesExample
    {
        public static void Main()
        {
            Configuration config = new Configuration();
            config.BasePath = "https://zernio.com/api";
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
> ListGoogleBusinessLocations200Response ListGoogleBusinessLocations (string? profileId = null, string? pendingDataToken = null, string? tempToken = null)

List GBP locations

For headless flows. Returns the list of GBP locations the user can manage. Use pendingDataToken (from the OAuth callback redirect) to list locations without consuming the token, so it remains available for select-location. Use X-Connect-Token header if connecting via API key. 

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
    public class ListGoogleBusinessLocationsExample
    {
        public static void Main()
        {
            Configuration config = new Configuration();
            config.BasePath = "https://zernio.com/api";
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
            var profileId = "profileId_example";  // string? | Profile ID from your connection flow. Required for auth validation when provided. (optional) 
            var pendingDataToken = "pendingDataToken_example";  // string? | Token from the OAuth callback redirect. Preferred over tempToken because it preserves server-side token storage. One of pendingDataToken or tempToken is required. (optional) 
            var tempToken = "tempToken_example";  // string? | Legacy. Direct Google access token. Use pendingDataToken instead when available. (optional) 

            try
            {
                // List GBP locations
                ListGoogleBusinessLocations200Response result = apiInstance.ListGoogleBusinessLocations(profileId, pendingDataToken, tempToken);
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
    ApiResponse<ListGoogleBusinessLocations200Response> response = apiInstance.ListGoogleBusinessLocationsWithHttpInfo(profileId, pendingDataToken, tempToken);
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
| **profileId** | **string?** | Profile ID from your connection flow. Required for auth validation when provided. | [optional]  |
| **pendingDataToken** | **string?** | Token from the OAuth callback redirect. Preferred over tempToken because it preserves server-side token storage. One of pendingDataToken or tempToken is required. | [optional]  |
| **tempToken** | **string?** | Legacy. Direct Google access token. Use pendingDataToken instead when available. | [optional]  |

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

Fetch full LinkedIn organization details (logos, vanity names, websites) for custom UI. No authentication required, just the tempToken from OAuth.

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
    public class ListLinkedInOrganizationsExample
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

For headless flows. Returns Pinterest boards the user can post to. Use X-Connect-Token from the redirect URL.

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
    public class ListPinterestBoardsForSelectionExample
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
            var apiInstance = new ConnectApi(httpClient, config, httpClientHandler);
            var xConnectToken = "xConnectToken_example";  // string | Short-lived connect token from the OAuth redirect
            var profileId = "profileId_example";  // string | Your Zernio profile ID
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
| **profileId** | **string** | Your Zernio profile ID |  |
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

For headless flows. Returns Snapchat Public Profiles the user can post to. Use X-Connect-Token from the redirect URL.

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
    public class ListSnapchatProfilesExample
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
            var apiInstance = new ConnectApi(httpClient, config, httpClientHandler);
            var xConnectToken = "xConnectToken_example";  // string | Short-lived connect token from the OAuth redirect
            var profileId = "profileId_example";  // string | Your Zernio profile ID
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
| **profileId** | **string** | Your Zernio profile ID |  |
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

<a id="listwhatsappphonenumbers"></a>
# **ListWhatsAppPhoneNumbers**
> ListWhatsAppPhoneNumbers200Response ListWhatsAppPhoneNumbers (string profileId, string tempToken, string? xConnectToken = null)

List WhatsApp phone numbers for selection

Fetch the WhatsApp phone numbers available across the user's WhatsApp Business Accounts (WABAs) after a headless OAuth flow.  WhatsApp OAuth grants access at the WABA level. When a connected WABA has 2 or more phone numbers, you must call this endpoint to list them and then `POST /v1/connect/whatsapp/select-phone-number` to bind one to the Zernio profile. Single-phone WABAs auto-complete during the OAuth callback and never reach this endpoint.  Use the `profileId` and `tempToken` returned in the headless redirect (`step=select_phone_number`).  Alternative: if you already know `wabaId` and `phoneNumberId` (e.g. from Meta Business Suite), use `connectWhatsAppCredentials` instead, which skips this two-step flow. 

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
    public class ListWhatsAppPhoneNumbersExample
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
            var apiInstance = new ConnectApi(httpClient, config, httpClientHandler);
            var profileId = "profileId_example";  // string | The Zernio profile ID from the headless redirect
            var tempToken = "tempToken_example";  // string | The temporary access token from the headless redirect
            var xConnectToken = "xConnectToken_example";  // string? | Alternative auth for API users' end customers (used when the bearer token is scoped to a different user) (optional) 

            try
            {
                // List WhatsApp phone numbers for selection
                ListWhatsAppPhoneNumbers200Response result = apiInstance.ListWhatsAppPhoneNumbers(profileId, tempToken, xConnectToken);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling ConnectApi.ListWhatsAppPhoneNumbers: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the ListWhatsAppPhoneNumbersWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // List WhatsApp phone numbers for selection
    ApiResponse<ListWhatsAppPhoneNumbers200Response> response = apiInstance.ListWhatsAppPhoneNumbersWithHttpInfo(profileId, tempToken, xConnectToken);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling ConnectApi.ListWhatsAppPhoneNumbersWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **profileId** | **string** | The Zernio profile ID from the headless redirect |  |
| **tempToken** | **string** | The temporary access token from the headless redirect |  |
| **xConnectToken** | **string?** | Alternative auth for API users&#39; end customers (used when the bearer token is scoped to a different user) | [optional]  |

### Return type

[**ListWhatsAppPhoneNumbers200Response**](ListWhatsAppPhoneNumbers200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Phone numbers fetched successfully |  -  |
| **400** | Missing profileId or tempToken |  -  |
| **401** | Unauthorized |  -  |
| **500** | Failed to fetch phone numbers (Meta API error, expired token, or insufficient permissions) |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="selectfacebookpage"></a>
# **SelectFacebookPage**
> SelectFacebookPage200Response SelectFacebookPage (SelectFacebookPageRequest selectFacebookPageRequest)

Select Facebook page

Complete the headless flow by saving the user's selected Facebook page. Pass the userProfile from the OAuth redirect and use X-Connect-Token if connecting via API key.

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
    public class SelectFacebookPageExample
    {
        public static void Main()
        {
            Configuration config = new Configuration();
            config.BasePath = "https://zernio.com/api";
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
| **400** | Missing required fields (profileId, pageId, tempToken, or userProfile) |  -  |
| **401** | Unauthorized |  -  |
| **403** | User does not have access to the specified profile |  -  |
| **404** | Selected page not found in available pages |  -  |
| **500** | Failed to save Facebook connection |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="selectgooglebusinesslocation"></a>
# **SelectGoogleBusinessLocation**
> SelectGoogleBusinessLocation200Response SelectGoogleBusinessLocation (SelectGoogleBusinessLocationRequest selectGoogleBusinessLocationRequest)

Select GBP location

Complete the headless GBP flow by saving the user's selected location. The pendingDataToken is returned in your redirect URL after OAuth completes (step=select_location). Tokens and profile data are stored server-side, so only the pendingDataToken is needed here. Use X-Connect-Token header if connecting via API key. 

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
    public class SelectGoogleBusinessLocationExample
    {
        public static void Main()
        {
            Configuration config = new Configuration();
            config.BasePath = "https://zernio.com/api";
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

Complete the LinkedIn connection flow. Set accountType to \"personal\" or \"organization\" to connect as a company page. Use X-Connect-Token if connecting via API key.

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
    public class SelectLinkedInOrganizationExample
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
using Zernio.Api;
using Zernio.Client;
using Zernio.Model;

namespace Example
{
    public class SelectPinterestBoardExample
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

Complete the Snapchat connection flow by saving the selected Public Profile. Snapchat requires a Public Profile to publish content. Use X-Connect-Token if connecting via API key.

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
    public class SelectSnapchatProfileExample
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

Switch which Facebook Page is active for a connected account.

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
    public class UpdateFacebookPageExample
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

Switch which GBP location is active for a connected account.

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
    public class UpdateGmbLocationExample
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

Switch a LinkedIn account between personal profile and organization (company page) posting.

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
    public class UpdateLinkedInOrganizationExample
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

Sets the default board used when publishing pins for this account.

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
    public class UpdatePinterestBoardsExample
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
> UpdateYoutubeDefaultPlaylist200Response UpdateRedditSubreddits (string accountId, UpdateRedditSubredditsRequest updateRedditSubredditsRequest)

Set default subreddit

Sets the default subreddit used when publishing posts for this Reddit account.

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
    public class UpdateRedditSubredditsExample
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
            var apiInstance = new ConnectApi(httpClient, config, httpClientHandler);
            var accountId = "accountId_example";  // string | 
            var updateRedditSubredditsRequest = new UpdateRedditSubredditsRequest(); // UpdateRedditSubredditsRequest | 

            try
            {
                // Set default subreddit
                UpdateYoutubeDefaultPlaylist200Response result = apiInstance.UpdateRedditSubreddits(accountId, updateRedditSubredditsRequest);
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
    ApiResponse<UpdateYoutubeDefaultPlaylist200Response> response = apiInstance.UpdateRedditSubredditsWithHttpInfo(accountId, updateRedditSubredditsRequest);
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

[**UpdateYoutubeDefaultPlaylist200Response**](UpdateYoutubeDefaultPlaylist200Response.md)

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

<a id="updateyoutubedefaultplaylist"></a>
# **UpdateYoutubeDefaultPlaylist**
> UpdateYoutubeDefaultPlaylist200Response UpdateYoutubeDefaultPlaylist (string accountId, UpdateYoutubeDefaultPlaylistRequest updateYoutubeDefaultPlaylistRequest)

Set default YouTube playlist

Sets the default playlist used when publishing videos for this account. When a post does not specify a playlistId, the default playlist is not automatically used (it is stored for client-side convenience).

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
    public class UpdateYoutubeDefaultPlaylistExample
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
            var apiInstance = new ConnectApi(httpClient, config, httpClientHandler);
            var accountId = "accountId_example";  // string | 
            var updateYoutubeDefaultPlaylistRequest = new UpdateYoutubeDefaultPlaylistRequest(); // UpdateYoutubeDefaultPlaylistRequest | 

            try
            {
                // Set default YouTube playlist
                UpdateYoutubeDefaultPlaylist200Response result = apiInstance.UpdateYoutubeDefaultPlaylist(accountId, updateYoutubeDefaultPlaylistRequest);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling ConnectApi.UpdateYoutubeDefaultPlaylist: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the UpdateYoutubeDefaultPlaylistWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Set default YouTube playlist
    ApiResponse<UpdateYoutubeDefaultPlaylist200Response> response = apiInstance.UpdateYoutubeDefaultPlaylistWithHttpInfo(accountId, updateYoutubeDefaultPlaylistRequest);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling ConnectApi.UpdateYoutubeDefaultPlaylistWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **accountId** | **string** |  |  |
| **updateYoutubeDefaultPlaylistRequest** | [**UpdateYoutubeDefaultPlaylistRequest**](UpdateYoutubeDefaultPlaylistRequest.md) |  |  |

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
| **200** | Default playlist set |  -  |
| **400** | Invalid request |  -  |
| **401** | Unauthorized |  -  |
| **404** | Account not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

