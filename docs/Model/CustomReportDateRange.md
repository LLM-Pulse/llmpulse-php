# CustomReportDateRange

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**type** | **string** | rolling (the last range_days days), previous_month (the previous calendar month), previous_3_months (the 3 calendar months before the current one) or custom (fixed dates, custom_from to custom_to) |
**range_days** | **int** | Length of a rolling window; null for the other types |
**custom_from** | **\DateTime** | First day chosen for a custom range; null for the other types |
**custom_to** | **\DateTime** | Last day chosen for a custom range, which can be after today; null for the other types |
**from** | **\DateTime** | First day of the window as of now (detail only) | [optional]
**to** | **\DateTime** | Last day of the window as of now (detail only); a custom range stops at today | [optional]
**label** | **string** | The window as the report shows it (detail only) | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
