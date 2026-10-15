# PromptGenerationResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **string** | The run id; poll GET /prompt_generations/{id} with it (kept for 24 hours) |
**project_id** | **int** |  |
**source** | **string** |  |
**status** | **string** |  |
**params** | [**\LLMPulse\Model\PromptGenerationResponseParams**](PromptGenerationResponseParams.md) |  |
**created_at** | **\DateTime** |  |
**finished_at** | **\DateTime** |  |
**suggestions_count** | **int** |  |
**suggestions** | [**\LLMPulse\Model\SuggestedPrompt[]**](SuggestedPrompt.md) | The suggestions the run saved to the Suggested prompts queue, with their current status |
**error** | [**\LLMPulse\Model\PromptGenerationResponseError**](PromptGenerationResponseError.md) |  |
**request_id** | **string** |  |

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
