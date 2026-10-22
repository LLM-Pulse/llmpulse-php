# SearchConsoleRowsResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**project_id** | **int** |  | [optional]
**property** | [**\LLMPulse\Model\SearchConsoleProperty**](SearchConsoleProperty.md) |  | [optional]
**from** | **\DateTime** |  | [optional]
**to** | **\DateTime** |  | [optional]
**data_through** | **\DateTime** | Latest date Google has published for the property, or for every combined property (it lags 2-3 days). Later days are missing, not zero. | [optional]
**page** | **int** |  | [optional]
**per_page** | **int** |  | [optional]
**total** | **int** | Rows in this window (one Google request, at most 25,000) | [optional]
**sort** | **string** |  | [optional]
**start_row** | **int** | Present when start_row was set | [optional]
**truncated** | **bool** | Present (true) when Google returned 25,000 rows, so more rows exist past this window | [optional]
**dimensions** | **string[]** |  | [optional]
**data** | [**\LLMPulse\Model\SearchConsoleRowsResponseDataInner[]**](SearchConsoleRowsResponseDataInner.md) | One row per combination; only the requested dimensions are present | [optional]
**request_id** | **string** |  | [optional]
**properties** | [**\LLMPulse\Model\SearchConsoleProperty[]**](SearchConsoleProperty.md) | With a list or all in the property parameter, the properties whose data the response holds (instead of property) | [optional]
**excluded_properties** | [**\LLMPulse\Model\SearchConsoleExcludedProperty[]**](SearchConsoleExcludedProperty.md) | With a list or all, selected properties left out because another selected property already counts them | [optional]
**property_errors** | [**\LLMPulse\Model\SearchConsolePropertyError[]**](SearchConsolePropertyError.md) | With a list or all, selected properties Google refused, left out of the figures | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
