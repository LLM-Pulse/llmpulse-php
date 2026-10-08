# GeoAuditUpdateRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**project_id** | **int** |  | [optional]
**cadence** | **string** |  | [optional]
**schedule_day** | **int** | Weekly: 0 (Sunday) to 6. Monthly: 1 to 28. | [optional]
**schedule_hour** | **int** | Hour of the day, 0 to 23, in the audit time zone | [optional]
**status** | **string** | paused stops scheduled runs, active resumes them, archived is the same as DELETE | [optional]
**email_alerts** | **bool** |  | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
