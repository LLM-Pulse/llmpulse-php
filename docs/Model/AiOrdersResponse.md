# AiOrdersResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**project_id** | **int** |  |
**platform** | **string** |  |
**currency** | **string** | ISO 4217 code of the most recent stored day; null when the window holds no stored order |
**from** | **\DateTime** |  |
**to** | **\DateTime** |  |
**totals** | [**\LLMPulse\Model\AiOrdersResponseTotals**](AiOrdersResponseTotals.md) |  |
**by_source** | [**\LLMPulse\Model\AiOrdersResponseBySourceInner[]**](AiOrdersResponseBySourceInner.md) | One row per AI assistant, highest revenue first |
**series** | [**\LLMPulse\Model\AiOrdersResponseSeriesInner[]**](AiOrdersResponseSeriesInner.md) | Days that have stored orders, oldest first |
**request_id** | **string** |  |

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
