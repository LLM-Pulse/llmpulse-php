# CitedUrlOccurrencesResponseAllOfData

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**source_id** | **int** |  |
**answer_id** | **int** |  |
**prompt_execution_id** | **int** | Same as answer_id |
**prompt_id** | **int** |  |
**prompt_text** | **string** |  |
**model** | **string** |  |
**executed_at** | **\DateTime** |  |
**citation_position** | **int** | Rank of the citation in the answer; 0 for a background source reference |
**url** | **string** | Normalized cited URL |
**domain** | **string** |  |
**source_type** | **string** | owned, competitor or third_party |
**response_excerpt** | **string** | The first 600 characters of the answer |
**response_truncated** | **bool** |  |
**fan_out_queries** | **string[]** | Sub-queries the model issued while answering; null when the model reports none |

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
