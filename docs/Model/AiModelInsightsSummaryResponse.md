# AiModelInsightsSummaryResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**project_id** | **int** |  | [optional]
**from** | **\DateTime** |  | [optional]
**to** | **\DateTime** |  | [optional]
**filters** | [**\LLMPulse\Model\AiModelInsightsFiltersEcho**](AiModelInsightsFiltersEcho.md) |  | [optional]
**models** | [**\LLMPulse\Model\AiModelInsightsModel[]**](AiModelInsightsModel.md) | The AI models the account has enabled or that answered in the window, in the in-app column order | [optional]
**summary** | [**\LLMPulse\Model\AiModelInsightsSummaryResponseSummary**](AiModelInsightsSummaryResponseSummary.md) |  | [optional]
**request_id** | **string** |  | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
