# PromptSummaryRow

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**prompt_id** | **int** |  | [optional]
**prompt_text** | **string** |  | [optional]
**model** | **string** | Only present when breakdown&#x3D;model | [optional]
**responses** | **int** |  | [optional]
**mentions** | **int** |  | [optional]
**citations** | **int** |  | [optional]
**visibility** | **float** |  | [optional]
**mention_rate** | **float** |  | [optional]
**citation_rate** | **float** |  | [optional]
**avg_mention_position** | **float** |  | [optional]
**avg_position** | **float** |  | [optional]
**app_url** | **string** | Opens this prompt in the app. The link names its project, so it opens there for any user with access to that project | [optional]
**country_code** | **string** | Country of the prompt, as in /dimensions/prompts | [optional]
**language_code** | **string** | Language of the prompt, as in /dimensions/prompts | [optional]
**prompt_type** | **string** | Search intent: informational, navigational, commercial or transactional. Null until the prompt is classified | [optional]
**brand_kind** | **string** | Brand focus: brand, brand_other or non_brand. Null until the prompt is classified | [optional]
**tags** | [**\LLMPulse\Model\TagRef[]**](TagRef.md) | Every tag the prompt belongs to | [optional]
**sentiment_responses** | **int** | Responses in the window with a sentiment verdict for the brand, the base of the sentiment percentages (deduplicated like the sentiment timeseries) | [optional]
**sentiment_very_positive** | **float** | Percentage (0-100) of sentiment_responses whose brand verdict is very positive; null when sentiment_responses is 0 | [optional]
**sentiment_positive** | **float** | Percentage (0-100) of sentiment_responses whose brand verdict is positive; null when sentiment_responses is 0 | [optional]
**sentiment_neutral** | **float** | Percentage (0-100) of sentiment_responses whose brand verdict is neutral; null when sentiment_responses is 0 | [optional]
**sentiment_negative** | **float** | Percentage (0-100) of sentiment_responses whose brand verdict is negative; null when sentiment_responses is 0 | [optional]
**sentiment_very_negative** | **float** | Percentage (0-100) of sentiment_responses whose brand verdict is very negative; null when sentiment_responses is 0 | [optional]
**net_sentiment** | **float** | Positive minus negative percentages (-100 to 100), neutral counted in the base; null when sentiment_responses is 0 | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
