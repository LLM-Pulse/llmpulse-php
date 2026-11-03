# SearchConsoleDecayResponse

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
**dimension** | **string** |  | [optional]
**compared_through** | **\DateTime** | Last day of the requested window that is compared, to or the last day Google has published when that is earlier | [optional]
**previous_from** | **\DateTime** | Start of the window compared against, the same length as from..compared_through and just before it | [optional]
**previous_to** | **\DateTime** |  | [optional]
**min_clicks** | **int** |  | [optional]
**page** | **int** |  | [optional]
**per_page** | **int** |  | [optional]
**total** | **int** | Rows in the report before paging | [optional]
**truncated** | **bool** | Present (true) when Google returned its 25,000-row maximum for a property, so the report covers its top rows only | [optional]
**data** | [**\LLMPulse\Model\SearchConsoleDecayResponseDataInner[]**](SearchConsoleDecayResponseDataInner.md) |  | [optional]
**request_id** | **string** |  | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
