# Late.Model.ApiKey

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Id** | **string** |  | [optional] 
**Name** | **string** |  | [optional] 
**KeyPreview** | **string** |  | [optional] 
**ExpiresAt** | **DateTime** |  | [optional] 
**CreatedAt** | **DateTime** |  | [optional] 
**Key** | **string** | Returned only once, on creation | [optional] 
**Scope** | **string** | &#39;full&#39; grants access to all profiles, &#39;profiles&#39; restricts to specific profiles | [optional] [default to ScopeEnum.Full]
**ProfileIds** | [**List&lt;ApiKeyProfileIdsInner&gt;**](ApiKeyProfileIdsInner.md) | Profiles this key can access (populated with name and color). Only present when scope is &#39;profiles&#39;. | [optional] 
**Permission** | **string** | &#39;read-write&#39; allows all operations, &#39;read&#39; restricts to GET requests only | [optional] [default to PermissionEnum.ReadWrite]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

