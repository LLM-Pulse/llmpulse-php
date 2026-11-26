# AnswerRecord

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **int** |  |
**prompt_id** | **int** |  |
**prompt_text** | **string** |  |
**model** | **string** |  |
**executed_at** | **\DateTime** |  |
**duration_ms** | **float** | Milliseconds our pipeline spent processing the collected answer, rounded to one decimal place |
**no_result** | **bool** | True for a sentinel non-answer (no answer could be collected after all retries, or the model declined to answer, today only Gemini); excluded from platform metrics |
**no_result_reason** | **string** | Present only when no_result is true. declined &#x3D; the model declined to answer and response holds its reply; no_answer &#x3D; no answer could be collected | [optional]
**mentions_count** | **int** | Mentions of your brand in the answer |
**citations_count** | **int** | Citations of your brand in the answer |
**app_url** | **string** | Opens this answer in the app. The link names its project, so it opens there for any user with access to that project |
**response** | **string** | The answer text, cut to 10,000 characters (without query) | [optional]
**response_truncated** | **bool** | Whether response was cut (without query) | [optional]
**snippet** | **string** | The text around the first match (with query) | [optional]
**match_count** | **int** | Matches of query in the answer (with query) | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
