# LLMPulse\AnswersApi

Raw AI responses with mentions, citations, sentiments, sources, shopping products, brand entities and local businesses

All URIs are relative to https://api.llmpulse.ai/api/v1, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**getAnswer()**](AnswersApi.md#getAnswer) | **GET** /answers/{id} | Get one AI response |
| [**listAnswers()**](AnswersApi.md#listAnswers) | **GET** /answers | List AI responses |


## `getAnswer()`

```php
getAnswer($project_id, $id, $include_source_page_details): \LLMPulse\Model\AnswerDetails
```

Get one AI response

Full answer with mentions, citations, sentiments, sources, shopping_products, brand_entities, fan_out_queries. Pass `include_source_page_details=true` to nest page-cache metadata under each source.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: BearerAuth
$config = LLMPulse\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new LLMPulse\Api\AnswersApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$project_id = 56; // int | Project ID
$id = 56; // int
$include_source_page_details = false; // bool

try {
    $result = $apiInstance->getAnswer($project_id, $id, $include_source_page_details);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AnswersApi->getAnswer: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **project_id** | **int**| Project ID | |
| **id** | **int**|  | |
| **include_source_page_details** | **bool**|  | [optional] [default to false] |

### Return type

[**\LLMPulse\Model\AnswerDetails**](../Model/AnswerDetails.md)

### Authorization

[BearerAuth](../../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `listAnswers()`

```php
listAnswers($project_id, $model, $collection_id, $country_code, $language_code, $prompt, $mention_filter, $citation_filter, $competitors, $from, $to, $page, $per_page, $query)
```

List AI responses

Successful prompt-execution responses with truncated content (max 10,000 chars). Pass `query` for case-insensitive full-text search inside response texts: `total` becomes the exact count of matching responses and each item returns `snippet` + `match_count` instead of `response`/`response_truncated`.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: BearerAuth
$config = LLMPulse\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new LLMPulse\Api\AnswersApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$project_id = 56; // int | Project ID
$model = 'model_example'; // string | Filter by AI model. Models the API key's user has not enabled are silently dropped.
$collection_id = 56; // int
$country_code = 'country_code_example'; // string | ISO country code (e.g. US, GB, DE)
$language_code = 'language_code_example'; // string | ISO language code (e.g. en, es, de)
$prompt = 56; // int | Filter by prompt ID
$mention_filter = 'mention_filter_example'; // string | Filter by which brands are mentioned, as a two-axis matrix (your brand x competitors): mentions_you / not_mentions_you, mentions_competitor / not_mentions_competitor, and the four combined cells you_and_competitor, competitor_not_you (a rival wins and you are absent), you_not_competitor, no_brands (no tracked brand appears, i.e. open space). Combine with 'competitors' to narrow the competitor side to specific rivals; on a negative cell that reads 'none of these'. On /dimensions/sources it applies to the crawled content of each cited page instead of the answer text. The legacy value 'competitors_only' is still accepted as an alias of competitor_not_you.
$citation_filter = 'citation_filter_example'; // string | Same two-axis matrix applied to the domains cited in the answer instead of the brands named in it. Independent of mention_filter; pass both to intersect them (e.g. mentions_you + not_cites_you finds answers that talk about you without linking to you).
$competitors = 'competitors_example'; // string | Comma-separated competitor IDs (unknown IDs return ERR_INVALID_PARAM)
$from = new \DateTime('2013-10-20T19:20:30+01:00'); // \DateTime
$to = new \DateTime('2013-10-20T19:20:30+01:00'); // \DateTime
$page = 1; // int
$per_page = 20; // int
$query = 'query_example'; // string | Case-insensitive full-text search inside AI response texts. Switches items to snippet + match_count mode.

try {
    $apiInstance->listAnswers($project_id, $model, $collection_id, $country_code, $language_code, $prompt, $mention_filter, $citation_filter, $competitors, $from, $to, $page, $per_page, $query);
} catch (Exception $e) {
    echo 'Exception when calling AnswersApi->listAnswers: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **project_id** | **int**| Project ID | |
| **model** | **string**| Filter by AI model. Models the API key&#39;s user has not enabled are silently dropped. | [optional] |
| **collection_id** | **int**|  | [optional] |
| **country_code** | **string**| ISO country code (e.g. US, GB, DE) | [optional] |
| **language_code** | **string**| ISO language code (e.g. en, es, de) | [optional] |
| **prompt** | **int**| Filter by prompt ID | [optional] |
| **mention_filter** | **string**| Filter by which brands are mentioned, as a two-axis matrix (your brand x competitors): mentions_you / not_mentions_you, mentions_competitor / not_mentions_competitor, and the four combined cells you_and_competitor, competitor_not_you (a rival wins and you are absent), you_not_competitor, no_brands (no tracked brand appears, i.e. open space). Combine with &#39;competitors&#39; to narrow the competitor side to specific rivals; on a negative cell that reads &#39;none of these&#39;. On /dimensions/sources it applies to the crawled content of each cited page instead of the answer text. The legacy value &#39;competitors_only&#39; is still accepted as an alias of competitor_not_you. | [optional] |
| **citation_filter** | **string**| Same two-axis matrix applied to the domains cited in the answer instead of the brands named in it. Independent of mention_filter; pass both to intersect them (e.g. mentions_you + not_cites_you finds answers that talk about you without linking to you). | [optional] |
| **competitors** | **string**| Comma-separated competitor IDs (unknown IDs return ERR_INVALID_PARAM) | [optional] |
| **from** | **\DateTime**|  | [optional] |
| **to** | **\DateTime**|  | [optional] |
| **page** | **int**|  | [optional] [default to 1] |
| **per_page** | **int**|  | [optional] [default to 20] |
| **query** | **string**| Case-insensitive full-text search inside AI response texts. Switches items to snippet + match_count mode. | [optional] |

### Return type

void (empty response body)

### Authorization

[BearerAuth](../../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
