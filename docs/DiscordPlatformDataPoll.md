# Zernio.Model.DiscordPlatformDataPoll
Native Discord poll. Cannot be combined with media attachments in the same message.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Question** | [**DiscordPlatformDataPollQuestion**](DiscordPlatformDataPollQuestion.md) |  | [optional] 
**Answers** | [**List&lt;DiscordPlatformDataPollAnswersInner&gt;**](DiscordPlatformDataPollAnswersInner.md) | 1-10 answer options | [optional] 
**Duration** | **int** | Poll duration in hours (1-768). Default 24. | [optional] 
**AllowMultiselect** | **bool** | Allow users to select multiple answers. Default false. | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

