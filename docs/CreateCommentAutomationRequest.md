# Zernio.Model.CreateCommentAutomationRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**ProfileId** | **string** |  | 
**AccountId** | **string** | Instagram or Facebook account ID | 
**PlatformPostId** | **string** | Platform media/post ID. Omit for an account-wide (any-post) automation. | [optional] 
**PostId** | **string** | Zernio post ID. Required only when also targeting a specific post via platformPostId. | [optional] 
**PostTitle** | **string** | Post content snippet for display | [optional] 
**Name** | **string** | Automation label | 
**Keywords** | **List&lt;string&gt;** | Trigger keywords (empty &#x3D; any comment triggers) | [optional] 
**MatchMode** | **string** |  | [optional] [default to MatchModeEnum.Contains]
**DmMessage** | **string** | DM text to send to commenter | 
**CommentReply** | **string** | Optional public reply to the comment | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

