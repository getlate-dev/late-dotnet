# Late.Api.WhatsAppPhoneNumbersApi

All URIs are relative to *https://getlate.dev/api*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**GetPreverifiedWhatsAppNumbers**](WhatsAppPhoneNumbersApi.md#getpreverifiedwhatsappnumbers) | **GET** /v1/whatsapp/phone-numbers/preverified | Get pre-verified numbers |
| [**GetWhatsAppPhoneNumber**](WhatsAppPhoneNumbersApi.md#getwhatsappphonenumber) | **GET** /v1/whatsapp/phone-numbers/{phoneNumberId} | Get phone number |
| [**GetWhatsAppPhoneNumbers**](WhatsAppPhoneNumbersApi.md#getwhatsappphonenumbers) | **GET** /v1/whatsapp/phone-numbers | List phone numbers |
| [**PurchaseWhatsAppPhoneNumber**](WhatsAppPhoneNumbersApi.md#purchasewhatsappphonenumber) | **POST** /v1/whatsapp/phone-numbers/purchase | Purchase phone number |
| [**ReleaseWhatsAppPhoneNumber**](WhatsAppPhoneNumbersApi.md#releasewhatsappphonenumber) | **DELETE** /v1/whatsapp/phone-numbers/{phoneNumberId} | Release phone number |
| [**RequestWhatsAppVerificationCode**](WhatsAppPhoneNumbersApi.md#requestwhatsappverificationcode) | **POST** /v1/whatsapp/phone-numbers/{phoneNumberId}/request-code | Request OTP |
| [**SearchAvailableWhatsAppNumbers**](WhatsAppPhoneNumbersApi.md#searchavailablewhatsappnumbers) | **GET** /v1/whatsapp/phone-numbers/available | Search available numbers |
| [**VerifyWhatsAppPhoneNumber**](WhatsAppPhoneNumbersApi.md#verifywhatsappphonenumber) | **POST** /v1/whatsapp/phone-numbers/{phoneNumberId}/verify | Verify OTP |

<a id="getpreverifiedwhatsappnumbers"></a>
# **GetPreverifiedWhatsAppNumbers**
> GetPreverifiedWhatsAppNumbers200Response GetPreverifiedWhatsAppNumbers (string profileId)

Get pre-verified numbers

Returns the user's pre-verified phone number IDs that are ready for OTP-free Embedded Signup. Only returns numbers with verified Meta status and non-expired verification. 

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
    public class GetPreverifiedWhatsAppNumbersExample
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
            var apiInstance = new WhatsAppPhoneNumbersApi(httpClient, config, httpClientHandler);
            var profileId = "profileId_example";  // string | Profile ID to filter by

            try
            {
                // Get pre-verified numbers
                GetPreverifiedWhatsAppNumbers200Response result = apiInstance.GetPreverifiedWhatsAppNumbers(profileId);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling WhatsAppPhoneNumbersApi.GetPreverifiedWhatsAppNumbers: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the GetPreverifiedWhatsAppNumbersWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Get pre-verified numbers
    ApiResponse<GetPreverifiedWhatsAppNumbers200Response> response = apiInstance.GetPreverifiedWhatsAppNumbersWithHttpInfo(profileId);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling WhatsAppPhoneNumbersApi.GetPreverifiedWhatsAppNumbersWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **profileId** | **string** | Profile ID to filter by |  |

### Return type

[**GetPreverifiedWhatsAppNumbers200Response**](GetPreverifiedWhatsAppNumbers200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Pre-verified numbers retrieved |  -  |
| **400** | profileId is required |  -  |
| **401** | Unauthorized |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

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
using Late.Api;
using Late.Client;
using Late.Model;

namespace Example
{
    public class GetWhatsAppPhoneNumberExample
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
using Late.Api;
using Late.Client;
using Late.Model;

namespace Example
{
    public class GetWhatsAppPhoneNumbersExample
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
using Late.Api;
using Late.Client;
using Late.Model;

namespace Example
{
    public class PurchaseWhatsAppPhoneNumberExample
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
using Late.Api;
using Late.Client;
using Late.Model;

namespace Example
{
    public class ReleaseWhatsAppPhoneNumberExample
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

<a id="requestwhatsappverificationcode"></a>
# **RequestWhatsAppVerificationCode**
> RequestWhatsAppVerificationCode200Response RequestWhatsAppVerificationCode (string phoneNumberId, RequestWhatsAppVerificationCodeRequest? requestWhatsAppVerificationCodeRequest = null)

Request OTP

Request a new OTP verification code from Meta for a pre-verified phone number. Useful when the initial SMS did not arrive or when re-verifying before the 90-day expiry. 

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
    public class RequestWhatsAppVerificationCodeExample
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
            var apiInstance = new WhatsAppPhoneNumbersApi(httpClient, config, httpClientHandler);
            var phoneNumberId = "phoneNumberId_example";  // string | Phone number record ID
            var requestWhatsAppVerificationCodeRequest = new RequestWhatsAppVerificationCodeRequest?(); // RequestWhatsAppVerificationCodeRequest? |  (optional) 

            try
            {
                // Request OTP
                RequestWhatsAppVerificationCode200Response result = apiInstance.RequestWhatsAppVerificationCode(phoneNumberId, requestWhatsAppVerificationCodeRequest);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling WhatsAppPhoneNumbersApi.RequestWhatsAppVerificationCode: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the RequestWhatsAppVerificationCodeWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Request OTP
    ApiResponse<RequestWhatsAppVerificationCode200Response> response = apiInstance.RequestWhatsAppVerificationCodeWithHttpInfo(phoneNumberId, requestWhatsAppVerificationCodeRequest);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling WhatsAppPhoneNumbersApi.RequestWhatsAppVerificationCodeWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **phoneNumberId** | **string** | Phone number record ID |  |
| **requestWhatsAppVerificationCodeRequest** | [**RequestWhatsAppVerificationCodeRequest?**](RequestWhatsAppVerificationCodeRequest?.md) |  | [optional]  |

### Return type

[**RequestWhatsAppVerificationCode200Response**](RequestWhatsAppVerificationCode200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Verification code requested successfully |  -  |
| **400** | Number has not been added to Meta pre-verified pool |  -  |
| **401** | Unauthorized |  -  |
| **404** | Resource not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="searchavailablewhatsappnumbers"></a>
# **SearchAvailableWhatsAppNumbers**
> SearchAvailableWhatsAppNumbers200Response SearchAvailableWhatsAppNumbers (string? prefix = null, string? locality = null, string? contains = null, int? limit = null)

Search available numbers

Search for available US phone numbers that can be purchased for WhatsApp Business. Requires a paid plan. Numbers are sourced from Telnyx. 

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
    public class SearchAvailableWhatsAppNumbersExample
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
            var apiInstance = new WhatsAppPhoneNumbersApi(httpClient, config, httpClientHandler);
            var prefix = "prefix_example";  // string? | Area code to search (e.g., \"212\" for New York) (optional) 
            var locality = "locality_example";  // string? | City name (e.g., \"New York\") (optional) 
            var contains = "contains_example";  // string? | Pattern to match within the phone number (optional) 
            var limit = 20;  // int? | Maximum results (default 20, max 100) (optional)  (default to 20)

            try
            {
                // Search available numbers
                SearchAvailableWhatsAppNumbers200Response result = apiInstance.SearchAvailableWhatsAppNumbers(prefix, locality, contains, limit);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling WhatsAppPhoneNumbersApi.SearchAvailableWhatsAppNumbers: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the SearchAvailableWhatsAppNumbersWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Search available numbers
    ApiResponse<SearchAvailableWhatsAppNumbers200Response> response = apiInstance.SearchAvailableWhatsAppNumbersWithHttpInfo(prefix, locality, contains, limit);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling WhatsAppPhoneNumbersApi.SearchAvailableWhatsAppNumbersWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **prefix** | **string?** | Area code to search (e.g., \&quot;212\&quot; for New York) | [optional]  |
| **locality** | **string?** | City name (e.g., \&quot;New York\&quot;) | [optional]  |
| **contains** | **string?** | Pattern to match within the phone number | [optional]  |
| **limit** | **int?** | Maximum results (default 20, max 100) | [optional] [default to 20] |

### Return type

[**SearchAvailableWhatsAppNumbers200Response**](SearchAvailableWhatsAppNumbers200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Available numbers retrieved |  -  |
| **401** | Unauthorized |  -  |
| **403** | A paid plan is required |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

<a id="verifywhatsappphonenumber"></a>
# **VerifyWhatsAppPhoneNumber**
> VerifyWhatsAppPhoneNumber200Response VerifyWhatsAppPhoneNumber (string phoneNumberId, VerifyWhatsAppPhoneNumberRequest verifyWhatsAppPhoneNumberRequest)

Verify OTP

Manually verify a phone number by entering the OTP code received via SMS or voice call. This is a fallback for when the auto-verification webhook does not capture the code. Verification is valid for 90 days. 

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
    public class VerifyWhatsAppPhoneNumberExample
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
            var apiInstance = new WhatsAppPhoneNumbersApi(httpClient, config, httpClientHandler);
            var phoneNumberId = "phoneNumberId_example";  // string | Phone number record ID
            var verifyWhatsAppPhoneNumberRequest = new VerifyWhatsAppPhoneNumberRequest(); // VerifyWhatsAppPhoneNumberRequest | 

            try
            {
                // Verify OTP
                VerifyWhatsAppPhoneNumber200Response result = apiInstance.VerifyWhatsAppPhoneNumber(phoneNumberId, verifyWhatsAppPhoneNumberRequest);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling WhatsAppPhoneNumbersApi.VerifyWhatsAppPhoneNumber: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Using the VerifyWhatsAppPhoneNumberWithHttpInfo variant
This returns an ApiResponse object which contains the response data, status code and headers.

```csharp
try
{
    // Verify OTP
    ApiResponse<VerifyWhatsAppPhoneNumber200Response> response = apiInstance.VerifyWhatsAppPhoneNumberWithHttpInfo(phoneNumberId, verifyWhatsAppPhoneNumberRequest);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling WhatsAppPhoneNumbersApi.VerifyWhatsAppPhoneNumberWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **phoneNumberId** | **string** | Phone number record ID |  |
| **verifyWhatsAppPhoneNumberRequest** | [**VerifyWhatsAppPhoneNumberRequest**](VerifyWhatsAppPhoneNumberRequest.md) |  |  |

### Return type

[**VerifyWhatsAppPhoneNumber200Response**](VerifyWhatsAppPhoneNumber200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Phone number verified successfully (or already verified) |  -  |
| **400** | Invalid code or number not in Meta pre-verified pool |  -  |
| **401** | Unauthorized |  -  |
| **404** | Resource not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

