# Zernio.Model.ConversionEvent
A single conversion event to relay to the ad platform. All PII fields (email, phone, names) are hashed with SHA-256 server-side using each platform's normalization rules before they leave Zernio. Callers send plaintext. 

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**EventName** | **string** | Standard event name (Purchase, Lead, CompleteRegistration, AddToCart, InitiateCheckout, AddPaymentInfo, Subscribe, StartTrial, ViewContent, Search, Contact, SubmitApplication, Schedule) or a custom string (only supported on platforms that accept custom events).  | 
**EventTime** | **int** | When the conversion happened, in unix seconds. | 
**EventId** | **string** | Unique dedup key. The same eventId must be used on pixel + CAPI to prevent double-counting. Mapped to event_id on Meta and transactionId on Google.  | 
**Value** | **decimal** | Conversion value in the specified currency. | [optional] 
**Currency** | **string** | ISO 4217 currency code. | [optional] 
**User** | [**ConversionEventUser**](ConversionEventUser.md) |  | 
**Items** | [**List&lt;ConversionEventItemsInner&gt;**](ConversionEventItemsInner.md) | Item-level detail for ecommerce events. | [optional] 
**SourceUrl** | **string** | URL where the conversion originated (used by Meta). | [optional] 
**ActionSource** | **string** | Where the conversion happened. Used by Meta; Google ignores. | [optional] 
**PlatformData** | **Dictionary&lt;string, Object&gt;** | Escape hatch for platform-specific fields we haven&#39;t normalized. Forwarded as-is. | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

