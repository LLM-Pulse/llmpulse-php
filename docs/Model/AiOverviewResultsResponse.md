# AiOverviewResultsResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**project_id** | **int** |  |
**from** | **\DateTime** |  |
**to** | **\DateTime** |  |
**filters** | [**\LLMPulse\Model\AiModelInsightsReportFiltersEcho**](AiModelInsightsReportFiltersEcho.md) |  |
**granularity** | **string** |  |
**summary** | [**\LLMPulse\Model\AiOverviewResultCounts**](AiOverviewResultCounts.md) |  |
**chart** | [**\LLMPulse\Model\AiOverviewResultsResponseChartInner[]**](AiOverviewResultsResponseChartInner.md) | One point per period of the window, oldest first, 0 included |
**by_prompt** | [**\LLMPulse\Model\AiOverviewResultsResponseByPrompt**](AiOverviewResultsResponseByPrompt.md) |  |
**request_id** | **string** |  |

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
