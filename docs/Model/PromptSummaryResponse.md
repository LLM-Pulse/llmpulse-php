# PromptSummaryResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**project_id** | **int** |  | [optional]
**from** | **\DateTime** |  | [optional]
**to** | **\DateTime** |  | [optional]
**filters** | [**\LLMPulse\Model\MetricsFiltersEcho**](MetricsFiltersEcho.md) |  | [optional]
**breakdown** | **string** |  | [optional]
**sort** | **string** |  | [optional]
**sort_dir** | **string** |  | [optional]
**page** | **int** |  | [optional]
**per_page** | **int** |  | [optional]
**total** | **int** |  | [optional]
**data** | [**\LLMPulse\Model\PromptSummaryRow[]**](PromptSummaryRow.md) |  | [optional]
**plan_required_fields** | **string[]** | The row fields left out because they need a higher plan (the sentiment fields below Growth); empty when none is |
**request_id** | **string** |  | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
