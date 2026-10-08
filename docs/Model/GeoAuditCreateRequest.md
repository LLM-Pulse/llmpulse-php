# GeoAuditCreateRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**project_id** | **int** |  |
**target** | **string** | The domain (site-wide types) or page URL to audit |
**audit_types** | **string[]** | One or more audit types; each becomes its own audit and starts its first run |
**cadence** | **string** | once (default), weekly or monthly. Weekly and monthly need a type whose checks are tracked and count against the plan limit of recurring audits | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
