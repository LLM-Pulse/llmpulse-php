# SummaryResponseAllOfSummaryValueInner

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**actor** | [**\LLMPulse\Model\Actor**](Actor.md) |  | [optional]
**metric** | **string** |  | [optional]
**total** | **float** | Count metrics sum the buckets; rate, position and sentiment metrics average them. ai_visibility_score (weighted_visibility) is the window&#39;s points divided by its data days (the days with responses under the filters), the number the app shows, whatever the granularity. | [optional]
**aggregation** | **string** | How total combines the buckets (average for ai_visibility_score, a per-data-day score) | [optional]
**min** | **float** |  | [optional]
**max** | **float** |  | [optional]
**last** | **float** |  | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
