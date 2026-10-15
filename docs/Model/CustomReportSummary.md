# CustomReportSummary

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **int** |  |
**name** | **string** |  |
**date_range** | [**\LLMPulse\Model\CustomReportDateRange**](CustomReportDateRange.md) |  |
**schedule** | [**\LLMPulse\Model\CustomReportSchedule**](CustomReportSchedule.md) |  |
**recipients_count** | **int** |  |
**published** | **bool** | Whether the shared link is published |
**public_link_active** | **bool** | Whether the shared link opens (published and not made inside a client portal) |
**password_protected** | **bool** |  |
**portal_only** | **bool** | Made inside a client portal, so it cannot be shared or emailed |
**widget_count** | **int** |  |
**widgets** | [**\LLMPulse\Model\CustomReportWidgetRef[]**](CustomReportWidgetRef.md) |  |
**last_sent_at** | **\DateTime** | When the report was last emailed, on its schedule or with Send now | [optional]
**created_at** | **\DateTime** |  |
**updated_at** | **\DateTime** |  |

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
