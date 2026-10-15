# OwnedMediaCitingPromptsResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**project_id** | **int** |  | [optional]
**provider** | **string** |  | [optional]
**from** | **\DateTime** |  | [optional]
**to** | **\DateTime** |  | [optional]
**item** | [**\LLMPulse\Model\OwnedMediaCitedItem**](OwnedMediaCitedItem.md) |  | [optional]
**citation_count** | **int** | Citations of the item in the window | [optional]
**prompt_count** | **int** | Distinct prompts whose answers cited it | [optional]
**page** | **int** |  | [optional]
**per_page** | **int** |  | [optional]
**total** | **int** | Citing answers | [optional]
**data** | [**\LLMPulse\Model\OwnedMediaCitingAnswer[]**](OwnedMediaCitingAnswer.md) |  | [optional]
**request_id** | **string** |  | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
