# Late.Model.GetInboxPostComments200ResponseCommentsInner

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Id** | **string** |  | [optional] 
**Message** | **string** |  | [optional] 
**CreatedTime** | **DateTime** |  | [optional] 
**From** | [**GetInboxPostComments200ResponseCommentsInnerFrom**](GetInboxPostComments200ResponseCommentsInnerFrom.md) |  | [optional] 
**LikeCount** | **int** |  | [optional] 
**ReplyCount** | **int** |  | [optional] 
**Platform** | **string** | The platform this comment is from | [optional] 
**Url** | **string** | Direct link to the comment on the platform (if available) | [optional] 
**Replies** | **List&lt;Object&gt;** |  | [optional] 
**CanReply** | **bool** |  | [optional] 
**CanDelete** | **bool** |  | [optional] 
**CanHide** | **bool** | Whether this comment can be hidden (Facebook | [optional] 
**CanLike** | **bool** | Whether this comment can be liked (Facebook | [optional] 
**IsHidden** | **bool** | Whether the comment is currently hidden | [optional] 
**IsLiked** | **bool** | Whether the current user has liked this comment | [optional] 
**LikeUri** | **string** | Bluesky like URI for unliking | [optional] 
**Cid** | **string** | Bluesky content identifier | [optional] 
**ParentId** | **string** | Parent comment ID for nested replies | [optional] 
**RootUri** | **string** | Bluesky root post URI | [optional] 
**RootCid** | **string** | Bluesky root post CID | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

