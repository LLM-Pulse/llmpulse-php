# SearchConsoleSummaryResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**project_id** | **int** |  | [optional]
**property** | [**\LLMPulse\Model\SearchConsoleProperty**](SearchConsoleProperty.md) |  | [optional]
**from** | **\DateTime** |  | [optional]
**to** | **\DateTime** |  | [optional]
**data_through** | **\DateTime** | Latest date Google has published for the property, or for every combined property (it lags 2-3 days). Later days are missing, not zero. | [optional]
**totals** | [**\LLMPulse\Model\SearchConsoleMetrics**](SearchConsoleMetrics.md) |  | [optional]
**dimension** | **string** | Present when a breakdown was requested | [optional]
**breakdown** | [**\LLMPulse\Model\SearchConsoleSummaryResponseBreakdownInner[]**](SearchConsoleSummaryResponseBreakdownInner.md) | Present when a breakdown was requested, sorted by impressions descending | [optional]
**breakdown_truncated** | **bool** | Present (true) when limit or Google&#39;s 25,000-row maximum left breakdown rows out, so they add up to less than totals | [optional]
**request_id** | **string** |  | [optional]
**properties** | [**\LLMPulse\Model\SearchConsoleProperty[]**](SearchConsoleProperty.md) | With a list or all in the property parameter, the properties whose data the response holds (instead of property) | [optional]
**excluded_properties** | [**\LLMPulse\Model\SearchConsoleExcludedProperty[]**](SearchConsoleExcludedProperty.md) | With a list or all, selected properties left out because another selected property already counts them | [optional]
**property_errors** | [**\LLMPulse\Model\SearchConsolePropertyError[]**](SearchConsolePropertyError.md) | With a list or all, selected properties Google refused, left out of the figures | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
