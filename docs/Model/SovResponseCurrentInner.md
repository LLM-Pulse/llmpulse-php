# SovResponseCurrentInner

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**actor** | [**\LLMPulse\Model\Actor**](Actor.md) |  | [optional]
**share** | **float** |  | [optional]
**previous_share** | **float** | The actor&#39;s share in the last complete bucket before the current one; null without complete history. | [optional]
**avg_share** | **float** | Mean share across complete buckets with data (partial buckets excluded); null without complete history. | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
