# CustomReportDateRange

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**type** | **string** | rolling (the last range_days days) or previous_month (the previous calendar month) |
**range_days** | **int** | Length of a rolling window; null for previous_month |
**from** | **\DateTime** | First day of the window as of now (detail only) | [optional]
**to** | **\DateTime** | Last day of the window as of now (detail only) | [optional]
**label** | **string** | The window as the report shows it (detail only) | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
