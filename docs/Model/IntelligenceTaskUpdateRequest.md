# IntelligenceTaskUpdateRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**project_id** | **int** |  |
**edits** | **array<string,string>** | Dotted result_data paths (title, sections.0.content, key_points.2) mapped to their replacement text. Only string fields that already exist are editable; sections cannot be added or removed. |
**result_version** | **string** | Optional. The result_version of the task as last read. When sent, the edit is refused with ERR_STALE_CONTENT (409) and nothing is written if the task was regenerated since. Omitted, null or empty, the edits apply to whatever the task holds now | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
