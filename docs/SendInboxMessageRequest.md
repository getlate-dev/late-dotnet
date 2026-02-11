# Late.Model.SendInboxMessageRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**AccountId** | **string** | Social account ID | 
**Message** | **string** | Message text | [optional] 
**QuickReplies** | [**List&lt;SendInboxMessageRequestQuickRepliesInner&gt;**](SendInboxMessageRequestQuickRepliesInner.md) | Quick reply buttons. Mutually exclusive with buttons. Max 13 items. | [optional] 
**Buttons** | [**List&lt;SendInboxMessageRequestButtonsInner&gt;**](SendInboxMessageRequestButtonsInner.md) | Action buttons. Mutually exclusive with quickReplies. Max 3 items. | [optional] 
**Template** | [**SendInboxMessageRequestTemplate**](SendInboxMessageRequestTemplate.md) |  | [optional] 
**ReplyMarkup** | [**SendInboxMessageRequestReplyMarkup**](SendInboxMessageRequestReplyMarkup.md) |  | [optional] 
**MessagingType** | **string** | Facebook messaging type. Required when using messageTag. | [optional] 
**MessageTag** | **string** | Facebook message tag for messaging outside 24h window. Requires messagingType MESSAGE_TAG. Instagram only supports HUMAN_AGENT. | [optional] 
**ReplyTo** | **string** | Platform message ID to reply to (Telegram only). | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

