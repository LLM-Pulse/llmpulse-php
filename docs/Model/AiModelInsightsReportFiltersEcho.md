# AiModelInsightsReportFiltersEcho

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**from** | **\DateTime** |  |
**to** | **\DateTime** |  |
**granularity** | **string** |  |
**country_code** | **string** | Comma-separated country codes | [optional]
**language_code** | **string** | Comma-separated language codes | [optional]
**collection_id** | **string** | Comma-separated collection ids | [optional]
**prompt_type** | **string** | Comma-separated prompt types | [optional]
**brand_kind** | **string** |  | [optional]
**model** | **string** | The model filter; always ai_overview on the AI Overview report | [optional]
**competitors** | **int[]** | Competitor ids from the competitors parameter; empty when it was not given |
**brand1** | **string** | Position distribution only. The id, as a string, of the competitor compared as the first brand; left out for the project brand | [optional]
**brand2** | **string** | Position distribution only. The id, as a string, of the competitor compared as the second brand, by default the competitor with the most mentions; left out when the project has none to compare | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
