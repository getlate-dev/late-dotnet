# Zernio.Model.RecyclingConfig
Configure automatic post recycling (reposting at regular intervals). After the post is published, the system creates new scheduled copies at the specified interval until expiration conditions are met. Supports weekly or monthly intervals. Maximum 10 active recycling posts per account. YouTube and TikTok platforms are excluded from recycling. Content variations are recommended for Twitter and Pinterest to avoid duplicate flags. 

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Enabled** | **bool** | Set to false to disable recycling on this post | [optional] [default to true]
**Gap** | **int** | Number of interval units between each repost. Required when enabling recycling. | [optional] 
**GapFreq** | **string** | Interval unit for the gap. Defaults to &#39;month&#39;. | [optional] [default to GapFreqEnum.Month]
**StartDate** | **DateTime** | When to start the recycling cycle. Defaults to the post&#39;s scheduledFor date. | [optional] 
**ExpireCount** | **int** | Stop recycling after this many copies have been created | [optional] 
**ExpireDate** | **DateTime** | Stop recycling after this date, regardless of count | [optional] 
**ContentVariations** | **List&lt;string&gt;** | Array of content variations for recycled copies. On each recycle, the next variation is used in round-robin order. Recommended for Twitter and Pinterest to avoid duplicate content flags. If omitted, the original post content is used for all recycled copies. Send an empty array [] to clear existing variations. Must have 2+ entries when setting variations. Platform-level customContent still overrides the base content per platform.  | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

