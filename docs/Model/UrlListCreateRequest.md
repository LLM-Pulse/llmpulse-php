# UrlListCreateRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**project_id** | **int** |  |
**name** | **string** |  |
**description** | **string** |  | [optional]
**currency** | **string** |  | [optional] [default to 'USD']
**entries** | [**\LLMPulse\Model\UrlListEntryInput[]**](UrlListEntryInput.md) |  | [optional]
**match_type** | **string** | Read every entry without its own match_type as this type. Default detects it from each value. | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
