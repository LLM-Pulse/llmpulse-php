# StudySummary

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **int** |  |
**title** | **string** |  |
**study_type** | **string** | brand_set, sector, geo, topic or custom |
**cadence** | **string** | one_shot or monthly |
**status** | **string** | active or archived |
**project_id** | **int** | The project the study is attached to; null for an account-level study |
**subjects_count** | **int** |  |
**ai_models** | **string[]** | Analyst models the study runs on |
**output_language_code** | **string** | ISO 639-1 code of the language the reports are written in |
**created_at** | **\DateTime** |  |
**last_report_at** | **\DateTime** | When the latest report started; null before the first one |

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
