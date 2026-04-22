# Zernio.Model.CreateStandaloneAdRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**AccountId** | **string** |  | 
**AdAccountId** | **string** |  | 
**Name** | **string** |  | 
**Goal** | **string** | Required on legacy + multi-creative shapes. Inherited from the ad set on the attach shape. Available goals vary by platform. | [optional] 
**BudgetAmount** | **decimal** | Required on legacy + multi-creative shapes. Inherited on attach. | [optional] 
**BudgetType** | **string** | Required on legacy + multi-creative shapes. Inherited on attach. | [optional] 
**Currency** | **string** |  | [optional] 
**Headline** | **string** | Required on legacy + attach shapes (skip for multi-creative — use &#x60;creatives[].headline&#x60;). Max: Meta&#x3D;255, Google&#x3D;30, Pinterest&#x3D;100 | [optional] 
**LongHeadline** | **string** | Google Display only | [optional] 
**Body** | **string** | Required on legacy + attach shapes. Max: Google&#x3D;90, Pinterest&#x3D;500 | [optional] 
**CallToAction** | **string** | Required on legacy + attach shapes. Meta only. | [optional] 
**LinkUrl** | **string** | Required on legacy + attach shapes. Skip for multi-creative. | [optional] 
**ImageUrl** | **string** | Required on legacy + attach shapes. Not required for Google Search campaigns. | [optional] 
**Creatives** | [**List&lt;CreateStandaloneAdRequestCreativesInner&gt;**](CreateStandaloneAdRequestCreativesInner.md) | Meta-only. When present, switches to the multi-creative shape: creates 1 campaign + 1 ad set + N ads (one per entry here). Top-level &#x60;headline&#x60; / &#x60;body&#x60; / &#x60;imageUrl&#x60; / &#x60;linkUrl&#x60; / &#x60;callToAction&#x60; are ignored in this mode. Mutually exclusive with &#x60;adSetId&#x60;.  | [optional] 
**AdSetId** | **string** | Meta-only. When present, switches to the attach shape: adds one new ad to this existing ad set without creating a new campaign. Budget, targeting, goal, and schedule are inherited from the ad set on Meta. Mutually exclusive with &#x60;creatives[]&#x60;.  | [optional] 
**BusinessName** | **string** | Google Display only | [optional] 
**BoardId** | **string** | Pinterest only. Board ID (auto-creates if not provided). | [optional] 
**Countries** | **List&lt;string&gt;** |  | [optional] 
**AgeMin** | **int** |  | [optional] 
**AgeMax** | **int** |  | [optional] 
**Interests** | [**List&lt;UpdateAdRequestTargetingInterestsInner&gt;**](UpdateAdRequestTargetingInterestsInner.md) | Interest objects from /v1/ads/interests. Each must include id and name. | [optional] 
**EndDate** | **DateTime** | Required for lifetime budgets | [optional] 
**AudienceId** | **string** | Custom audience ID for targeting | [optional] 
**CampaignType** | **string** | Google only | [optional] [default to CampaignTypeEnum.Display]
**Keywords** | **List&lt;string&gt;** | Google Search only | [optional] 
**AdditionalHeadlines** | **List&lt;string&gt;** | Google Search RSA only. Extra headlines. | [optional] 
**AdditionalDescriptions** | **List&lt;string&gt;** | Google Search RSA only. Extra descriptions. | [optional] 
**AdvantageAudience** | **int** | Meta only. Controls the Advantage audience feature (targeting_automation). 0 &#x3D; disabled (default), 1 &#x3D; enabled. Meta Marketing API requires this field on all ad set creation requests. | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

