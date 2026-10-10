# WebAnalyticsQueryResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**project_id** | **int** |  | [optional]
**provider** | **string** |  | [optional]
**property** | **string** |  | [optional]
**columns** | [**\LLMPulse\Model\WebAnalyticsQueryResponseColumnsInner[]**](WebAnalyticsQueryResponseColumnsInner.md) |  | [optional]
**rows** | **mixed[][]** | One array per row, values in column order: strings, numbers or null. | [optional]
**row_count** | **int** | Rows in this response (at most 5,000). | [optional]
**total_rows** | **int** | Rows the provider has for the query, when it reports it. | [optional]
**truncated** | **bool** | True when the provider has more rows than returned; page with its own offset or page field. | [optional]
**totals** | **array<string,mixed>** | Metric totals by metric name, when the query asked for them. | [optional]
**notes** | **string[]** | Provider caveats: sampling, thresholds, more rows available. | [optional]
**meta** | **array<string,mixed>** | Provider metadata such as GA4 time zone, currency and remaining property quota. | [optional]
**fetched_at** | **\DateTime** | When the provider answered. | [optional]
**cached** | **bool** | True when the answer came from the 10-minute cache instead of the provider. | [optional]
**query** | **array<string,mixed>** | The request as sent to the provider, with the connected property forced and limits applied. | [optional]
**request_id** | **string** |  | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
