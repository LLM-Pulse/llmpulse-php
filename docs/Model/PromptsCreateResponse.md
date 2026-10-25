# PromptsCreateResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**project_id** | **int** |  | [optional]
**created** | **int** |  | [optional]
**skipped** | **int** |  | [optional]
**total_after** | **int** |  | [optional]
**prompts_available** | **int** |  | [optional]
**tracked** | **bool** | Whether scheduled runs include the project the prompts were added to. False when it is paused or beyond the plan&#39;s project limit, so the new prompts do not run until that changes | [optional]
**untracked_reason** | **string** | Why tracked is false: paused or project_limit. Null when tracked | [optional]
**warning** | **string** | What to do when tracked is false. Null when tracked | [optional]
**data** | [**\LLMPulse\Model\PromptsCreateResponseDataInner[]**](PromptsCreateResponseDataInner.md) |  | [optional]
**request_id** | **string** |  | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
