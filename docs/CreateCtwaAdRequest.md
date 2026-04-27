# Zernio.Model.CreateCtwaAdRequest
In addition to the `required` list, **exactly one of `imageUrl` or `video` must be supplied** (mutually exclusive). The route enforces this at the Zod boundary; OpenAPI's `required` cannot express OR-required cleanly. 

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**AccountId** | **string** | Facebook or Instagram SocialAccount ID. | 
**AdAccountId** | **string** | Meta ad account ID, e.g. &#x60;act_123456789&#x60;. | 
**Name** | **string** | Ad display name. Used to derive campaign / ad set names. | 
**Headline** | **string** |  | 
**Body** | **string** | Primary text shown above the image / video. | 
**ImageUrl** | **string** | Image asset for image creatives. Mutually exclusive with &#x60;video&#x60;. Required if &#x60;video&#x60; is not supplied.  | [optional] 
**Video** | [**CreateCtwaAdRequestVideo**](CreateCtwaAdRequestVideo.md) |  | [optional] 
**BudgetAmount** | **decimal** | Budget amount in the ad account&#39;s currency major units (e.g. dollars for USD, not cents). Must be positive.  | 
**BudgetType** | **string** |  | 
**Currency** | **string** | ISO 4217 currency code matching the ad account&#39;s currency (e.g. &#x60;USD&#x60;). Optional — Meta infers from the ad account when omitted.  | [optional] 
**EndDate** | **DateTime** | ISO 8601 datetime. Required when &#x60;budgetType&#x60; is &#x60;lifetime&#x60;.  | [optional] 
**Countries** | **List&lt;string&gt;** | ISO 3166-1 alpha-2 country codes. Defaults to &#x60;[\&quot;US\&quot;]&#x60;. | [optional] 
**AgeMin** | **int** |  | [optional] 
**AgeMax** | **int** |  | [optional] 
**Interests** | [**List&lt;CreateCtwaAdRequestInterestsInner&gt;**](CreateCtwaAdRequestInterestsInner.md) |  | [optional] 
**AudienceId** | **string** | Custom audience ID to target. | [optional] 
**AdvantageAudience** | **int** | Meta&#39;s Advantage+ audience expansion. &#x60;0&#x60; (default) keeps targeting strict; &#x60;1&#x60; lets Meta expand beyond the supplied targeting when its delivery system finds better matches. Always sent on CREATE (Meta requires it).  | [optional] 
**Objective** | **string** | Defaults to &#x60;OUTCOME_ENGAGEMENT&#x60; (the broadly-supported CTWA objective). &#x60;OUTCOME_SALES&#x60; and &#x60;OUTCOME_LEADS&#x60; require additional account configuration (Dataset linked to the WABA for sales) and may be rejected by Meta if missing.  | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

