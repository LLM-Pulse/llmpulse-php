# LLMPulse\PromptsApi

The questions executed against the AI models every week, and the execution records each run produces.

All URIs are relative to https://api.llmpulse.ai/api/v1, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**createPrompts()**](PromptsApi.md#createPrompts) | **POST** /prompts | Bulk-create prompts |
| [**deletePrompt()**](PromptsApi.md#deletePrompt) | **DELETE** /prompts/{id} | Delete a prompt |
| [**listPromptExecutions()**](PromptsApi.md#listPromptExecutions) | **GET** /dimensions/prompt_executions | List prompt executions |
| [**listPrompts()**](PromptsApi.md#listPrompts) | **GET** /dimensions/prompts | List prompts |
| [**listQueryFanOuts()**](PromptsApi.md#listQueryFanOuts) | **GET** /dimensions/query_fan_outs | List query fan-out |


## `createPrompts()`

```php
createPrompts($prompts_create_request): \LLMPulse\Model\PromptsCreateResponse
```

Bulk-create prompts

Add prompts to a project in bulk (up to 100 per request). Validates the account prompt quota and skips duplicates. Requires a `read_write` scope API key.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: BearerAuth
$config = LLMPulse\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new LLMPulse\Api\PromptsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$prompts_create_request = new \LLMPulse\Model\PromptsCreateRequest(); // \LLMPulse\Model\PromptsCreateRequest

try {
    $result = $apiInstance->createPrompts($prompts_create_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling PromptsApi->createPrompts: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **prompts_create_request** | [**\LLMPulse\Model\PromptsCreateRequest**](../Model/PromptsCreateRequest.md)|  | |

### Return type

[**\LLMPulse\Model\PromptsCreateResponse**](../Model/PromptsCreateResponse.md)

### Authorization

[BearerAuth](../../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `deletePrompt()`

```php
deletePrompt($project_id, $id)
```

Delete a prompt

Deletes a prompt (irreversible). The prompt disappears immediately and frees a prompt slot; its historical data (executions, mentions, citations, sentiment) is purged by a background job. Requires a `read_write` scope API key.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: BearerAuth
$config = LLMPulse\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new LLMPulse\Api\PromptsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$project_id = 56; // int | Project ID
$id = 56; // int

try {
    $apiInstance->deletePrompt($project_id, $id);
} catch (Exception $e) {
    echo 'Exception when calling PromptsApi->deletePrompt: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **project_id** | **int**| Project ID | |
| **id** | **int**|  | |

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

## `listPromptExecutions()`

```php
listPromptExecutions($project_id, $page, $per_page, $model, $collection_id, $country_code, $language_code, $prompt, $from, $to, $mention_filter, $citation_filter, $competitors, $output)
```

List prompt executions

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: BearerAuth
$config = LLMPulse\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new LLMPulse\Api\PromptsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$project_id = 56; // int | Project ID
$page = 1; // int
$per_page = 20; // int
$model = 'model_example'; // string | Filter by AI model. Models the API key's user has not enabled are silently dropped.
$collection_id = new \LLMPulse\Model\\LLMPulse\Model\GetTimeseriesCollectionIdParameter(); // \LLMPulse\Model\GetTimeseriesCollectionIdParameter | One collection/tag ID or a comma-separated list of IDs
$country_code = 'country_code_example'; // string | One ISO country code or a comma-separated list (e.g. US,GB,DE)
$language_code = 'language_code_example'; // string | One ISO language code or a comma-separated list (e.g. en,es,de)
$prompt = 56; // int | Filter by prompt ID
$from = new \DateTime('2013-10-20T19:20:30+01:00'); // \DateTime
$to = new \DateTime('2013-10-20T19:20:30+01:00'); // \DateTime | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier.
$mention_filter = 'mention_filter_example'; // string | Filter by which brands are mentioned, as a two-axis matrix (your brand x competitors): mentions_you / not_mentions_you, mentions_competitor / not_mentions_competitor, and the four combined cells you_and_competitor, competitor_not_you (a rival wins and you are absent), you_not_competitor, no_brands (no tracked brand appears, i.e. open space). Combine with 'competitors' to narrow the competitor side to specific rivals; on a negative cell that reads 'none of these'. On /dimensions/sources it applies to the crawled content of each cited page instead of the answer text. The legacy value 'competitors_only' is still accepted as an alias of competitor_not_you.
$citation_filter = 'citation_filter_example'; // string | Same two-axis matrix applied to the domains cited in the answer instead of the brands named in it. Independent of mention_filter; pass both to intersect them (e.g. mentions_you + not_cites_you finds answers that talk about you without linking to you).
$competitors = 'competitors_example'; // string | Comma-separated competitor IDs (unknown IDs return ERR_INVALID_PARAM)
$output = 'output_example'; // string | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.

try {
    $apiInstance->listPromptExecutions($project_id, $page, $per_page, $model, $collection_id, $country_code, $language_code, $prompt, $from, $to, $mention_filter, $citation_filter, $competitors, $output);
} catch (Exception $e) {
    echo 'Exception when calling PromptsApi->listPromptExecutions: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **project_id** | **int**| Project ID | |
| **page** | **int**|  | [optional] [default to 1] |
| **per_page** | **int**|  | [optional] [default to 20] |
| **model** | **string**| Filter by AI model. Models the API key&#39;s user has not enabled are silently dropped. | [optional] |
| **collection_id** | [**\LLMPulse\Model\GetTimeseriesCollectionIdParameter**](../Model/.md)| One collection/tag ID or a comma-separated list of IDs | [optional] |
| **country_code** | **string**| One ISO country code or a comma-separated list (e.g. US,GB,DE) | [optional] |
| **language_code** | **string**| One ISO language code or a comma-separated list (e.g. en,es,de) | [optional] |
| **prompt** | **int**| Filter by prompt ID | [optional] |
| **from** | **\DateTime**|  | [optional] |
| **to** | **\DateTime**| End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. | [optional] |
| **mention_filter** | **string**| Filter by which brands are mentioned, as a two-axis matrix (your brand x competitors): mentions_you / not_mentions_you, mentions_competitor / not_mentions_competitor, and the four combined cells you_and_competitor, competitor_not_you (a rival wins and you are absent), you_not_competitor, no_brands (no tracked brand appears, i.e. open space). Combine with &#39;competitors&#39; to narrow the competitor side to specific rivals; on a negative cell that reads &#39;none of these&#39;. On /dimensions/sources it applies to the crawled content of each cited page instead of the answer text. The legacy value &#39;competitors_only&#39; is still accepted as an alias of competitor_not_you. | [optional] |
| **citation_filter** | **string**| Same two-axis matrix applied to the domains cited in the answer instead of the brands named in it. Independent of mention_filter; pass both to intersect them (e.g. mentions_you + not_cites_you finds answers that talk about you without linking to you). | [optional] |
| **competitors** | **string**| Comma-separated competitor IDs (unknown IDs return ERR_INVALID_PARAM) | [optional] |
| **output** | **string**| Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] |

### Return type

void (empty response body)

### Authorization

[BearerAuth](../../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: Not defined

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `listPrompts()`

```php
listPrompts($project_id, $page, $per_page, $model, $collection_id, $country_code, $language_code, $prompt_type, $brand_kind, $from, $to, $output)
```

List prompts

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: BearerAuth
$config = LLMPulse\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new LLMPulse\Api\PromptsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$project_id = 56; // int | Project ID
$page = 1; // int
$per_page = 20; // int
$model = 'model_example'; // string | Filter by AI model. Models the API key's user has not enabled are silently dropped.
$collection_id = new \LLMPulse\Model\\LLMPulse\Model\GetTimeseriesCollectionIdParameter(); // \LLMPulse\Model\GetTimeseriesCollectionIdParameter | One collection/tag ID or a comma-separated list of IDs
$country_code = 'country_code_example'; // string | One ISO country code or a comma-separated list (e.g. US,GB,DE)
$language_code = 'language_code_example'; // string | One ISO language code or a comma-separated list (e.g. en,es,de)
$prompt_type = 'prompt_type_example'; // string | One prompt type or a comma-separated list: informational, navigational, commercial, transactional
$brand_kind = 'brand_kind_example'; // string | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default.
$from = new \DateTime('2013-10-20T19:20:30+01:00'); // \DateTime
$to = new \DateTime('2013-10-20T19:20:30+01:00'); // \DateTime | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier.
$output = 'output_example'; // string | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.

try {
    $apiInstance->listPrompts($project_id, $page, $per_page, $model, $collection_id, $country_code, $language_code, $prompt_type, $brand_kind, $from, $to, $output);
} catch (Exception $e) {
    echo 'Exception when calling PromptsApi->listPrompts: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **project_id** | **int**| Project ID | |
| **page** | **int**|  | [optional] [default to 1] |
| **per_page** | **int**|  | [optional] [default to 20] |
| **model** | **string**| Filter by AI model. Models the API key&#39;s user has not enabled are silently dropped. | [optional] |
| **collection_id** | [**\LLMPulse\Model\GetTimeseriesCollectionIdParameter**](../Model/.md)| One collection/tag ID or a comma-separated list of IDs | [optional] |
| **country_code** | **string**| One ISO country code or a comma-separated list (e.g. US,GB,DE) | [optional] |
| **language_code** | **string**| One ISO language code or a comma-separated list (e.g. en,es,de) | [optional] |
| **prompt_type** | **string**| One prompt type or a comma-separated list: informational, navigational, commercial, transactional | [optional] |
| **brand_kind** | **string**| Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. | [optional] |
| **from** | **\DateTime**|  | [optional] |
| **to** | **\DateTime**| End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. | [optional] |
| **output** | **string**| Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] |

### Return type

void (empty response body)

### Authorization

[BearerAuth](../../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: Not defined

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `listQueryFanOuts()`

```php
listQueryFanOuts($project_id, $page, $per_page, $view, $order, $direction, $query, $model, $collection_id, $country_code, $language_code, $prompt, $prompt_type, $brand_kind, $range, $from, $to, $output)
```

List query fan-out

The sub-queries a model actually issued when answering your tracked prompts. view=query (default) returns one row per distinct sub-query with count and share of all occurrences; view=prompt returns one row per prompt with how many distinct sub-queries it produced. Fan-out is reported mainly by ChatGPT, so an empty result usually means the models in scope do not expose it. The API returns the aggregation only: for a period-over-period delta, call it twice with explicit from/to.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: BearerAuth
$config = LLMPulse\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new LLMPulse\Api\PromptsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$project_id = 56; // int | Project ID
$page = 1; // int
$per_page = 20; // int
$view = 'query'; // string | Row shape: one per distinct sub-query, or one per prompt
$order = 'order_example'; // string | Sort field; the allowed set depends on view
$direction = 'desc'; // string
$query = 'query_example'; // string | Case-insensitive substring filter on the sub-query text
$model = 'model_example'; // string | Filter by AI model. Models the API key's user has not enabled are silently dropped.
$collection_id = new \LLMPulse\Model\\LLMPulse\Model\GetTimeseriesCollectionIdParameter(); // \LLMPulse\Model\GetTimeseriesCollectionIdParameter | One collection/tag ID or a comma-separated list of IDs
$country_code = 'country_code_example'; // string | One ISO country code or a comma-separated list (e.g. US,GB,DE)
$language_code = 'language_code_example'; // string | One ISO language code or a comma-separated list (e.g. en,es,de)
$prompt = 56; // int | Filter by prompt ID
$prompt_type = 'prompt_type_example'; // string | One prompt type or a comma-separated list: informational, navigational, commercial, transactional
$brand_kind = 'brand_kind_example'; // string | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default.
$range = 56; // int | Number of days to look back (alternative to from/to)
$from = new \DateTime('2013-10-20T19:20:30+01:00'); // \DateTime
$to = new \DateTime('2013-10-20T19:20:30+01:00'); // \DateTime | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier.
$output = 'output_example'; // string | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.

try {
    $apiInstance->listQueryFanOuts($project_id, $page, $per_page, $view, $order, $direction, $query, $model, $collection_id, $country_code, $language_code, $prompt, $prompt_type, $brand_kind, $range, $from, $to, $output);
} catch (Exception $e) {
    echo 'Exception when calling PromptsApi->listQueryFanOuts: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **project_id** | **int**| Project ID | |
| **page** | **int**|  | [optional] [default to 1] |
| **per_page** | **int**|  | [optional] [default to 20] |
| **view** | **string**| Row shape: one per distinct sub-query, or one per prompt | [optional] [default to &#39;query&#39;] |
| **order** | **string**| Sort field; the allowed set depends on view | [optional] |
| **direction** | **string**|  | [optional] [default to &#39;desc&#39;] |
| **query** | **string**| Case-insensitive substring filter on the sub-query text | [optional] |
| **model** | **string**| Filter by AI model. Models the API key&#39;s user has not enabled are silently dropped. | [optional] |
| **collection_id** | [**\LLMPulse\Model\GetTimeseriesCollectionIdParameter**](../Model/.md)| One collection/tag ID or a comma-separated list of IDs | [optional] |
| **country_code** | **string**| One ISO country code or a comma-separated list (e.g. US,GB,DE) | [optional] |
| **language_code** | **string**| One ISO language code or a comma-separated list (e.g. en,es,de) | [optional] |
| **prompt** | **int**| Filter by prompt ID | [optional] |
| **prompt_type** | **string**| One prompt type or a comma-separated list: informational, navigational, commercial, transactional | [optional] |
| **brand_kind** | **string**| Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. | [optional] |
| **range** | **int**| Number of days to look back (alternative to from/to) | [optional] |
| **from** | **\DateTime**|  | [optional] |
| **to** | **\DateTime**| End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. | [optional] |
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
