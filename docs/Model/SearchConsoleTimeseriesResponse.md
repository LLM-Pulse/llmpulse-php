# SearchConsoleTimeseriesResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**project_id** | **int** |  | [optional]
**property** | [**\LLMPulse\Model\SearchConsoleProperty**](SearchConsoleProperty.md) |  | [optional]
**from** | **\DateTime** |  | [optional]
**to** | **\DateTime** |  | [optional]
**data_through** | **\DateTime** | Latest date Google has published for the property (it lags 2-3 days). Later days are missing, not zero. | [optional]
**granularity** | **string** |  | [optional]
**data** | [**\LLMPulse\Model\SearchConsoleTimeseriesResponseDataInner[]**](SearchConsoleTimeseriesResponseDataInner.md) |  | [optional]
**request_id** | **string** |  | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
