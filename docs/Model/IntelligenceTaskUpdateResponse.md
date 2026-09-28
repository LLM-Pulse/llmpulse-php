# IntelligenceTaskUpdateResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **int** |  | [optional]
**public_id** | **string** |  | [optional]
**project_id** | **int** |  | [optional]
**task_type** | **string** |  | [optional]
**title** | **string** |  | [optional]
**status** | **string** |  | [optional]
**prompt_id** | **int** |  | [optional]
**prompt_text** | **string** |  | [optional]
**agentic_mode** | **bool** |  | [optional]
**custom_topic** | **string** |  | [optional]
**user_instructions** | **string** |  | [optional]
**output_language_code** | **string** |  | [optional]
**word_count** | **int** |  | [optional]
**result_data** | **object** | The generated content once status is completed; null before that | [optional]
**error_message** | **string** |  | [optional]
**estimated_time** | **string** |  | [optional]
**created_at** | **\DateTime** |  | [optional]
**processed_at** | **\DateTime** |  | [optional]
**manually_edited_at** | **\DateTime** | When the content was last edited by hand; null while the output is as generated | [optional]
**edited_by_user_id** | **int** | User behind the last manual edit; null for an unedited task or an edit made from an embedded portal | [optional]
**request_id** | **string** |  | [optional]
**changed_paths** | **string[]** | Paths whose text actually changed; empty when every value matched the stored text | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
