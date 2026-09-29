# TechnicalGeoReportContentUpdateRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**project_id** | **int** |  |
**report_type** | **string** | Only llms_txt reports have editable content |
**content_version** | **string** | result_data.content_version of the report as last read. It changes on every save; a value that no longer matches is refused as stale |
**edits** | [**\LLMPulse\Model\TechnicalGeoReportContentUpdateRequestEdits**](TechnicalGeoReportContentUpdateRequestEdits.md) |  |

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
