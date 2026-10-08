# SentimentRecord

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **int** |  |
**prompt_execution_id** | **int** |  |
**prompt_text** | **string** |  |
**model** | **string** |  |
**analysis** | **string** |  |
**score** | **float** | From -1 (very negative) to 1 (very positive) |
**comment** | **string** |  |
**topics** | **string** | Comma-separated topics |
**competitor_id** | **int** | Null for a sentiment about the project&#39;s own brand |
**competitor_name** | **string** | Null for a sentiment about the project&#39;s own brand |
**is_brand_sentiment** | **bool** |  |
**executed_at** | **\DateTime** |  |
**created_at** | **\DateTime** |  |

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
