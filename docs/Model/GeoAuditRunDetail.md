# GeoAuditRunDetail

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**sequence** | **int** | Run number within the audit, starting at 1 | [optional]
**status** | **string** |  | [optional]
**trigger** | **string** |  | [optional]
**score** | **float** |  | [optional]
**grade** | **string** |  | [optional]
**score_delta** | **float** | Score change against the previous completed run | [optional]
**comparable_to_previous** | **bool** | False when the checks or the audit settings changed since the previous run, so a diff may reflect that change | [optional]
**new_issues** | **int** |  | [optional]
**fixed_issues** | **int** |  | [optional]
**regressed_issues** | **int** |  | [optional]
**error** | **string** |  | [optional]
**engine_version** | **string** |  | [optional]
**created_at** | **\DateTime** |  | [optional]
**finished_at** | **\DateTime** |  | [optional]
**app_url** | **string** |  | [optional]
**project_id** | **int** |  | [optional]
**metrics** | **array<string,float>** |  | [optional]
**result_data** | **object** | The full report of the run, in the shape of the matching technical GEO report type | [optional]
**request_id** | **string** |  | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
