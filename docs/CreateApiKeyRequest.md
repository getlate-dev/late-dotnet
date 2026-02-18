# Late.Model.CreateApiKeyRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Name** | **string** |  | 
**ExpiresIn** | **int** | Days until expiry | [optional] 
**Scope** | **string** | &#39;full&#39; grants access to all profiles (default), &#39;profiles&#39; restricts to specific profiles | [optional] [default to ScopeEnum.Full]
**ProfileIds** | **List&lt;string&gt;** | Profile IDs this key can access. Required when scope is &#39;profiles&#39;. | [optional] 
**Permission** | **string** | &#39;read-write&#39; allows all operations (default), &#39;read&#39; restricts to GET requests only | [optional] [default to PermissionEnum.ReadWrite]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

