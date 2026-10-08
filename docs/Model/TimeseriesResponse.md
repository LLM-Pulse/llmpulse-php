# TimeseriesResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**project_id** | **int** |  | [optional]
**from** | **\DateTime** |  | [optional]
**to** | **\DateTime** |  | [optional]
**granularity** | **string** | day, week or month | [optional]
**filters** | [**\LLMPulse\Model\MetricsFiltersEcho**](MetricsFiltersEcho.md) |  | [optional]
**series** | **array<string,\LLMPulse\Model\TimeseriesSeries[]>** |  | [optional]
**request_id** | **string** |  | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
