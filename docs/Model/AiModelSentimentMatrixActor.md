# AiModelSentimentMatrixActor

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**type** | **string** |  | [optional]
**id** | **int** | Project id, or competitor id | [optional]
**competitor_id** | **int** | Null for the project, the competitor id otherwise | [optional]
**name** | **string** |  | [optional]
**domain** | **string** | Bare (scheme-less) domain. Null for the project actor when the project has no URL. | [optional]
**total_sentiments** | **int** | The actor&#39;s sentiment verdicts summed over the models | [optional]
**models** | [**array<string,\LLMPulse\Model\AiModelSentimentCell>**](AiModelSentimentCell.md) | One cell per model, keyed by model | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
