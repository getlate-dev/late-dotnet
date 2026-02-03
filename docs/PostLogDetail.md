# Late.Model.PostLogDetail

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Id** | **string** |  | [optional] 
**PostId** | [**PostLogDetailAllOfPostId**](PostLogDetailAllOfPostId.md) |  | [optional] 
**UserId** | **string** |  | [optional] 
**ProfileId** | **string** |  | [optional] 
**Platform** | **string** |  | [optional] 
**AccountId** | [**PostLogDetailAllOfAccountId**](PostLogDetailAllOfAccountId.md) |  | [optional] 
**AccountUsername** | **string** |  | [optional] 
**Action** | **string** | Type of action logged: - &#x60;publish&#x60; - Initial publish attempt - &#x60;retry&#x60; - Retry after failure - &#x60;media_upload&#x60; - Media upload step - &#x60;rate_limit_pause&#x60; - Account paused due to rate limits - &#x60;token_refresh&#x60; - Token was refreshed - &#x60;cancelled&#x60; - Post was cancelled  | [optional] 
**Status** | **string** |  | [optional] 
**StatusCode** | **int** | HTTP status code from platform API | [optional] 
**Endpoint** | **string** | Platform API endpoint called | [optional] 
**Request** | [**PostLogRequest**](PostLogRequest.md) |  | [optional] 
**Response** | [**PostLogResponse**](PostLogResponse.md) |  | [optional] 
**DurationMs** | **int** | How long the operation took in milliseconds | [optional] 
**AttemptNumber** | **int** | Attempt number (1 for first try, 2+ for retries) | [optional] 
**CreatedAt** | **DateTime** |  | [optional] 
**Metadata** | **Object** | Additional metadata (e.g., rate limit info) | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

