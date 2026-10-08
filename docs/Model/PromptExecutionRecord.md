# PromptExecutionRecord

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **int** |  |
**prompt_id** | **int** |  |
**executed_at** | **\DateTime** | Null while the answer is still pending |
**duration_ms** | **float** |  |
**success** | **bool** | Null while the answer is still pending |
**model** | **string** |  |
**fan_out_queries** | **string[]** | Sub-queries the model issued while answering; null when the model reports none |
**has_mention** | **bool** |  |
**has_citation** | **bool** |  |
**mentions_count** | **int** | 1 when the answer mentions the brand, otherwise 0 |
**citations_count** | **int** | 1 when the answer cites the brand, otherwise 0 |
**app_url** | **string** | Opens this answer in the app. The link names its project, so it opens there for any user with access to that project |

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
