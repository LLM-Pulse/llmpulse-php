# BingWebmasterSummaryResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**project_id** | **int** |  | [optional]
**site** | **string** | The connected site, as Bing Webmaster Tools names it (e.g. https://example.com/) | [optional]
**sync_status** | **string** | State of the daily sync: pending, syncing, completed, failed or on_hold. on_hold means Bing refused the stored API key or the site is no longer verified: the data already synced still answers but stops updating until the site is reconnected in Preferences &gt; Project Settings &gt; Connections. | [optional]
**last_synced_at** | **\DateTime** | When the site last synced. Null before its first sync, or while history_current is false. | [optional]
**history_current** | **bool** | False right after the site was changed and before its first sync. Until then the response holds no data and data_through is null. | [optional]
**from** | **\DateTime** |  | [optional]
**to** | **\DateTime** |  | [optional]
**data_through** | **\DateTime** | The last day synced for the site. Later days are missing, not zero. | [optional]
**totals** | [**\LLMPulse\Model\BingWebmasterMetrics**](BingWebmasterMetrics.md) |  | [optional]
**request_id** | **string** |  | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
