# AnswerDetails

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **int** |  | [optional]
**prompt_id** | **int** |  | [optional]
**prompt_text** | **string** |  | [optional]
**model** | **string** |  | [optional]
**response** | **string** |  | [optional]
**response_truncated** | **bool** |  | [optional]
**executed_at** | **\DateTime** |  | [optional]
**duration_ms** | **float** | Milliseconds, rounded to one decimal place | [optional]
**success** | **bool** | Null while the answer is still pending | [optional]
**fan_out_queries** | **string[]** |  | [optional]
**mentions** | **object[]** |  | [optional]
**citations** | **object[]** |  | [optional]
**competitor_mentions** | **object[]** |  | [optional]
**competitor_citations** | **object[]** |  | [optional]
**sentiments** | **object[]** |  | [optional]
**sources** | **object[]** |  | [optional]
**shopping_products** | **object[]** |  | [optional]
**brand_entities** | **object[]** |  | [optional]
**local_businesses** | **object[]** |  | [optional]
**locale** | [**\LLMPulse\Model\AnswerDetailsLocale**](AnswerDetailsLocale.md) |  | [optional]
**app_url** | **string** | Opens this answer in the app. The link names its project, so it opens there for any user with access to that project | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
