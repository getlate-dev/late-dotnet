# Late.Model.PostLog
Publishing log entry showing details of a post publishing attempt

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Id** | **string** |  | [optional] 
**PostId** | [**PostLogPostId**](PostLogPostId.md) |  | [optional] 
**UserId** | **string** |  | [optional] 
**ProfileId** | **string** |  | [optional] 
**Platform** | **string** |  | [optional] 
**AccountId** | **string** |  | [optional] 
**AccountUsername** | **string** |  | [optional] 
**Action** | **string** | Type of action logged: publish (initial attempt), retry (after failure), media_upload, rate_limit_pause, token_refresh, cancelled | [optional] 
**Status** | **string** |  | [optional] 
**StatusCode** | **int** | HTTP status code from platform API | [optional] 
**Endpoint** | **string** | Platform API endpoint called | [optional] 
**Request** | [**PostLogRequest**](PostLogRequest.md) |  | [optional] 
**Response** | [**PostLogResponse**](PostLogResponse.md) |  | [optional] 
**DurationMs** | **int** | How long the operation took in milliseconds | [optional] 
**AttemptNumber** | **int** | Attempt number (1 for first try, 2+ for retries) | [optional] 
**CreatedAt** | **DateTime** |  | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

