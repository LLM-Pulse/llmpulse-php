# IntelligenceTaskSummary

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **int** |  |
**public_id** | **string** |  |
**task_type** | **string** |  |
**title** | **string** |  |
**status** | **string** |  |
**prompt_id** | **int** |  |
**prompt_text** | **string** |  |
**word_count** | **int** |  |
**manually_edited_at** | **\DateTime** | When the content was last edited by hand; null while the output is as generated |
**created_at** | **\DateTime** |  |
**processed_at** | **\DateTime** |  |
**result_version** | **string** | Concurrency token for content edits: send it back as result_version on PATCH /intelligence_tasks/{id} so an edit composed before a regeneration is refused with ERR_STALE_CONTENT (409). It is \&quot;0\&quot; until the task first completes, then changes each time a generation or regeneration replaces result_data, never on a manual edit or a revert. Treat it as opaque text |

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
