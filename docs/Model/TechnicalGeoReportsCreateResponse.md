# TechnicalGeoReportsCreateResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**project_id** | **int** |  |
**url** | **string** | The URL analysed |
**country_code** | **string** | The country used, the project country when none was sent |
**output_language_code** | **string** | ISO 639-1 code the llms.txt files are written in, or auto for the website&#39;s own language |
**batch_id** | **int** | Bundle id, for the batch_id filter of GET /technical_geo_reports; null when no report was created |
**created_reports** | **string[]** | The report_type of every report created |
**report_ids** | **array<string,int>** | The id of each created report, by report_type |
**app_urls** | **array<string,string>** | The link that opens each created report in the app, by report_type |
**failed_reports** | [**\LLMPulse\Model\TechnicalGeoReportsCreateResponseFailedReportsInner[]**](TechnicalGeoReportsCreateResponseFailedReportsInner.md) | Reports that could not be created, with the reasons |
**next_endpoint** | **string** | Path template to poll each created report |
**poll_after_seconds** | **int** | Seconds to wait before the first poll |
**request_id** | **string** |  |

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
