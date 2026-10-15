# PromptsImportResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**project_id** | **int** |  |
**processed_rows** | **int** | Distinct rows imported or matched to an existing prompt |
**created** | **int** |  |
**duplicates** | **int** | Rows that matched an existing prompt (they still get the row&#39;s tags) |
**tagged** | **int** | New prompt-tag links |
**created_tags** | **int** |  |
**row_errors** | [**\LLMPulse\Model\PromptsImportResponseRowErrorsInner[]**](PromptsImportResponseRowErrorsInner.md) | Rows that were skipped, by their index in rows |
**length_warning** | **string** | Which tracked AI models will skip new prompts that are too long for them |
**prompts_available** | **int** | Prompt slots left on the plan; null when unlimited |
**request_id** | **string** |  |

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
