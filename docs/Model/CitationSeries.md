# CitationSeries

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**granularity** | **string** |  |
**total** | **int** | Equal to total_responses |
**by_model** | **array<string,int>** | Answers per AI model, keyed by model, largest first |
**data** | [**\LLMPulse\Model\AiModelPositionDistributionBrandBucketsInnerDataInner[]**](AiModelPositionDistributionBrandBucketsInnerDataInner.md) | One point per period holding a filtered answer, oldest first; a zero means answers ran and none cited it |

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
