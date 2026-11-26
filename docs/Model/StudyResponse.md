# StudyResponse

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
**brief** | **string** | What the study asks the analyst models; null when none was written |
**subjects** | **string[]** | Names of the subjects it compares |
**dimensions** | **string[]** | Keys of the dimensions it scores, as the dimension filter takes them |
**reports** | [**\LLMPulse\Model\ReputationReportSummary[]**](ReputationReportSummary.md) | The 24 latest reports, newest first |
**request_id** | **string** |  |

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
