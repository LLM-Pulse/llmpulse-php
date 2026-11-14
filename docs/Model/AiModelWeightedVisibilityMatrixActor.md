# AiModelWeightedVisibilityMatrixActor

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**type** | **string** |  | [optional]
**id** | **int** | Project id, or competitor id | [optional]
**competitor_id** | **int** | Null for the project, the competitor id otherwise | [optional]
**name** | **string** |  | [optional]
**domain** | **string** | Bare (scheme-less) domain. Null for the project actor when the project has no URL. | [optional]
**total_weighted_visibility_score** | **float** | The actor&#39;s AI Visibility Score across the enabled models, its points there divided by the project&#39;s days with answers in them, so actors compare | [optional]
**models** | [**array<string,\LLMPulse\Model\AiModelWeightedVisibilityCell>**](AiModelWeightedVisibilityCell.md) | One cell per model, keyed by model | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
