# Late.Model.UpdateQueueSlotRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**ProfileId** | **string** |  | 
**QueueId** | **string** | Queue ID to update (optional) | [optional] 
**Name** | **string** | Queue name | [optional] 
**Timezone** | **string** |  | 
**Slots** | [**List&lt;QueueSlot&gt;**](QueueSlot.md) |  | 
**Active** | **bool** |  | [optional] [default to true]
**SetAsDefault** | **bool** | Make this queue the default | [optional] 
**ReshuffleExisting** | **bool** | Whether to reschedule existing queued posts to match new slots | [optional] [default to false]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

