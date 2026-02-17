# Late.Model.ConnectBlueskyCredentialsRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Identifier** | **string** | Your Bluesky handle (e.g. user.bsky.social) or email address | 
**AppPassword** | **string** | App password generated from Bluesky Settings &gt; App Passwords | 
**State** | **string** | Required state formatted as {userId}-{profileId}. Get userId from GET /v1/users and profileId from GET /v1/profiles. | 
**RedirectUri** | **string** | Optional URL to redirect to after successful connection | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

