# CustomReportDetailResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**project_id** | **int** |  |
**id** | **int** |  |
**name** | **string** |  |
**date_range** | [**\LLMPulse\Model\CustomReportDateRange**](CustomReportDateRange.md) |  |
**schedule** | [**\LLMPulse\Model\CustomReportSchedule**](CustomReportSchedule.md) |  |
**recipients_count** | **int** |  | [optional]
**published** | **bool** |  | [optional]
**public_link_active** | **bool** |  | [optional]
**password_protected** | **bool** |  | [optional]
**portal_only** | **bool** |  | [optional]
**last_sent_at** | **\DateTime** | When the report was last emailed, on its schedule or with Send now | [optional]
**created_at** | **\DateTime** |  | [optional]
**updated_at** | **\DateTime** |  | [optional]
**filters** | [**\LLMPulse\Model\CustomReportFilters**](CustomReportFilters.md) |  |
**compare_previous** | **bool** |  | [optional]
**attach_excel** | **bool** |  | [optional]
**manual_send_available_at** | **\DateTime** | When the 10-minute cooldown after the last manual send ends; null when none is running | [optional]
**generated_at** | **\DateTime** |  |
**blocks** | [**\LLMPulse\Model\CustomReportBlock[]**](CustomReportBlock.md) | The report layout in order |
**widgets** | [**\LLMPulse\Model\CustomReportWidget[]**](CustomReportWidget.md) |  |
**request_id** | **string** |  |

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
