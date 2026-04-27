# Zernio.Model.SendWhatsAppConversionRequest
In addition to the `required` list, **at least one of `conversationId` or `phoneE164` must be supplied** (used to resolve the originating CTWA conversation). The route enforces this at the Zod boundary; OpenAPI's `required` cannot express OR-required cleanly. 

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**AccountId** | **string** | WhatsApp SocialAccount ID. | 
**EventName** | **string** | Live-verified allowlist of event names accepted by Meta&#39;s CAPI for Business Messaging (Graph API v25.0). Other standard pixel events including &#x60;Lead&#x60;, &#x60;CompleteRegistration&#x60;, &#x60;Subscribe&#x60;, &#x60;Schedule&#x60;, &#x60;Contact&#x60;, &#x60;StartTrial&#x60;, &#x60;AddPaymentInfo&#x60;, &#x60;Search&#x60;, and &#x60;SubmitApplication&#x60; are rejected with subcode 2804066 (\&quot;Messaging Event Invalid Event Type\&quot;) on &#x60;action_source &#x3D; business_messaging&#x60; events. Custom event names are also rejected.  Use &#x60;LeadSubmitted&#x60; (NOT &#x60;Lead&#x60;) for lead-style conversions.  | 
**EventTime** | **decimal** | Unix seconds. Defaults to the time of the request when omitted. Meta&#39;s attribution window is 7 days from click; events older than that lose attribution.  | [optional] 
**EventId** | **string** | Stable dedup key. Reuse to suppress duplicate events (Meta dedupes against pixel events with the same id).  | 
**ConversationId** | **string** | Zernio Conversation &#x60;_id&#x60; (preferred lookup). The conversation must have a captured &#x60;ctwa_clid&#x60; in metadata (set automatically by the WhatsApp webhook on the first inbound message after a CTWA ad click).  | [optional] 
**PhoneE164** | **string** | Contact phone number, digits only with no &#39;+&#39;. When used in lieu of &#x60;conversationId&#x60;, the handler resolves to the most recent CTWA-attributed conversation for this phone on the supplied account.  | [optional] 
**Value** | **decimal** | Conversion value (e.g. order total). | [optional] 
**Currency** | **string** | ISO 4217 currency code (e.g. &#x60;USD&#x60;). | [optional] 
**ContentIds** | **List&lt;string&gt;** | Optional product / content identifiers. | [optional] 
**Email** | **string** | User email. Normalized + SHA-256 hashed before sending to Meta. | [optional] 
**ExternalId** | **string** | Stable customer identifier. Lowercased + SHA-256 hashed before sending to Meta.  | [optional] 
**TestCode** | **string** | Meta &#x60;test_event_code&#x60; passthrough. Routes the event to the Test Events tab in Events Manager instead of the production dataset, useful for development.  | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

