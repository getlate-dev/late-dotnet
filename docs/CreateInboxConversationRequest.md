# Zernio.Model.CreateInboxConversationRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**AccountId** | **string** | The social account ID to send from | 
**ParticipantId** | **string** | Twitter numeric user ID of the recipient. Provide either this or participantUsername. | [optional] 
**ParticipantUsername** | **string** | Twitter username (with or without @) of the recipient. Resolved to a user ID via lookup. Provide either this or participantId. | [optional] 
**Message** | **string** | Text content of the message. At least one of message or attachment is required. | [optional] 
**SkipDmCheck** | **bool** | Skip the receives_your_dm eligibility check before sending. Use if you have already verified the recipient accepts DMs. | [optional] [default to false]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

