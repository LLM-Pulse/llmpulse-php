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
**no_result** | **bool** | True for a sentinel non-answer (the provider returned nothing after all retries, or the model declined to answer, today only Gemini); excluded from platform metrics | [optional]
**fan_out_queries** | **string[]** |  | [optional]
**mentions** | **object[]** |  | [optional]
**citations** | **object[]** |  | [optional]
**competitor_mentions** | **object[]** |  | [optional]
**competitor_citations** | **object[]** |  | [optional]
**sentiments** | **object[]** | Needs the Growth plan or above; left out below it and named in plan_required_fields | [optional]
**sources** | **object[]** |  | [optional]
**shopping_products** | **object[]** | Needs the Scale plan or above; left out below it and named in plan_required_fields | [optional]
**brand_entities** | **object[]** |  | [optional]
**local_businesses** | **object[]** |  | [optional]
**locale** | [**\LLMPulse\Model\AnswerDetailsLocale**](AnswerDetailsLocale.md) |  | [optional]
**plan_required_fields** | **string[]** | The fields left out of this answer because the account&#39;s plan does not include them (sentiments below Growth, shopping_products below Scale). Always present, empty when nothing is left out |
**app_url** | **string** | Opens this answer in the app. The link names its project, so it opens there for any user with access to that project | [optional]
**request_id** | **string** |  | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
