# PeecExportImportResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**project_id** | **int** |  |
**import_id** | **int** |  |
**status** | **string** | The import was accepted and finishes in the background |
**prompts** | **int** | Distinct prompts of the file, per country and language; each becomes a tracked prompt of the project |
**new_prompts** | **int** | The prompts the project does not hold yet, counted against the plan |
**planned_answers** | **int** | Weekly answers the import files (prompts x tracked AI models x weeks) |
**models** | **array<string,string>** | Each AI model name of the file that is imported, with the tracked AI model its answers are filed under |
**skipped_models** | **string[]** | AI model names of the file whose answers are skipped, because the account does not track them |
**detected_brands** | **string[]** | Brand names the export&#39;s mentions column lists (up to 50), none of them created as competitors |
**app_url** | **string** | Opens the project&#39;s prompts in the app |
**request_id** | **string** |  |

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
