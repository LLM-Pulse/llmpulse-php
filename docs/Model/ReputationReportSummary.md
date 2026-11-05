# ReputationReportSummary

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **string** | Report id for GET /reputation/reports/{id} |
**status** | **string** |  |
**created_at** | **\DateTime** |  |
**processed_at** | **\DateTime** |  | [optional]
**available_models** | **string[]** | Analyst models that produced data |
**missing_models** | **string[]** | Analyst models with no data yet |
**error_message** | **string** | Why the report failed; null unless status is failed | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
