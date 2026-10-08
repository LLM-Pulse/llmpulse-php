# MetricsFiltersEcho

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**metrics** | **string[]** | Requested metrics after alias resolution (mention_rate is echoed as visibility) | [optional]
**granularity** | **string** | day, week or month | [optional]
**model** | **string** | The model filter, or null when absent or not enabled for the account | [optional]
**collection_id** | **string** | The collection_id parameter as sent (one id or a comma-separated list) | [optional]
**collection_ids** | **int[]** |  | [optional]
**domains** | **string[]** |  | [optional]
**country_code** | **string** | Comma-separated country codes | [optional]
**language_code** | **string** | Comma-separated language codes | [optional]
**prompt** | **int** | The prompt id filter | [optional]
**prompt_type** | **string** | Comma-separated prompt types | [optional]
**brand_kind** | **string** |  | [optional]
**competitors** | **int[]** | Competitor ids from the competitors parameter; empty when it was not given | [optional]
**include_project** | **bool** |  | [optional]
**query** | **string** | Only present when a query filter was given | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
