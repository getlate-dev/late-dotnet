# Zernio.Model.GetInboxConversationMessages200Response

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Status** | **string** |  | [optional] 
**Pagination** | [**GetInboxConversationMessages200ResponsePagination**](GetInboxConversationMessages200ResponsePagination.md) |  | [optional] 
**SortOrderApplied** | **string** | Sort order actually applied to the returned page. May differ from the requested &#x60;sortOrder&#x60; for Twitter, Facebook and Bluesky (always &#x60;desc&#x60; regardless of request).  | [optional] 
**Messages** | [**List&lt;GetInboxConversationMessages200ResponseMessagesInner&gt;**](GetInboxConversationMessages200ResponseMessagesInner.md) |  | [optional] 
**LastUpdated** | **DateTime** |  | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

