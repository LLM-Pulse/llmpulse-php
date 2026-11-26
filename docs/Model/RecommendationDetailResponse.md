# RecommendationDetailResponse

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
**summary** | [**\LLMPulse\Model\RecommendationDetailResponseSummary**](RecommendationDetailResponseSummary.md) |  |
**context** | **object** | Generation context and run diagnostics as stored; empty until the generation completes. Its keys are not a stable contract |
**report_data** | **array<string,mixed>** | The stored run, including the evidence indices (prompts_index, citations_index, own_content_index and others) that the source_refs codes of the items point to. Its keys are not a stable contract |
**item_counts** | [**\LLMPulse\Model\RecommendationDetailResponseItemCounts**](RecommendationDetailResponseItemCounts.md) |  |
**items** | [**\LLMPulse\Model\RecommendationItem[]**](RecommendationItem.md) |  |
**request_id** | **string** |  |

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
