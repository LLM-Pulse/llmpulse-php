# AiModelSentimentRow

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**model** | **string** | AI model key, as /dimensions/models lists it | [optional]
**label** | **string** | Display name of the model | [optional]
**color** | **string** | Hex color the app charts the model with | [optional]
**sentiments_count** | **int** | Brand sentiment verdicts in the model&#39;s answers | [optional]
**positive_count** | **int** | Positive and very positive verdicts | [optional]
**negative_count** | **int** | Negative and very negative verdicts | [optional]
**net_sentiment** | **float** | positive_count minus negative_count as a percentage (-100 to 100) of sentiments_count, neutral verdicts counted in the base; null when sentiments_count is 0 | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
