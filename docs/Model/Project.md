# Project

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **int** |  | [optional]
**name** | **string** | Internal project label (sidebar, settings, admin) | [optional]
**brand_name** | **string** | LLM-facing brand label (used in prompts and customer-facing charts). Null when not set, in which case prompts and charts use &#x60;name&#x60;. | [optional]
**tracked** | **bool** | Whether scheduled runs include this project. False when it is a pitch project, which runs once, when it is paused, or when the plan&#39;s project limit leaves it out (the oldest projects up to the limit run), so its prompts do not run | [optional]
**untracked_reason** | **string** | Why tracked is false: pitch_project, paused or project_limit. Null when tracked | [optional]
**pitch** | **bool** | Whether this is a pitch project, a one-off snapshot that runs its prompts once, takes no project slot and is deleted at pitch_expires_at unless it is converted (PATCH /projects/{id} with pitch false) | [optional]
**pitch_expires_at** | **\DateTime** | When a pitch project is deleted, with its data, unless it is converted first. Null for a tracked project | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
