# AiModelDeclinedAnswersResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**project_id** | **int** |  |
**from** | **\DateTime** | Start of the tracking period holding the first day asked for |
**to** | **\DateTime** |  |
**model** | **string** | The model the counts are for |
**cadence** | **string** | The account&#39;s current tracking cadence: daily, weekly or monthly. Chart periods before a switch from weekly to daily stay weekly. |
**filters** | [**\LLMPulse\Model\AiModelDeclinedAnswersResponseFilters**](AiModelDeclinedAnswersResponseFilters.md) |  | [optional]
**summary** | [**\LLMPulse\Model\AiModelDeclinedAnswersResponseSummary**](AiModelDeclinedAnswersResponseSummary.md) |  |
**chart** | [**\LLMPulse\Model\AiModelDeclinedAnswersResponseChartInner[]**](AiModelDeclinedAnswersResponseChartInner.md) | One point per tracking period holding an answer, oldest first. A period without answers has no point; a period with answers and no declines is a real 0. |
**by_prompt** | [**\LLMPulse\Model\AiModelDeclinedAnswersResponseByPrompt**](AiModelDeclinedAnswersResponseByPrompt.md) |  |
**request_id** | **string** |  | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
