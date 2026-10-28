# CreateApiKey201Response

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **int** |  |
**name** | **string** |  |
**prefix** | **string** | The visible start of the token, to recognize the key. Never the secret itself. |
**scope** | **string** |  |
**project_scoped** | **bool** | True when the key is limited to project_ids; false for an account-wide key. |
**project_ids** | **int[]** | The projects the key is limited to; empty for an account-wide key. |
**created_at** | **\DateTime** |  |
**last_used_at** | **\DateTime** | Updated at most once a minute. |
**revoked_at** | **\DateTime** |  |
**token** | **string** | The secret to send as Bearer token. Shown only in this response. |
**request_id** | **string** |  | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
