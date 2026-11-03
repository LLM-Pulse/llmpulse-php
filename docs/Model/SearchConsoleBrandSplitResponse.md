# SearchConsoleBrandSplitResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**project_id** | **int** |  | [optional]
**property** | [**\LLMPulse\Model\SearchConsoleProperty**](SearchConsoleProperty.md) |  | [optional]
**properties** | [**\LLMPulse\Model\SearchConsoleProperty[]**](SearchConsoleProperty.md) | With a list or all in the property parameter, the properties whose data the response holds (instead of property) | [optional]
**excluded_properties** | [**\LLMPulse\Model\SearchConsoleExcludedProperty[]**](SearchConsoleExcludedProperty.md) | With a list or all, selected properties left out because another selected property already counts them | [optional]
**property_errors** | [**\LLMPulse\Model\SearchConsolePropertyError[]**](SearchConsolePropertyError.md) | With a list or all, selected properties Google refused, left out of the figures | [optional]
**from** | **\DateTime** |  | [optional]
**to** | **\DateTime** |  | [optional]
**data_through** | **\DateTime** | Latest date Google has published for the property, or for every combined property (it lags 2-3 days). Later days are missing, not zero. | [optional]
**brand_terms** | **string[]** | The project&#39;s brand name, matching names, app names and domain, lowercased, each matched as a whole word | [optional]
**totals** | [**\LLMPulse\Model\SearchConsoleMetrics**](SearchConsoleMetrics.md) |  | [optional]
**branded** | [**\LLMPulse\Model\SearchConsoleMetrics**](SearchConsoleMetrics.md) |  | [optional]
**non_branded** | [**\LLMPulse\Model\SearchConsoleMetrics**](SearchConsoleMetrics.md) |  | [optional]
**unclassified** | [**\LLMPulse\Model\SearchConsoleBrandSplitResponseUnclassified**](SearchConsoleBrandSplitResponseUnclassified.md) |  | [optional]
**request_id** | **string** |  | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
