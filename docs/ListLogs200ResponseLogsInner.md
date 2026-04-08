# Late.Model.ListLogs200ResponseLogsInner

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Type** | **string** | Log category (publishing, connections, webhooks, messaging) | [optional] 
**Action** | **string** | Specific action (post.published, message.sent, account.connected, etc.) | [optional] 
**UserId** | **string** |  | [optional] 
**Platform** | **string** |  | [optional] 
**AccountId** | **string** |  | [optional] 
**Status** | **string** |  | [optional] 
**StatusCode** | **int** |  | [optional] 
**ErrorMessage** | **string** |  | [optional] 
**ErrorCode** | **string** |  | [optional] 
**DurationMs** | **int** |  | [optional] 
**Endpoint** | **string** | The API endpoint that triggered this log | [optional] 
**RequestBody** | **string** | Request JSON (truncated to 5KB) | [optional] 
**ResponseBody** | **string** | Response JSON (truncated to 10KB) | [optional] 
**CreatedAt** | **DateTime** |  | [optional] 
**Metadata** | **string** | Additional context as JSON string | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

