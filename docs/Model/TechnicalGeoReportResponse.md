# TechnicalGeoReportResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **int** |  |
**report_type** | **string** | The report_type requested (agent_readiness for ai_readiness) |
**project_id** | **int** |  |
**batch_id** | **int** | Bundle the report was created in; null for a report created on its own |
**url** | **string** | The page analysed; null for the domain-level types (robots_txt, agent_readiness, llms_txt, ai_visibility) |
**domain** | **string** |  |
**country_code** | **string** | Set only on llms_txt and ai_visibility reports |
**output_language_code** | **string** | ISO 639-1 code an llms_txt report was requested in; null for an llms_txt report written in the website&#39;s own language and for every other type |
**status** | **string** | Depends on report_type. Every type ends completed or failed; ai_visibility can also end insufficient_data |
**result_available** | **bool** | Whether status is completed |
**overall_score** | **float** | Null until the report completes, and always for llms_txt |
**created_at** | **\DateTime** |  |
**updated_at** | **\DateTime** |  |
**result_data** | **array<string,mixed>** | The full result once the report has completed; null before that. Its shape depends on report_type; an llms_txt report returns its files as LlmsTxtTechnicalGeoReport describes |
**error_message** | **string** | Why the report failed, or why an ai_visibility report found insufficient data; null otherwise |
**poll_after_seconds** | **int** | Seconds to wait before polling again while the report runs; null once it has finished |
**app_url** | **string** | Opens this report in the app | [optional]
**request_id** | **string** |  |

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
