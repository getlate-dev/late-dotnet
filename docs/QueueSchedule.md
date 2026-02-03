# Late.Model.QueueSchedule

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Id** | **string** | Unique queue identifier | [optional] 
**ProfileId** | **string** | Profile ID this queue belongs to | [optional] 
**Name** | **string** | Queue name (e.g., \&quot;Morning Posts\&quot;, \&quot;Evening Content\&quot;) | [optional] 
**Timezone** | **string** | IANA timezone (e.g., America/New_York) | [optional] 
**Slots** | [**List&lt;QueueSlot&gt;**](QueueSlot.md) |  | [optional] 
**Active** | **bool** | Whether the queue is active | [optional] 
**IsDefault** | **bool** | Whether this is the default queue for the profile (used when no queueId specified) | [optional] 
**CreatedAt** | **DateTime** |  | [optional] 
**UpdatedAt** | **DateTime** |  | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

