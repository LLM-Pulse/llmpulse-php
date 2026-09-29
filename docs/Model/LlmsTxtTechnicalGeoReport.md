# LlmsTxtTechnicalGeoReport

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **int** |  | [optional]
**report_type** | **string** | Always llms_txt | [optional]
**project_id** | **int** |  | [optional]
**batch_id** | **int** | Bundle the report was created in; null for a report created on its own | [optional]
**url** | **string** | Always null for llms_txt reports; domain names the website | [optional]
**domain** | **string** |  | [optional]
**country_code** | **string** |  | [optional]
**output_language_code** | **string** | ISO 639-1 code the files were requested in; null when they are written in the website&#39;s own language | [optional]
**status** | **string** |  | [optional]
**result_available** | **bool** |  | [optional]
**overall_score** | **float** | Always null for llms_txt reports | [optional]
**created_at** | **\DateTime** |  | [optional]
**updated_at** | **\DateTime** |  | [optional]
**result_data** | [**\LLMPulse\Model\LlmsTxtTechnicalGeoReportResultData**](LlmsTxtTechnicalGeoReportResultData.md) |  | [optional]
**error_message** | **string** |  | [optional]
**poll_after_seconds** | **int** | Seconds to wait before polling again while the report runs; null once it has finished | [optional]
**app_url** | **string** | Opens this report in the app | [optional]
**request_id** | **string** |  | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
