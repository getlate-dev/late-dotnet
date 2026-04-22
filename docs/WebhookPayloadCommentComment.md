# Zernio.Model.WebhookPayloadCommentComment

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Id** | **string** | Platform comment ID | 
**PostId** | **string** | Internal post ID (null for posts not published through Zernio) | 
**PlatformPostId** | **string** | Platform&#39;s post ID | 
**Platform** | **string** |  | 
**Text** | **string** | Comment text content | 
**Author** | [**WebhookPayloadCommentCommentAuthor**](WebhookPayloadCommentCommentAuthor.md) |  | 
**CreatedAt** | **DateTime** |  | 
**IsReply** | **bool** | Whether this is a reply to another comment | 
**ParentCommentId** | **string** | Parent comment ID if this is a reply | 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

