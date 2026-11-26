# AiTrafficResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**project_id** | **int** |  |
**provider** | **string** | The connected provider: google_analytics, adobe_analytics, adobe_cja, posthog, plausible, matomo or piano |
**from** | **\DateTime** |  |
**to** | **\DateTime** |  |
**granularity** | **string** |  |
**totals** | [**\LLMPulse\Model\AiTrafficResponseTotals**](AiTrafficResponseTotals.md) |  |
**by_source** | [**\LLMPulse\Model\AiTrafficResponseBySourceInner[]**](AiTrafficResponseBySourceInner.md) | One row per AI source with traffic in the window, most sessions first |
**timeseries** | **array<string,array<string,int>>** | Sessions keyed by AI source slug, then by the first day of the period (YYYY-MM-DD); a period without traffic is left out |
**request_id** | **string** |  |

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
