# Late.Api.AdCampaignsApi

All URIs are relative to *https://zernio.com/api*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**GetAdTree**](AdCampaignsApi.md#getadtree) | **GET** /v1/ads/tree | Get campaign tree |
| [**ListAdCampaigns**](AdCampaignsApi.md#listadcampaigns) | **GET** /v1/ads/campaigns | List campaigns |
| [**UpdateAdCampaignStatus**](AdCampaignsApi.md#updateadcampaignstatus) | **PUT** /v1/ads/campaigns/{campaignId}/status | Pause or resume a campaign |

<a id="getadtree"></a>
# **GetAdTree**
> GetAdTree200Response GetAdTree (int? page = null, int? limit = null, string? source = null, string? platform = null, string? status = null, string? adAccountId = null, string? accountId = null, string? profileId = null, DateOnly? fromDate = null, DateOnly? toDate = null)

Get campaign tree

Returns a nested Campaign > Ad Set > Ad hierarchy with rolled-up metrics at each level. Uses a two-stage aggregation: ads are grouped into ad sets, then ad sets into campaigns. Metrics are computed over an optional date range, then rolled up from ad level to ad set and campaign levels. Pagination is at the campaign level. Ads without a campaign or ad set ID are grouped into synthetic \"Ungrouped\" buckets. If no date range is provided, defaults to the last 90 days. Date range is capped at 90 days max. 

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
    public class GetAdTreeExample
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
            var apiInstance = new AdCampaignsApi(httpClient, config, httpClientHandler);
            var page = 1;  // int? | Page number (1-based) (optional)  (default to 1)
            var limit = 20;  // int? | Campaigns per page (optional)  (default to 20)
            var source = "zernio";  // string? |  (optional)  (default to zernio)
            var platform = "facebook";  // string? |  (optional) 
            var status = "active";  // string? | Filter by derived campaign status (post-aggregation) (optional) 
            var adAccountId = "adAccountId_example";  // string? | Platform ad account ID (optional) 
            var accountId = "accountId_example";  // string? | Social account ID (optional) 
            var profileId = "profileId_example";  // string? | Profile ID (optional) 
            var fromDate = DateOnly.Parse("2013-10-20");  // DateOnly? | Start of metrics date range (YYYY-MM-DD). Defaults to 90 days ago. (optional) 
            var toDate = DateOnly.Parse("2013-10-20");  // DateOnly? | End of metrics date range (YYYY-MM-DD). Defaults to today. Max 90-day range. (optional) 

            try
            {
                // Get campaign tree
                GetAdTree200Response result = apiInstance.GetAdTree(page, limit, source, platform, status, adAccountId, accountId, profileId, fromDate, toDate);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling AdCampaignsApi.GetAdTree: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the GetAdTreeWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Get campaign tree
    ApiResponse<GetAdTree200Response> response = apiInstance.GetAdTreeWithHttpInfo(page, limit, source, platform, status, adAccountId, accountId, profileId, fromDate, toDate);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling AdCampaignsApi.GetAdTreeWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **page** | **int?** | Page number (1-based) | [optional] [default to 1] |
| **limit** | **int?** | Campaigns per page | [optional] [default to 20] |
| **source** | **string?** |  | [optional] [default to zernio] |
| **platform** | **string?** |  | [optional]  |
| **status** | **string?** | Filter by derived campaign status (post-aggregation) | [optional]  |
| **adAccountId** | **string?** | Platform ad account ID | [optional]  |
| **accountId** | **string?** | Social account ID | [optional]  |
| **profileId** | **string?** | Profile ID | [optional]  |
| **fromDate** | **DateOnly?** | Start of metrics date range (YYYY-MM-DD). Defaults to 90 days ago. | [optional]  |
| **toDate** | **DateOnly?** | End of metrics date range (YYYY-MM-DD). Defaults to today. Max 90-day range. | [optional]  |

### Return type

[**GetAdTree200Response**](GetAdTree200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Nested campaign tree with pagination |  -  |
| **401** | Unauthorized |  -  |
| **403** | Ads add-on required |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="listadcampaigns"></a>
# **ListAdCampaigns**
> ListAdCampaigns200Response ListAdCampaigns (int? page = null, int? limit = null, string? source = null, string? platform = null, string? status = null, string? adAccountId = null, string? accountId = null, string? profileId = null)

List campaigns

Returns campaigns as virtual aggregations over ad documents grouped by platform campaign ID. Metrics (spend, impressions, clicks, etc.) are summed across all ads in each campaign. Campaign status is derived from child ad statuses (active > pending_review > paused > error > completed > cancelled > rejected). 

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
    public class ListAdCampaignsExample
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
            var apiInstance = new AdCampaignsApi(httpClient, config, httpClientHandler);
            var page = 1;  // int? | Page number (1-based) (optional)  (default to 1)
            var limit = 20;  // int? |  (optional)  (default to 20)
            var source = "zernio";  // string? |  (optional)  (default to zernio)
            var platform = "facebook";  // string? |  (optional) 
            var status = "active";  // string? | Filter by derived campaign status (post-aggregation) (optional) 
            var adAccountId = "adAccountId_example";  // string? | Platform ad account ID (e.g. act_123 for Meta) (optional) 
            var accountId = "accountId_example";  // string? | Social account ID (optional) 
            var profileId = "profileId_example";  // string? | Profile ID (optional) 

            try
            {
                // List campaigns
                ListAdCampaigns200Response result = apiInstance.ListAdCampaigns(page, limit, source, platform, status, adAccountId, accountId, profileId);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling AdCampaignsApi.ListAdCampaigns: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the ListAdCampaignsWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // List campaigns
    ApiResponse<ListAdCampaigns200Response> response = apiInstance.ListAdCampaignsWithHttpInfo(page, limit, source, platform, status, adAccountId, accountId, profileId);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling AdCampaignsApi.ListAdCampaignsWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **page** | **int?** | Page number (1-based) | [optional] [default to 1] |
| **limit** | **int?** |  | [optional] [default to 20] |
| **source** | **string?** |  | [optional] [default to zernio] |
| **platform** | **string?** |  | [optional]  |
| **status** | **string?** | Filter by derived campaign status (post-aggregation) | [optional]  |
| **adAccountId** | **string?** | Platform ad account ID (e.g. act_123 for Meta) | [optional]  |
| **accountId** | **string?** | Social account ID | [optional]  |
| **profileId** | **string?** | Profile ID | [optional]  |

### Return type

[**ListAdCampaigns200Response**](ListAdCampaigns200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Paginated campaigns |  -  |
| **401** | Unauthorized |  -  |
| **403** | Ads add-on required |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="updateadcampaignstatus"></a>
# **UpdateAdCampaignStatus**
> UpdateAdCampaignStatus200Response UpdateAdCampaignStatus (string campaignId, UpdateAdCampaignStatusRequest updateAdCampaignStatusRequest)

Pause or resume a campaign

Updates the status of all ads in a campaign. Makes one platform API call (not per-ad) since status cascades through the campaign hierarchy. Ads in terminal statuses (rejected, completed, cancelled) are automatically skipped. 

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
    public class UpdateAdCampaignStatusExample
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
            var apiInstance = new AdCampaignsApi(httpClient, config, httpClientHandler);
            var campaignId = "campaignId_example";  // string | Platform campaign ID
            var updateAdCampaignStatusRequest = new UpdateAdCampaignStatusRequest(); // UpdateAdCampaignStatusRequest | 

            try
            {
                // Pause or resume a campaign
                UpdateAdCampaignStatus200Response result = apiInstance.UpdateAdCampaignStatus(campaignId, updateAdCampaignStatusRequest);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling AdCampaignsApi.UpdateAdCampaignStatus: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the UpdateAdCampaignStatusWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Pause or resume a campaign
    ApiResponse<UpdateAdCampaignStatus200Response> response = apiInstance.UpdateAdCampaignStatusWithHttpInfo(campaignId, updateAdCampaignStatusRequest);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling AdCampaignsApi.UpdateAdCampaignStatusWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **campaignId** | **string** | Platform campaign ID |  |
| **updateAdCampaignStatusRequest** | [**UpdateAdCampaignStatusRequest**](UpdateAdCampaignStatusRequest.md) |  |  |

### Return type

[**UpdateAdCampaignStatus200Response**](UpdateAdCampaignStatus200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Campaign status updated |  -  |
| **400** | Invalid input or campaign spans multiple social accounts |  -  |
| **401** | Unauthorized |  -  |
| **404** | No ads found for this campaign |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

