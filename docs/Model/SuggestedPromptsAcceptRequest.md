# SuggestedPromptsAcceptRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**project_id** | **int** |  |
**ids** | **int[]** | Suggestion ids to accept (max 100) |
**tag_ids** | **int[]** | One tag id to put the new prompts in | [optional]
**tag_names** | **string[]** | One tag name (case-insensitive) to put the new prompts in | [optional]
**create_missing** | **bool** | Create the tag named in tag_names when it does not exist | [optional] [default to false]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
