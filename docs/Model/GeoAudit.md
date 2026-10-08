# GeoAudit

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **string** | Stable audit id | [optional]
**audit_type** | **string** |  | [optional]
**target** | **string** | The audited domain (site-wide types) or page URL, normalized | [optional]
**country_code** | **string** |  | [optional]
**cadence** | **string** |  | [optional]
**status** | **string** |  | [optional]
**paused_reason** | **string** | user, or unreachable when three runs in a row could not reach the site | [optional]
**schedule** | [**\LLMPulse\Model\GeoAuditSchedule**](GeoAuditSchedule.md) |  | [optional]
**next_run_at** | **\DateTime** |  | [optional]
**email_alerts** | **bool** |  | [optional]
**recurring_available** | **bool** | Whether this audit type can run weekly or monthly | [optional]
**checks_tracked** | **bool** | Whether runs of this type produce findings and issues, or a score only | [optional]
**latest_run** | [**\LLMPulse\Model\GeoAuditRun**](GeoAuditRun.md) |  | [optional]
**open_issues** | **int** |  | [optional]
**open_critical_issues** | **int** |  | [optional]
**created_at** | **\DateTime** |  | [optional]
**app_url** | **string** |  | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
