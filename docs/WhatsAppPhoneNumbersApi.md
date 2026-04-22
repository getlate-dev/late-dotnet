# Zernio.Api.WhatsAppPhoneNumbersApi

All URIs are relative to *https://zernio.com/api*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**GetWhatsAppPhoneNumber**](WhatsAppPhoneNumbersApi.md#getwhatsappphonenumber) | **GET** /v1/whatsapp/phone-numbers/{phoneNumberId} | Get phone number |
| [**GetWhatsAppPhoneNumbers**](WhatsAppPhoneNumbersApi.md#getwhatsappphonenumbers) | **GET** /v1/whatsapp/phone-numbers | List phone numbers |
| [**PurchaseWhatsAppPhoneNumber**](WhatsAppPhoneNumbersApi.md#purchasewhatsappphonenumber) | **POST** /v1/whatsapp/phone-numbers/purchase | Purchase phone number |
| [**ReleaseWhatsAppPhoneNumber**](WhatsAppPhoneNumbersApi.md#releasewhatsappphonenumber) | **DELETE** /v1/whatsapp/phone-numbers/{phoneNumberId} | Release phone number |

<a id="getwhatsappphonenumber"></a>
# **GetWhatsAppPhoneNumber**
> GetWhatsAppPhoneNumber200Response GetWhatsAppPhoneNumber (string phoneNumberId)

Get phone number

Retrieve the current status of a purchased phone number. Used to poll for Meta pre-verification completion after purchase. 

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
    public class GetWhatsAppPhoneNumberExample
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
            var apiInstance = new WhatsAppPhoneNumbersApi(httpClient, config, httpClientHandler);
            var phoneNumberId = "phoneNumberId_example";  // string | Phone number record ID

            try
            {
                // Get phone number
                GetWhatsAppPhoneNumber200Response result = apiInstance.GetWhatsAppPhoneNumber(phoneNumberId);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling WhatsAppPhoneNumbersApi.GetWhatsAppPhoneNumber: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the GetWhatsAppPhoneNumberWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Get phone number
    ApiResponse<GetWhatsAppPhoneNumber200Response> response = apiInstance.GetWhatsAppPhoneNumberWithHttpInfo(phoneNumberId);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling WhatsAppPhoneNumbersApi.GetWhatsAppPhoneNumberWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **phoneNumberId** | **string** | Phone number record ID |  |

### Return type

[**GetWhatsAppPhoneNumber200Response**](GetWhatsAppPhoneNumber200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Phone number retrieved successfully |  -  |
| **401** | Unauthorized |  -  |
| **404** | Resource not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="getwhatsappphonenumbers"></a>
# **GetWhatsAppPhoneNumbers**
> GetWhatsAppPhoneNumbers200Response GetWhatsAppPhoneNumbers (string? status = null, string? profileId = null)

List phone numbers

List all WhatsApp phone numbers purchased by the authenticated user. By default, released numbers are excluded. 

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
    public class GetWhatsAppPhoneNumbersExample
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
            var apiInstance = new WhatsAppPhoneNumbersApi(httpClient, config, httpClientHandler);
            var status = "provisioning";  // string? | Filter by status (by default excludes released numbers) (optional) 
            var profileId = "profileId_example";  // string? | Filter by profile (optional) 

            try
            {
                // List phone numbers
                GetWhatsAppPhoneNumbers200Response result = apiInstance.GetWhatsAppPhoneNumbers(status, profileId);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling WhatsAppPhoneNumbersApi.GetWhatsAppPhoneNumbers: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the GetWhatsAppPhoneNumbersWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // List phone numbers
    ApiResponse<GetWhatsAppPhoneNumbers200Response> response = apiInstance.GetWhatsAppPhoneNumbersWithHttpInfo(status, profileId);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling WhatsAppPhoneNumbersApi.GetWhatsAppPhoneNumbersWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **status** | **string?** | Filter by status (by default excludes released numbers) | [optional]  |
| **profileId** | **string?** | Filter by profile | [optional]  |

### Return type

[**GetWhatsAppPhoneNumbers200Response**](GetWhatsAppPhoneNumbers200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Phone numbers retrieved successfully |  -  |
| **401** | Unauthorized |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="purchasewhatsappphonenumber"></a>
# **PurchaseWhatsAppPhoneNumber**
> PurchaseWhatsAppPhoneNumber200Response PurchaseWhatsAppPhoneNumber (PurchaseWhatsAppPhoneNumberRequest purchaseWhatsAppPhoneNumberRequest)

Purchase phone number

Initiate purchasing a WhatsApp phone number. Payment-first flow: the user does not pick a specific number. The system either creates a Stripe Checkout Session (first number) or increments the existing subscription quantity and provisions inline (subsequent numbers).  Requires a paid plan. The maximum number of phone numbers is determined by the user's plan. 

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
    public class PurchaseWhatsAppPhoneNumberExample
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
            var apiInstance = new WhatsAppPhoneNumbersApi(httpClient, config, httpClientHandler);
            var purchaseWhatsAppPhoneNumberRequest = new PurchaseWhatsAppPhoneNumberRequest(); // PurchaseWhatsAppPhoneNumberRequest | 

            try
            {
                // Purchase phone number
                PurchaseWhatsAppPhoneNumber200Response result = apiInstance.PurchaseWhatsAppPhoneNumber(purchaseWhatsAppPhoneNumberRequest);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling WhatsAppPhoneNumbersApi.PurchaseWhatsAppPhoneNumber: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the PurchaseWhatsAppPhoneNumberWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Purchase phone number
    ApiResponse<PurchaseWhatsAppPhoneNumber200Response> response = apiInstance.PurchaseWhatsAppPhoneNumberWithHttpInfo(purchaseWhatsAppPhoneNumberRequest);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling WhatsAppPhoneNumbersApi.PurchaseWhatsAppPhoneNumberWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **purchaseWhatsAppPhoneNumberRequest** | [**PurchaseWhatsAppPhoneNumberRequest**](PurchaseWhatsAppPhoneNumberRequest.md) |  |  |

### Return type

[**PurchaseWhatsAppPhoneNumber200Response**](PurchaseWhatsAppPhoneNumber200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Either a checkout URL (first number) or the provisioned phone number (subsequent numbers).  |  -  |
| **400** | Plan limit reached or profileId required |  -  |
| **401** | Unauthorized |  -  |
| **403** | A paid plan is required |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="releasewhatsappphonenumber"></a>
# **ReleaseWhatsAppPhoneNumber**
> ReleaseWhatsAppPhoneNumber200Response ReleaseWhatsAppPhoneNumber (string phoneNumberId)

Release phone number

Release a purchased phone number. This will: 1. Disconnect any linked WhatsApp social account 2. Decrement the Stripe subscription quantity (or cancel if last number) 3. Release the number from Telnyx 4. Mark the number as released 

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
    public class ReleaseWhatsAppPhoneNumberExample
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
            var apiInstance = new WhatsAppPhoneNumbersApi(httpClient, config, httpClientHandler);
            var phoneNumberId = "phoneNumberId_example";  // string | Phone number record ID

            try
            {
                // Release phone number
                ReleaseWhatsAppPhoneNumber200Response result = apiInstance.ReleaseWhatsAppPhoneNumber(phoneNumberId);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling WhatsAppPhoneNumbersApi.ReleaseWhatsAppPhoneNumber: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the ReleaseWhatsAppPhoneNumberWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Release phone number
    ApiResponse<ReleaseWhatsAppPhoneNumber200Response> response = apiInstance.ReleaseWhatsAppPhoneNumberWithHttpInfo(phoneNumberId);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling WhatsAppPhoneNumbersApi.ReleaseWhatsAppPhoneNumberWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **phoneNumberId** | **string** | Phone number record ID |  |

### Return type

[**ReleaseWhatsAppPhoneNumber200Response**](ReleaseWhatsAppPhoneNumber200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Phone number released successfully |  -  |
| **400** | Phone number is already released or being released |  -  |
| **401** | Unauthorized |  -  |
| **404** | Resource not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

