# AiModelDeclinedAnswersResponseByPromptDataInner

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**answers** | **int** | Finished runs of the model, declined ones included | [optional]
**declined** | **int** | Answers the model declined | [optional]
**decline_rate** | **float** |  | [optional]
**safety_filter** | **int** | Answers declined by the model&#39;s own safety filters | [optional]
**safety_filter_rate** | **float** |  | [optional]
**topic_refusal** | **int** | Answers that declined the topic itself, such as tobacco, gambling or alcohol | [optional]
**topic_refusal_rate** | **float** |  | [optional]
**prompt_id** | **int** |  | [optional]
**prompt_text** | **string** |  | [optional]
**last_declined_at** | **\DateTime** | When the prompt&#39;s latest declined answer of the window was created; null when none was declined | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
