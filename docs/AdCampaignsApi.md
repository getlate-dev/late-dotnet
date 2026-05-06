# Zernio.Api.AdCampaignsApi

All URIs are relative to *https://zernio.com/api*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**BulkUpdateAdCampaignStatus**](AdCampaignsApi.md#bulkupdateadcampaignstatus) | **POST** /v1/ads/campaigns/bulk-status | Pause or resume many campaigns |
| [**DeleteAdCampaign**](AdCampaignsApi.md#deleteadcampaign) | **DELETE** /v1/ads/campaigns/{campaignId} | Delete a campaign |
| [**DuplicateAdCampaign**](AdCampaignsApi.md#duplicateadcampaign) | **POST** /v1/ads/campaigns/{campaignId}/duplicate | Duplicate a campaign |
| [**GetAdTree**](AdCampaignsApi.md#getadtree) | **GET** /v1/ads/tree | Get campaign tree |
| [**ListAdCampaigns**](AdCampaignsApi.md#listadcampaigns) | **GET** /v1/ads/campaigns | List campaigns |
| [**UpdateAdCampaign**](AdCampaignsApi.md#updateadcampaign) | **PUT** /v1/ads/campaigns/{campaignId} | Update a campaign (budget and/or bid strategy) |
| [**UpdateAdCampaignStatus**](AdCampaignsApi.md#updateadcampaignstatus) | **PUT** /v1/ads/campaigns/{campaignId}/status | Pause or resume a campaign |
| [**UpdateAdSet**](AdCampaignsApi.md#updateadset) | **PUT** /v1/ads/ad-sets/{adSetId} | Update an ad set (budget, status, and/or bid strategy) |
| [**UpdateAdSetStatus**](AdCampaignsApi.md#updateadsetstatus) | **PUT** /v1/ads/ad-sets/{adSetId}/status | Pause or resume a single ad set |

<a id="bulkupdateadcampaignstatus"></a>
# **BulkUpdateAdCampaignStatus**
> BulkUpdateAdCampaignStatus200Response BulkUpdateAdCampaignStatus (BulkUpdateAdCampaignStatusRequest bulkUpdateAdCampaignStatusRequest)

Pause or resume many campaigns

Process up to 50 campaigns in one call. Each campaign is updated concurrently and the response contains a per-campaign result so a single bad row does not fail the whole batch. 

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
    public class BulkUpdateAdCampaignStatusExample
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
            var bulkUpdateAdCampaignStatusRequest = new BulkUpdateAdCampaignStatusRequest(); // BulkUpdateAdCampaignStatusRequest | 

            try
            {
                // Pause or resume many campaigns
                BulkUpdateAdCampaignStatus200Response result = apiInstance.BulkUpdateAdCampaignStatus(bulkUpdateAdCampaignStatusRequest);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling AdCampaignsApi.BulkUpdateAdCampaignStatus: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the BulkUpdateAdCampaignStatusWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Pause or resume many campaigns
    ApiResponse<BulkUpdateAdCampaignStatus200Response> response = apiInstance.BulkUpdateAdCampaignStatusWithHttpInfo(bulkUpdateAdCampaignStatusRequest);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling AdCampaignsApi.BulkUpdateAdCampaignStatusWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **bulkUpdateAdCampaignStatusRequest** | [**BulkUpdateAdCampaignStatusRequest**](BulkUpdateAdCampaignStatusRequest.md) |  |  |

### Return type

[**BulkUpdateAdCampaignStatus200Response**](BulkUpdateAdCampaignStatus200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Per-campaign results |  -  |
| **400** | Invalid input |  -  |
| **401** | Unauthorized |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="deleteadcampaign"></a>
# **DeleteAdCampaign**
> DeleteAdCampaign200Response DeleteAdCampaign (string campaignId, DeleteAdCampaignRequest deleteAdCampaignRequest)

Delete a campaign

Deletes the whole campaign on the platform, cascading to its ad sets and ads. Locally, all Ad documents for this campaign are marked `status: cancelled`.  Meta-only for now. Other platforms return 501 Not Implemented — fall back to DELETE /v1/ads/{adId} per ad in the meantime. 

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
    public class DeleteAdCampaignExample
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
            var deleteAdCampaignRequest = new DeleteAdCampaignRequest(); // DeleteAdCampaignRequest | 

            try
            {
                // Delete a campaign
                DeleteAdCampaign200Response result = apiInstance.DeleteAdCampaign(campaignId, deleteAdCampaignRequest);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling AdCampaignsApi.DeleteAdCampaign: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the DeleteAdCampaignWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Delete a campaign
    ApiResponse<DeleteAdCampaign200Response> response = apiInstance.DeleteAdCampaignWithHttpInfo(campaignId, deleteAdCampaignRequest);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling AdCampaignsApi.DeleteAdCampaignWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **campaignId** | **string** | Platform campaign ID |  |
| **deleteAdCampaignRequest** | [**DeleteAdCampaignRequest**](DeleteAdCampaignRequest.md) |  |  |

### Return type

[**DeleteAdCampaign200Response**](DeleteAdCampaign200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Campaign deleted |  -  |
| **401** | Unauthorized |  -  |
| **404** | Campaign not found |  -  |
| **501** | Operation not supported on this platform |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="duplicateadcampaign"></a>
# **DuplicateAdCampaign**
> DuplicateAdCampaign200Response DuplicateAdCampaign (string campaignId, DuplicateAdCampaignRequest duplicateAdCampaignRequest)

Duplicate a campaign

Duplicates a campaign, including its ad sets, ads, creatives, and targeting by default (`deepCopy: true`). The copy is created paused so callers can review before launching.  Per-platform implementation: - **Meta** uses the native `POST /{campaign-id}/copies` endpoint. - **TikTok** has no native copy primitive; Zernio walks the source   graph (`/v2/campaign/get/`, `/v2/adgroup/get/`, `/v2/ad/get/`) and   recreates each entity via the corresponding `/create/` endpoints,   carrying over budget / targeting / bid_type / bid_price /   deep_bid_type / creative fields. Spark Ad linkage (`tiktok_item_id`)   is preserved.  The new hierarchy is asynchronous to materialize in our DB — we trigger sync discovery automatically. Set `syncAfter: false` to skip and poll `/v1/ads/tree` on your own cadence.  Other platforms return 501 Not Implemented. 

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
    public class DuplicateAdCampaignExample
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
            var campaignId = "campaignId_example";  // string | Source platform campaign ID
            var duplicateAdCampaignRequest = new DuplicateAdCampaignRequest(); // DuplicateAdCampaignRequest | 

            try
            {
                // Duplicate a campaign
                DuplicateAdCampaign200Response result = apiInstance.DuplicateAdCampaign(campaignId, duplicateAdCampaignRequest);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling AdCampaignsApi.DuplicateAdCampaign: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the DuplicateAdCampaignWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Duplicate a campaign
    ApiResponse<DuplicateAdCampaign200Response> response = apiInstance.DuplicateAdCampaignWithHttpInfo(campaignId, duplicateAdCampaignRequest);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling AdCampaignsApi.DuplicateAdCampaignWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **campaignId** | **string** | Source platform campaign ID |  |
| **duplicateAdCampaignRequest** | [**DuplicateAdCampaignRequest**](DuplicateAdCampaignRequest.md) |  |  |

### Return type

[**DuplicateAdCampaign200Response**](DuplicateAdCampaign200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Campaign duplicated |  -  |
| **400** | Invalid input |  -  |
| **401** | Unauthorized |  -  |
| **404** | Source campaign not found |  -  |
| **501** | Operation not supported on this platform |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="getadtree"></a>
# **GetAdTree**
> GetAdTree200Response GetAdTree (int? page = null, int? limit = null, string? source = null, string? platform = null, AdStatus? status = null, string? adAccountId = null, string? accountId = null, string? profileId = null, DateOnly? fromDate = null, DateOnly? toDate = null)

Get campaign tree

Returns a nested Campaign > Ad Set > Ad hierarchy with rolled-up metrics at each level. Uses a two-stage aggregation: ads are grouped into ad sets, then ad sets into campaigns. Metrics are computed over an optional date range, then rolled up from ad level to ad set and campaign levels. Pagination is at the campaign level. Ads without a campaign or ad set ID are grouped into synthetic \"Ungrouped\" buckets. If no date range is provided, defaults to the last 90 days. Date range is capped at 730 days max. Ranges older than 90 days trigger a one-time on-demand fetch from the platform when scoped to a specific accountId, then serve from cache on subsequent requests. 

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
            var source = "zernio";  // string? | `all` (default) returns both Zernio-created ads and those discovered from the platform's ad manager — matches the web UI's default view. Pass `zernio` to restrict to isExternal=false only. Status is NOT filtered by default — use the `status` param for that. (optional)  (default to all)
            var platform = "facebook";  // string? |  (optional) 
            var status = new AdStatus?(); // AdStatus? | Filter by derived campaign status (post-aggregation) (optional) 
            var adAccountId = "adAccountId_example";  // string? | Platform ad account ID (optional) 
            var accountId = "accountId_example";  // string? | Social account ID (optional) 
            var profileId = "profileId_example";  // string? | Profile ID (optional) 
            var fromDate = DateOnly.Parse("2013-10-20");  // DateOnly? | Start of metrics date range (YYYY-MM-DD). Defaults to 90 days ago. Ranges older than 90 days trigger an on-demand platform fetch when scoped to a specific accountId. (optional) 
            var toDate = DateOnly.Parse("2013-10-20");  // DateOnly? | End of metrics date range (YYYY-MM-DD). Defaults to today. Max 730-day range. (optional) 

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
| **source** | **string?** | &#x60;all&#x60; (default) returns both Zernio-created ads and those discovered from the platform&#39;s ad manager — matches the web UI&#39;s default view. Pass &#x60;zernio&#x60; to restrict to isExternal&#x3D;false only. Status is NOT filtered by default — use the &#x60;status&#x60; param for that. | [optional] [default to all] |
| **platform** | **string?** |  | [optional]  |
| **status** | [**AdStatus?**](AdStatus?.md) | Filter by derived campaign status (post-aggregation) | [optional]  |
| **adAccountId** | **string?** | Platform ad account ID | [optional]  |
| **accountId** | **string?** | Social account ID | [optional]  |
| **profileId** | **string?** | Profile ID | [optional]  |
| **fromDate** | **DateOnly?** | Start of metrics date range (YYYY-MM-DD). Defaults to 90 days ago. Ranges older than 90 days trigger an on-demand platform fetch when scoped to a specific accountId. | [optional]  |
| **toDate** | **DateOnly?** | End of metrics date range (YYYY-MM-DD). Defaults to today. Max 730-day range. | [optional]  |

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
> ListAdCampaigns200Response ListAdCampaigns (int? page = null, int? limit = null, string? source = null, string? platform = null, AdStatus? status = null, string? adAccountId = null, string? accountId = null, string? profileId = null)

List campaigns

Returns campaigns as virtual aggregations over ad documents grouped by platform campaign ID. Metrics (spend, impressions, clicks, etc.) are summed across all ads in each campaign. Campaign status is derived from child ad statuses (active > pending_review > paused > error > completed > cancelled > rejected). 

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
            var source = "zernio";  // string? | `all` (default) returns both Zernio-created ads and those discovered from the platform's ad manager — matches the web UI's default view. Pass `zernio` to restrict to isExternal=false only. Status is NOT filtered by default — use the `status` param for that. (optional)  (default to all)
            var platform = "facebook";  // string? |  (optional) 
            var status = new AdStatus?(); // AdStatus? | Filter by derived campaign status (post-aggregation) (optional) 
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
| **source** | **string?** | &#x60;all&#x60; (default) returns both Zernio-created ads and those discovered from the platform&#39;s ad manager — matches the web UI&#39;s default view. Pass &#x60;zernio&#x60; to restrict to isExternal&#x3D;false only. Status is NOT filtered by default — use the &#x60;status&#x60; param for that. | [optional] [default to all] |
| **platform** | **string?** |  | [optional]  |
| **status** | [**AdStatus?**](AdStatus?.md) | Filter by derived campaign status (post-aggregation) | [optional]  |
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

<a id="updateadcampaign"></a>
# **UpdateAdCampaign**
> UpdateAdCampaign200Response UpdateAdCampaign (string campaignId, UpdateAdCampaignRequest updateAdCampaignRequest)

Update a campaign (budget and/or bid strategy)

Campaign-level edits. At least one of `budget` or `bidStrategy` is required.  - `budget` updates the CBO (Campaign Budget Optimization) budget. For ABO campaigns   (where the budget lives on the ad set), use PUT /v1/ads/ad-sets/{adSetId} instead — this endpoint   will return 409 with code BUDGET_LEVEL_MISMATCH. - `bidStrategy` sets the campaign-level default bid strategy. Per Meta's spec, `bid_amount` and   `bid_constraints` do NOT exist at the campaign level — pass them via PUT /v1/ads/ad-sets/{adSetId}.  Meta-only for now. Other platforms return 501 Not Implemented. 

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
    public class UpdateAdCampaignExample
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
            var updateAdCampaignRequest = new UpdateAdCampaignRequest(); // UpdateAdCampaignRequest | 

            try
            {
                // Update a campaign (budget and/or bid strategy)
                UpdateAdCampaign200Response result = apiInstance.UpdateAdCampaign(campaignId, updateAdCampaignRequest);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling AdCampaignsApi.UpdateAdCampaign: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the UpdateAdCampaignWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Update a campaign (budget and/or bid strategy)
    ApiResponse<UpdateAdCampaign200Response> response = apiInstance.UpdateAdCampaignWithHttpInfo(campaignId, updateAdCampaignRequest);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling AdCampaignsApi.UpdateAdCampaignWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **campaignId** | **string** | Platform campaign ID |  |
| **updateAdCampaignRequest** | [**UpdateAdCampaignRequest**](UpdateAdCampaignRequest.md) |  |  |

### Return type

[**UpdateAdCampaign200Response**](UpdateAdCampaign200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Campaign updated |  -  |
| **400** | Invalid input |  -  |
| **401** | Unauthorized |  -  |
| **404** | Campaign not found |  -  |
| **409** | Campaign is ABO — route to /v1/ads/ad-sets/{adSetId} instead |  -  |
| **501** | Operation not supported on this platform |  -  |

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
using Zernio.Api;
using Zernio.Client;
using Zernio.Model;

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

<a id="updateadset"></a>
# **UpdateAdSet**
> UpdateAdSet200Response UpdateAdSet (string adSetId, UpdateAdSetRequest updateAdSetRequest)

Update an ad set (budget, status, and/or bid strategy)

Ad-set-level writes. Use this for ABO budget updates, ad-set-scoped pause/resume, and bid-strategy edits. At least one of `budget`, `status`, or `bidStrategy` is required.  Bid strategy compatibility (per Meta's spec): - `LOWEST_COST_WITHOUT_CAP`: no `bidAmount`, no `roasAverageFloor`. - `LOWEST_COST_WITH_BID_CAP` / `COST_CAP`: `bidAmount` REQUIRED (whole currency units). - `LOWEST_COST_WITH_MIN_ROAS`: `roasAverageFloor` REQUIRED (decimal multiplier, e.g. 2.0 = 2.0x ROAS).  When updating `budget` on an ABO campaign: if the parent campaign is CBO, the response is 409 with code BUDGET_LEVEL_MISMATCH — route to PUT /v1/ads/campaigns/{campaignId} instead. 

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
    public class UpdateAdSetExample
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
            var adSetId = "adSetId_example";  // string | Platform ad set ID
            var updateAdSetRequest = new UpdateAdSetRequest(); // UpdateAdSetRequest | 

            try
            {
                // Update an ad set (budget, status, and/or bid strategy)
                UpdateAdSet200Response result = apiInstance.UpdateAdSet(adSetId, updateAdSetRequest);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling AdCampaignsApi.UpdateAdSet: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the UpdateAdSetWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Update an ad set (budget, status, and/or bid strategy)
    ApiResponse<UpdateAdSet200Response> response = apiInstance.UpdateAdSetWithHttpInfo(adSetId, updateAdSetRequest);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling AdCampaignsApi.UpdateAdSetWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **adSetId** | **string** | Platform ad set ID |  |
| **updateAdSetRequest** | [**UpdateAdSetRequest**](UpdateAdSetRequest.md) |  |  |

### Return type

[**UpdateAdSet200Response**](UpdateAdSet200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Ad set updated |  -  |
| **400** | Invalid input |  -  |
| **401** | Unauthorized |  -  |
| **404** | Ad set not found |  -  |
| **409** | Campaign is CBO — route to /v1/ads/campaigns/{campaignId} instead |  -  |
| **501** | bidStrategy not supported on the platform (Meta + TikTok only) |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="updateadsetstatus"></a>
# **UpdateAdSetStatus**
> UpdateAdSetStatus200Response UpdateAdSetStatus (string adSetId, UpdateAdCampaignStatusRequest updateAdCampaignStatusRequest)

Pause or resume a single ad set

Ad-set-scoped pause/resume (doesn't touch sibling ad sets). Thin wrapper over PUT /v1/ads/ad-sets/{adSetId} for callers that only want the status toggle and prefer a symmetric URL to /v1/ads/campaigns/{campaignId}/status. 

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
    public class UpdateAdSetStatusExample
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
            var adSetId = "adSetId_example";  // string | Platform ad set ID
            var updateAdCampaignStatusRequest = new UpdateAdCampaignStatusRequest(); // UpdateAdCampaignStatusRequest | 

            try
            {
                // Pause or resume a single ad set
                UpdateAdSetStatus200Response result = apiInstance.UpdateAdSetStatus(adSetId, updateAdCampaignStatusRequest);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling AdCampaignsApi.UpdateAdSetStatus: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the UpdateAdSetStatusWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Pause or resume a single ad set
    ApiResponse<UpdateAdSetStatus200Response> response = apiInstance.UpdateAdSetStatusWithHttpInfo(adSetId, updateAdCampaignStatusRequest);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling AdCampaignsApi.UpdateAdSetStatusWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **adSetId** | **string** | Platform ad set ID |  |
| **updateAdCampaignStatusRequest** | [**UpdateAdCampaignStatusRequest**](UpdateAdCampaignStatusRequest.md) |  |  |

### Return type

[**UpdateAdSetStatus200Response**](UpdateAdSetStatus200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Ad set status updated |  -  |
| **400** | Invalid input |  -  |
| **401** | Unauthorized |  -  |
| **404** | Ad set not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

