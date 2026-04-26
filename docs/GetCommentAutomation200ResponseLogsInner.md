# Zernio.Model.GetCommentAutomation200ResponseLogsInner

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Id** | **string** |  | [optional] 
**CommentId** | **string** |  | [optional] 
**CommenterId** | **string** |  | [optional] 
**CommenterName** | **string** |  | [optional] 
**CommentText** | **string** |  | [optional] 
**Status** | **string** | DM outcome | [optional] 
**Error** | **string** | DM error message if status is failed | [optional] 
**CommentReplyStatus** | **string** | Outcome of the optional public reply on the triggering comment. &#39;skipped&#39; if no commentReply was configured or if the DM failed (the public reply is not attempted in that case). | [optional] 
**CommentReplyError** | **string** | Public-reply error message if commentReplyStatus is failed | [optional] 
**CreatedAt** | **DateTime** |  | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

