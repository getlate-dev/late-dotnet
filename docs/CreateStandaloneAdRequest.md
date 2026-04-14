# Late.Model.CreateStandaloneAdRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**AccountId** | **string** |  | 
**AdAccountId** | **string** |  | 
**Name** | **string** |  | 
**Goal** | **string** |  | 
**BudgetAmount** | **decimal** |  | 
**BudgetType** | **string** |  | 
**Currency** | **string** |  | [optional] 
**Headline** | **string** | Required for most platforms. Max: Meta&#x3D;255, Google&#x3D;30, Pinterest&#x3D;100 | [optional] 
**LongHeadline** | **string** | Google Display only | [optional] 
**Body** | **string** | Max: Google&#x3D;90, Pinterest&#x3D;500 | 
**CallToAction** | **string** | Meta only | [optional] 
**LinkUrl** | **string** |  | [optional] 
**ImageUrl** | **string** | Image URL (or video URL for TikTok). Not required for Google Search campaigns. | [optional] 
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

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

