# SummaryResponseAllOfSummaryValueInner

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**actor** | [**\LLMPulse\Model\Actor**](Actor.md) |  | [optional]
**metric** | **string** |  | [optional]
**total** | **float** | Count metrics sum the buckets. Rate, position and sentiment metrics pool the whole window, the number the app shows for the same filters, whatever the granularity; visibility is all mentions over all responses x 100, citation_rate all citations over all responses x 100, a sentiment share all verdicts of that kind over all verdicts x 100, an average position the average of every position recorded in the window. They are never a mean of the bucket values. ai_visibility_score (weighted_visibility) is the window&#39;s points divided by its tracking runs (the days, weeks or months at the account&#39;s tracking frequency with responses under the filters). | [optional]
**aggregation** | **string** | How total combines the buckets. sum for counts; average for rates, positions and sentiment, pooled over the window, and for ai_visibility_score, a per-run score | [optional]
**min** | **float** |  | [optional]
**max** | **float** |  | [optional]
**last** | **float** |  | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
