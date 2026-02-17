# Late.Model.ConnectionLog
Connection event log showing account connection/disconnection history

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Id** | **string** |  | [optional] 
**UserId** | **string** | User who owns the connection (may be null for early OAuth failures) | [optional] 
**ProfileId** | **string** |  | [optional] 
**AccountId** | **string** | The social account ID (present on successful connections and disconnects) | [optional] 
**Platform** | **string** |  | [optional] 
**EventType** | **string** | Type of connection event: connect_success, connect_failed, disconnect, reconnect_success, reconnect_failed | [optional] 
**ConnectionMethod** | **string** | How the connection was initiated | [optional] 
**Error** | [**ConnectionLogError**](ConnectionLogError.md) |  | [optional] 
**Success** | [**ConnectionLogSuccess**](ConnectionLogSuccess.md) |  | [optional] 
**Context** | [**ConnectionLogContext**](ConnectionLogContext.md) |  | [optional] 
**DurationMs** | **int** | How long the operation took in milliseconds | [optional] 
**Metadata** | **Object** | Additional metadata | [optional] 
**CreatedAt** | **DateTime** |  | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

