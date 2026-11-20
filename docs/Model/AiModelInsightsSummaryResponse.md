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
**plan_required_fields** | **string[]** | The summary sections left out because they need a higher plan (brand_net_sentiment_by_model and sentiment_market_share below Growth); empty when none is |
**request_id** | **string** |  | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
