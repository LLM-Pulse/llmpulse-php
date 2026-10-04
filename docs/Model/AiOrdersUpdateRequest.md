# AiOrdersUpdateRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**project_id** | **int** |  |
**platform** | **string** |  |
**currency** | **string** | ISO 4217 code, e.g. EUR |
**from** | **\DateTime** | First day of the window this push replaces |
**to** | **\DateTime** | Last day of the window; at most 400 days after from |
**days** | [**\LLMPulse\Model\AiOrdersUpdateRequestDaysInner[]**](AiOrdersUpdateRequestDaysInner.md) |  |

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
