# SovResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**project_id** | **int** |  | [optional]
**periods** | [**\LLMPulse\Model\SovResponsePeriodsInner[]**](SovResponsePeriodsInner.md) | Per-bucket sample size and completeness: mentions is the total the shares were computed on (1-3 mentions produce the 100/50/33.33 low-sample patterns); partial marks buckets still collecting data or clipped by the requested window. | [optional]
**over_time** | [**\LLMPulse\Model\SovResponseOverTimeInner[]**](SovResponseOverTimeInner.md) |  | [optional]
**current** | [**\LLMPulse\Model\SovResponseCurrentInner[]**](SovResponseCurrentInner.md) |  | [optional]
**breakdown** | [**\LLMPulse\Model\SovResponseBreakdownInner[]**](SovResponseBreakdownInner.md) |  | [optional]
**others** | **object[]** |  | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
