# CreateApiKeyRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**name** | **string** | A label to recognize the key, for example the customer it is for |
**scope** | **string** | read (default) only reads data; read_write can also create, change and delete within the key&#39;s projects | [optional] [default to 'read']
**project_ids** | **int[]** | The projects the key is limited to, at least one |

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
