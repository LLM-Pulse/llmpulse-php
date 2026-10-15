# LLMPulse\SentimentsApi

Sentiment records with their comments, topics and scores, plus the category catalog used to label them.

All URIs are relative to https://api.llmpulse.ai/api/v1, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**getSentimentTags()**](SentimentsApi.md#getSentimentTags) | **GET** /reports/sentiment/tags | Sentiment by tag (Growth plan or above) |
| [**getSentimentTopics()**](SentimentsApi.md#getSentimentTopics) | **GET** /reports/sentiment/topics | Sentiment by topic (Growth plan or above) |
| [**listSentimentCategories()**](SentimentsApi.md#listSentimentCategories) | **GET** /dimensions/sentiments | List sentiment categories (Growth plan or above) |
| [**listSentimentRecords()**](SentimentsApi.md#listSentimentRecords) | **GET** /sentiments | List sentiment records (Growth plan or above) |


## `getSentimentTags()`

```php
getSentimentTags($project_id, $range, $from, $to, $model, $collection_id, $country_code, $language_code, $brand_kind, $analysis, $topic, $query, $brand, $sort, $sort_dir, $page, $per_page, $output): \LLMPulse\Model\SentimentTagsResponse
```

Sentiment by tag (Growth plan or above)

One row per tag of the project with at least one analyzed mention, with the positive (very positive included), neutral and negative counts, their shares on a 0-100 scale and the net sentiment score. A mention counts once for every tag its prompt carries, as on the Sentiment page. Same filters as GET /reports/sentiment/topics. Requires the Growth plan; lower tiers receive ERR_PLAN_REQUIRED.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: BearerAuth
$config = LLMPulse\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new LLMPulse\Api\SentimentsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$project_id = 56; // int | Project ID
$range = 56; // int | Number of days to look back, today included (default 28, like the Sentiment page). Ignored when from or to is given.
$from = new \DateTime('2013-10-20T19:20:30+01:00'); // \DateTime
$to = new \DateTime('2013-10-20T19:20:30+01:00'); // \DateTime | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier.
$model = 'model_example'; // string | Filter by one AI model. It must be a model enabled for the API key's user: an unknown value, or a model the user has not enabled, returns 422 ERR_INVALID_PARAM with the valid values in the message.
$collection_id = 12,34; // string | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize.
$country_code = 'country_code_example'; // string | One ISO country code or a comma-separated list (e.g. US,GB,DE)
$language_code = 'language_code_example'; // string | One ISO language code or a comma-separated list (e.g. en,es,de)
$brand_kind = 'brand_kind_example'; // string | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default.
$analysis = 'analysis_example'; // string | One sentiment level or a comma-separated list: very_positive, positive, neutral, negative, very_negative
$topic = 'topic_example'; // string | Only sentiments tagged with this topic (case-insensitive)
$query = 'query_example'; // string | Only sentiments whose answer or prompt text contains this text
$brand = 'brand_example'; // string | Whose sentiment to count. Empty or omitted for your own brand, all for every brand, or a competitor id (an unknown id returns ERR_INVALID_PARAM).
$sort = 'mentions'; // string | Sort column: mentions, name (the topic or tag), positive, negative or neutral (their shares) or net_score. Ties sort by name.
$sort_dir = 'desc'; // string
$page = 1; // int
$per_page = 20; // int
$output = 'output_example'; // string | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.

try {
    $result = $apiInstance->getSentimentTags($project_id, $range, $from, $to, $model, $collection_id, $country_code, $language_code, $brand_kind, $analysis, $topic, $query, $brand, $sort, $sort_dir, $page, $per_page, $output);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling SentimentsApi->getSentimentTags: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **project_id** | **int**| Project ID | |
| **range** | **int**| Number of days to look back, today included (default 28, like the Sentiment page). Ignored when from or to is given. | [optional] |
| **from** | **\DateTime**|  | [optional] |
| **to** | **\DateTime**| End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. | [optional] |
| **model** | **string**| Filter by one AI model. It must be a model enabled for the API key&#39;s user: an unknown value, or a model the user has not enabled, returns 422 ERR_INVALID_PARAM with the valid values in the message. | [optional] |
| **collection_id** | **string**| One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize. | [optional] |
| **country_code** | **string**| One ISO country code or a comma-separated list (e.g. US,GB,DE) | [optional] |
| **language_code** | **string**| One ISO language code or a comma-separated list (e.g. en,es,de) | [optional] |
| **brand_kind** | **string**| Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. | [optional] |
| **analysis** | **string**| One sentiment level or a comma-separated list: very_positive, positive, neutral, negative, very_negative | [optional] |
| **topic** | **string**| Only sentiments tagged with this topic (case-insensitive) | [optional] |
| **query** | **string**| Only sentiments whose answer or prompt text contains this text | [optional] |
| **brand** | **string**| Whose sentiment to count. Empty or omitted for your own brand, all for every brand, or a competitor id (an unknown id returns ERR_INVALID_PARAM). | [optional] |
| **sort** | **string**| Sort column: mentions, name (the topic or tag), positive, negative or neutral (their shares) or net_score. Ties sort by name. | [optional] [default to &#39;mentions&#39;] |
| **sort_dir** | **string**|  | [optional] [default to &#39;desc&#39;] |
| **page** | **int**|  | [optional] [default to 1] |
| **per_page** | **int**|  | [optional] [default to 20] |
| **output** | **string**| Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] |

### Return type

[**\LLMPulse\Model\SentimentTagsResponse**](../Model/SentimentTagsResponse.md)

### Authorization

[BearerAuth](../../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getSentimentTopics()`

```php
getSentimentTopics($project_id, $range, $from, $to, $model, $collection_id, $country_code, $language_code, $brand_kind, $analysis, $topic, $query, $brand, $sort, $sort_dir, $page, $per_page, $output): \LLMPulse\Model\SentimentTopicsResponse
```

Sentiment by topic (Growth plan or above)

One row per topic AI answers associate with the brand (topics are matched case-insensitively), with its analyzed mentions, the positive (very positive included), neutral and negative counts, their shares on a 0-100 scale and the net sentiment score ((positive - negative) / mentions x 100). The same rows and filters as the Topics tab of the Sentiment page: the window defaults to the last 28 days, `brand` empty counts your own brand, `all` every brand and a competitor id that competitor. Requires the Growth plan; lower tiers receive ERR_PLAN_REQUIRED.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: BearerAuth
$config = LLMPulse\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new LLMPulse\Api\SentimentsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$project_id = 56; // int | Project ID
$range = 56; // int | Number of days to look back, today included (default 28, like the Sentiment page). Ignored when from or to is given.
$from = new \DateTime('2013-10-20T19:20:30+01:00'); // \DateTime
$to = new \DateTime('2013-10-20T19:20:30+01:00'); // \DateTime | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier.
$model = 'model_example'; // string | Filter by one AI model. It must be a model enabled for the API key's user: an unknown value, or a model the user has not enabled, returns 422 ERR_INVALID_PARAM with the valid values in the message.
$collection_id = 12,34; // string | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize.
$country_code = 'country_code_example'; // string | One ISO country code or a comma-separated list (e.g. US,GB,DE)
$language_code = 'language_code_example'; // string | One ISO language code or a comma-separated list (e.g. en,es,de)
$brand_kind = 'brand_kind_example'; // string | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default.
$analysis = 'analysis_example'; // string | One sentiment level or a comma-separated list: very_positive, positive, neutral, negative, very_negative
$topic = 'topic_example'; // string | Only sentiments tagged with this topic (case-insensitive)
$query = 'query_example'; // string | Only sentiments whose answer or prompt text contains this text
$brand = 'brand_example'; // string | Whose sentiment to count. Empty or omitted for your own brand, all for every brand, or a competitor id (an unknown id returns ERR_INVALID_PARAM).
$sort = 'mentions'; // string | Sort column: mentions, name (the topic or tag), positive, negative or neutral (their shares) or net_score. Ties sort by name.
$sort_dir = 'desc'; // string
$page = 1; // int
$per_page = 20; // int
$output = 'output_example'; // string | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.

try {
    $result = $apiInstance->getSentimentTopics($project_id, $range, $from, $to, $model, $collection_id, $country_code, $language_code, $brand_kind, $analysis, $topic, $query, $brand, $sort, $sort_dir, $page, $per_page, $output);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling SentimentsApi->getSentimentTopics: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **project_id** | **int**| Project ID | |
| **range** | **int**| Number of days to look back, today included (default 28, like the Sentiment page). Ignored when from or to is given. | [optional] |
| **from** | **\DateTime**|  | [optional] |
| **to** | **\DateTime**| End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. | [optional] |
| **model** | **string**| Filter by one AI model. It must be a model enabled for the API key&#39;s user: an unknown value, or a model the user has not enabled, returns 422 ERR_INVALID_PARAM with the valid values in the message. | [optional] |
| **collection_id** | **string**| One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize. | [optional] |
| **country_code** | **string**| One ISO country code or a comma-separated list (e.g. US,GB,DE) | [optional] |
| **language_code** | **string**| One ISO language code or a comma-separated list (e.g. en,es,de) | [optional] |
| **brand_kind** | **string**| Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. | [optional] |
| **analysis** | **string**| One sentiment level or a comma-separated list: very_positive, positive, neutral, negative, very_negative | [optional] |
| **topic** | **string**| Only sentiments tagged with this topic (case-insensitive) | [optional] |
| **query** | **string**| Only sentiments whose answer or prompt text contains this text | [optional] |
| **brand** | **string**| Whose sentiment to count. Empty or omitted for your own brand, all for every brand, or a competitor id (an unknown id returns ERR_INVALID_PARAM). | [optional] |
| **sort** | **string**| Sort column: mentions, name (the topic or tag), positive, negative or neutral (their shares) or net_score. Ties sort by name. | [optional] [default to &#39;mentions&#39;] |
| **sort_dir** | **string**|  | [optional] [default to &#39;desc&#39;] |
| **page** | **int**|  | [optional] [default to 1] |
| **per_page** | **int**|  | [optional] [default to 20] |
| **output** | **string**| Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] |

### Return type

[**\LLMPulse\Model\SentimentTopicsResponse**](../Model/SentimentTopicsResponse.md)

### Authorization

[BearerAuth](../../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `listSentimentCategories()`

```php
listSentimentCategories($project_id, $output)
```

List sentiment categories (Growth plan or above)

Sentiment metric keys + labels + colors. For records, use /sentiments. Requires the Growth plan; lower tiers receive ERR_PLAN_REQUIRED.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: BearerAuth
$config = LLMPulse\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new LLMPulse\Api\SentimentsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$project_id = 56; // int | Project ID
$output = 'output_example'; // string | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.

try {
    $apiInstance->listSentimentCategories($project_id, $output);
} catch (Exception $e) {
    echo 'Exception when calling SentimentsApi->listSentimentCategories: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **project_id** | **int**| Project ID | |
| **output** | **string**| Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] |

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

## `listSentimentRecords()`

```php
listSentimentRecords($project_id, $competitor_id, $brand_only, $analysis, $model, $collection_id, $country_code, $language_code, $from, $to, $page, $per_page): \LLMPulse\Model\SentimentsResponse
```

List sentiment records (Growth plan or above)

Requires the Growth plan; lower tiers receive ERR_PLAN_REQUIRED.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: BearerAuth
$config = LLMPulse\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new LLMPulse\Api\SentimentsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$project_id = 56; // int | Project ID
$competitor_id = 56; // int
$brand_only = True; // bool
$analysis = 'analysis_example'; // string | One sentiment level or a comma-separated list: very_positive, positive, neutral, negative, very_negative
$model = 'model_example'; // string | Filter by one AI model. Here an unknown value, or a model the API key's user has not enabled, is ignored rather than rejected: the request succeeds and returns the records of every enabled model, as if model were omitted.
$collection_id = 12,34; // string | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize.
$country_code = 'country_code_example'; // string | One ISO country code or a comma-separated list (e.g. US,GB,DE)
$language_code = 'language_code_example'; // string | One ISO language code or a comma-separated list (e.g. en,es,de)
$from = new \DateTime('2013-10-20T19:20:30+01:00'); // \DateTime
$to = new \DateTime('2013-10-20T19:20:30+01:00'); // \DateTime | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier.
$page = 1; // int
$per_page = 20; // int

try {
    $result = $apiInstance->listSentimentRecords($project_id, $competitor_id, $brand_only, $analysis, $model, $collection_id, $country_code, $language_code, $from, $to, $page, $per_page);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling SentimentsApi->listSentimentRecords: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **project_id** | **int**| Project ID | |
| **competitor_id** | **int**|  | [optional] |
| **brand_only** | **bool**|  | [optional] |
| **analysis** | **string**| One sentiment level or a comma-separated list: very_positive, positive, neutral, negative, very_negative | [optional] |
| **model** | **string**| Filter by one AI model. Here an unknown value, or a model the API key&#39;s user has not enabled, is ignored rather than rejected: the request succeeds and returns the records of every enabled model, as if model were omitted. | [optional] |
| **collection_id** | **string**| One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize. | [optional] |
| **country_code** | **string**| One ISO country code or a comma-separated list (e.g. US,GB,DE) | [optional] |
| **language_code** | **string**| One ISO language code or a comma-separated list (e.g. en,es,de) | [optional] |
| **from** | **\DateTime**|  | [optional] |
| **to** | **\DateTime**| End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. | [optional] |
| **page** | **int**|  | [optional] [default to 1] |
| **per_page** | **int**|  | [optional] [default to 20] |

### Return type

[**\LLMPulse\Model\SentimentsResponse**](../Model/SentimentsResponse.md)

### Authorization

[BearerAuth](../../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
