# Late.Model.GetPendingOAuthData200Response

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Platform** | **string** | The platform (e.g., \&quot;linkedin\&quot;) | [optional] 
**ProfileId** | **string** | The Late profile ID | [optional] 
**TempToken** | **string** | Temporary access token for the platform | [optional] 
**RefreshToken** | **string** | Refresh token (if available) | [optional] 
**ExpiresIn** | **decimal** | Token expiry in seconds | [optional] 
**UserProfile** | **Object** | User profile data (id, username, displayName, profilePicture) | [optional] 
**SelectionType** | **string** | Type of selection data | [optional] 
**Organizations** | [**List&lt;GetPendingOAuthData200ResponseOrganizationsInner&gt;**](GetPendingOAuthData200ResponseOrganizationsInner.md) | LinkedIn organizations (when selectionType is \&quot;organizations\&quot;) | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

