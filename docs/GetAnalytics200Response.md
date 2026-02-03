# Late.Model.GetAnalytics200Response

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**PostId** | **string** |  | [optional] 
**Status** | **string** |  | [optional] 
**Content** | **string** |  | [optional] 
**ScheduledFor** | **DateTime** |  | [optional] 
**PublishedAt** | **DateTime** |  | [optional] 
**Analytics** | [**PostAnalytics**](PostAnalytics.md) |  | [optional] 
**PlatformAnalytics** | [**List&lt;PlatformAnalytics&gt;**](PlatformAnalytics.md) |  | [optional] 
**Platform** | **string** |  | [optional] 
**PlatformPostUrl** | **string** |  | [optional] 
**IsExternal** | **bool** |  | [optional] 
**Overview** | [**AnalyticsOverview**](AnalyticsOverview.md) |  | [optional] 
**Posts** | [**List&lt;AnalyticsListResponsePostsInner&gt;**](AnalyticsListResponsePostsInner.md) |  | [optional] 
**Pagination** | [**Pagination**](Pagination.md) |  | [optional] 
**Accounts** | [**List&lt;SocialAccount&gt;**](SocialAccount.md) | Connected social accounts (followerCount and followersLastUpdated only included if user has analytics add-on) | [optional] 
**HasAnalyticsAccess** | **bool** | Whether user has analytics add-on access | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

