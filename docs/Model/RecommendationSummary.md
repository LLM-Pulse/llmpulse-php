# RecommendationSummary

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **int** |  |
**project_id** | **int** |  |
**recommendation_type** | **string** |  |
**status** | **string** |  |
**error_message** | **string** | Set only when status is failed |
**generated_at** | **\DateTime** | Null until the generation completes |
**created_at** | **\DateTime** |  |
**updated_at** | **\DateTime** |  |
**total_recommendations** | **int** |  |
**high_priority_count** | **int** |  |
**summary** | [**\LLMPulse\Model\RecommendationSummarySummary**](RecommendationSummarySummary.md) |  |
**context** | **object** | Generation context and run diagnostics as stored; empty until the generation completes. Its keys are not a stable contract |

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
