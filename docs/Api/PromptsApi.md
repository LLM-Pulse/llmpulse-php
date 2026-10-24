# LLMPulse\PromptsApi

The questions executed against the AI models every week, and the execution records each run produces.

All URIs are relative to https://api.llmpulse.ai/api/v1, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**acceptSuggestedPrompts()**](PromptsApi.md#acceptSuggestedPrompts) | **POST** /suggested_prompts/accept | Accept suggested prompts |
| [**createPromptGeneration()**](PromptsApi.md#createPromptGeneration) | **POST** /prompt_generations | Generate prompt suggestions |
| [**createPrompts()**](PromptsApi.md#createPrompts) | **POST** /prompts | Bulk-create prompts |
| [**deletePrompt()**](PromptsApi.md#deletePrompt) | **DELETE** /prompts/{id} | Delete a prompt |
| [**getPromptGeneration()**](PromptsApi.md#getPromptGeneration) | **GET** /prompt_generations/{id} | Get a prompt generation run |
| [**importPrompts()**](PromptsApi.md#importPrompts) | **POST** /prompts/import | Import prompts |
| [**listPromptExecutions()**](PromptsApi.md#listPromptExecutions) | **GET** /dimensions/prompt_executions | List prompt executions |
| [**listPrompts()**](PromptsApi.md#listPrompts) | **GET** /dimensions/prompts | List prompts |
| [**listQueryFanOuts()**](PromptsApi.md#listQueryFanOuts) | **GET** /dimensions/query_fan_outs | List query fan-out |
| [**listSuggestedPrompts()**](PromptsApi.md#listSuggestedPrompts) | **GET** /suggested_prompts | List suggested prompts |
| [**rejectSuggestedPrompts()**](PromptsApi.md#rejectSuggestedPrompts) | **POST** /suggested_prompts/reject | Reject suggested prompts |
| [**updatePrompt()**](PromptsApi.md#updatePrompt) | **PATCH** /prompts/{id} | Edit a prompt&#39;s categorization |


## `acceptSuggestedPrompts()`

```php
acceptSuggestedPrompts($suggested_prompts_accept_request): \LLMPulse\Model\SuggestedPromptsAcceptResponse
```

Accept suggested prompts

Starts tracking up to 100 pending suggestions: each becomes a prompt in its own country and language, optionally put in one tag (tag_ids or tag_names; create_missing creates a missing name when the team member may create tags). Suggestions that are no longer pending come back in skipped. When the new prompts would exceed the plan the call returns ERR_LIMIT_REACHED and accepts nothing. Requires a `read_write` scope API key and, for team members, create access to Prompts.

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
$suggested_prompts_accept_request = new \LLMPulse\Model\SuggestedPromptsAcceptRequest(); // \LLMPulse\Model\SuggestedPromptsAcceptRequest

try {
    $result = $apiInstance->acceptSuggestedPrompts($suggested_prompts_accept_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling PromptsApi->acceptSuggestedPrompts: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **suggested_prompts_accept_request** | [**\LLMPulse\Model\SuggestedPromptsAcceptRequest**](../Model/SuggestedPromptsAcceptRequest.md)|  | |

### Return type

[**\LLMPulse\Model\SuggestedPromptsAcceptResponse**](../Model/SuggestedPromptsAcceptResponse.md)

### Authorization

[BearerAuth](../../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `createPromptGeneration()`

```php
createPromptGeneration($prompt_generation_request): \LLMPulse\Model\PromptGenerationResponse
```

Generate prompt suggestions

Starts a suggestion run with one of the generators behind the app's Add prompts wizards and answers 202 with the run. website writes suggestions from the scraped website (80% non-brand, 20% brand; up to 100 per project, then ERR_LIMIT_REACHED), keyword from a keyword or the project profile (optionally around a competitor), topic from a topic, reddit from Reddit discussions of a topic or brand, paa from Google People Also Ask (up to 5 keywords, counted against the account's 24-hour lookup allowance), reputational from brand reputation questions, translate from the project's prompts of another locale, search_console from the connected property's top queries of the last 28 days (Growth plan or above, ERR_PLAN_REQUIRED). The suggestions land in the Suggested prompts queue; poll GET /prompt_generations/{id}, then accept the ones you want with POST /suggested_prompts/accept. Nothing is tracked until accepted. The request is validated before the run starts, and refused with ERR_LIMIT_REACHED when the plan has no prompt slot left, or ERR_QUOTA_EXCEEDED after 60 runs in an hour (the per-user prompt suggestion allowance, shared with project setup). Requires a `read_write` scope API key and, for team members, create access to Prompts.

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
$prompt_generation_request = new \LLMPulse\Model\PromptGenerationRequest(); // \LLMPulse\Model\PromptGenerationRequest

try {
    $result = $apiInstance->createPromptGeneration($prompt_generation_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling PromptsApi->createPromptGeneration: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **prompt_generation_request** | [**\LLMPulse\Model\PromptGenerationRequest**](../Model/PromptGenerationRequest.md)|  | |

### Return type

[**\LLMPulse\Model\PromptGenerationResponse**](../Model/PromptGenerationResponse.md)

### Authorization

[BearerAuth](../../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

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

## `getPromptGeneration()`

```php
getPromptGeneration($project_id, $id): \LLMPulse\Model\PromptGenerationResponse
```

Get a prompt generation run

Returns a run started with POST /prompt_generations: processing while the generator works, then completed with the suggestions it saved to the Suggested prompts queue, or failed with an error code and message. Poll every few seconds; most runs finish within a minute. Runs are kept for 24 hours, their suggestions stay in the queue.

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
$id = 'id_example'; // string

try {
    $result = $apiInstance->getPromptGeneration($project_id, $id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling PromptsApi->getPromptGeneration: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **project_id** | **int**| Project ID | |
| **id** | **string**|  | |

### Return type

[**\LLMPulse\Model\PromptGenerationResponse**](../Model/PromptGenerationResponse.md)

### Authorization

[BearerAuth](../../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `importPrompts()`

```php
importPrompts($prompts_import_request): \LLMPulse\Model\PromptsImportResponse
```

Import prompts

The app's CSV import as JSON: up to 500 rows, each with its own prompt, country_code, language_code (codes or names; both default to the project's) and tags, created when missing. Duplicates are skipped and existing prompts still get the row's tags. The prompt limits are checked before anything is written: when the new prompts would exceed the plan the call returns ERR_LIMIT_REACHED and imports nothing. A row is skipped and comes back in row_errors when its country or language is unknown, when it would give a prompt more than 50 tags (rows repeating a prompt add up) or when its tags would take the request past 500 new tags. For a team member without create access to Tags, a row that needs a tag that does not exist yet is skipped and comes back in row_errors. For a team member without update access to Prompts, a row matching a prompt that already existed adds no tags to it, and comes back in row_errors when it would have added one. Responds 201 when it created prompts, 200 otherwise. Requires a `read_write` scope API key and, for team members, create access to Prompts.

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
$prompts_import_request = new \LLMPulse\Model\PromptsImportRequest(); // \LLMPulse\Model\PromptsImportRequest

try {
    $result = $apiInstance->importPrompts($prompts_import_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling PromptsApi->importPrompts: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **prompts_import_request** | [**\LLMPulse\Model\PromptsImportRequest**](../Model/PromptsImportRequest.md)|  | |

### Return type

[**\LLMPulse\Model\PromptsImportResponse**](../Model/PromptsImportResponse.md)

### Authorization

[BearerAuth](../../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `listPromptExecutions()`

```php
listPromptExecutions($project_id, $page, $per_page, $model, $collection_id, $country_code, $language_code, $prompt, $from, $to, $mention_filter, $citation_filter, $competitors, $output, $prompt_type, $brand_kind): \LLMPulse\Model\PromptExecutionsResponse
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
$model = 'model_example'; // string | Filter by one AI model. It must be a model enabled for the API key's user: an unknown value, or a model the user has not enabled, returns 422 ERR_INVALID_PARAM with the valid values in the message.
$collection_id = 12,34; // string | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize.
$country_code = 'country_code_example'; // string | One ISO country code or a comma-separated list (e.g. US,GB,DE)
$language_code = 'language_code_example'; // string | One ISO language code or a comma-separated list (e.g. en,es,de)
$prompt = 56; // int | Filter by prompt ID
$from = new \DateTime('2013-10-20T19:20:30+01:00'); // \DateTime
$to = new \DateTime('2013-10-20T19:20:30+01:00'); // \DateTime | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier.
$mention_filter = 'mention_filter_example'; // string | Filter by which brands are mentioned, as a two-axis matrix (your brand x competitors): mentions_you / not_mentions_you, mentions_competitor / not_mentions_competitor, and the four combined cells you_and_competitor, competitor_not_you (a rival wins and you are absent), you_not_competitor, no_brands (no tracked brand appears, i.e. open space). Combine with 'competitors' to narrow the competitor side to specific rivals; on a negative cell that reads 'none of these'. On /dimensions/sources it applies to the crawled content of each cited page instead of the answer text. The legacy value 'competitors_only' is still accepted as an alias of competitor_not_you.
$citation_filter = 'citation_filter_example'; // string | Same two-axis matrix applied to the domains cited in the answer instead of the brands named in it. Independent of mention_filter; pass both to intersect them (e.g. mentions_you + not_cites_you finds answers that talk about you without linking to you).
$competitors = 'competitors_example'; // string | Comma-separated competitor IDs (unknown IDs return ERR_INVALID_PARAM)
$output = 'output_example'; // string | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
$prompt_type = 'prompt_type_example'; // string | One prompt type or a comma-separated list: informational, navigational, commercial, transactional
$brand_kind = 'brand_kind_example'; // string | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default.

try {
    $result = $apiInstance->listPromptExecutions($project_id, $page, $per_page, $model, $collection_id, $country_code, $language_code, $prompt, $from, $to, $mention_filter, $citation_filter, $competitors, $output, $prompt_type, $brand_kind);
    print_r($result);
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
| **model** | **string**| Filter by one AI model. It must be a model enabled for the API key&#39;s user: an unknown value, or a model the user has not enabled, returns 422 ERR_INVALID_PARAM with the valid values in the message. | [optional] |
| **collection_id** | **string**| One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize. | [optional] |
| **country_code** | **string**| One ISO country code or a comma-separated list (e.g. US,GB,DE) | [optional] |
| **language_code** | **string**| One ISO language code or a comma-separated list (e.g. en,es,de) | [optional] |
| **prompt** | **int**| Filter by prompt ID | [optional] |
| **from** | **\DateTime**|  | [optional] |
| **to** | **\DateTime**| End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. | [optional] |
| **mention_filter** | **string**| Filter by which brands are mentioned, as a two-axis matrix (your brand x competitors): mentions_you / not_mentions_you, mentions_competitor / not_mentions_competitor, and the four combined cells you_and_competitor, competitor_not_you (a rival wins and you are absent), you_not_competitor, no_brands (no tracked brand appears, i.e. open space). Combine with &#39;competitors&#39; to narrow the competitor side to specific rivals; on a negative cell that reads &#39;none of these&#39;. On /dimensions/sources it applies to the crawled content of each cited page instead of the answer text. The legacy value &#39;competitors_only&#39; is still accepted as an alias of competitor_not_you. | [optional] |
| **citation_filter** | **string**| Same two-axis matrix applied to the domains cited in the answer instead of the brands named in it. Independent of mention_filter; pass both to intersect them (e.g. mentions_you + not_cites_you finds answers that talk about you without linking to you). | [optional] |
| **competitors** | **string**| Comma-separated competitor IDs (unknown IDs return ERR_INVALID_PARAM) | [optional] |
| **output** | **string**| Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] |
| **prompt_type** | **string**| One prompt type or a comma-separated list: informational, navigational, commercial, transactional | [optional] |
| **brand_kind** | **string**| Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. | [optional] |

### Return type

[**\LLMPulse\Model\PromptExecutionsResponse**](../Model/PromptExecutionsResponse.md)

### Authorization

[BearerAuth](../../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `listPrompts()`

```php
listPrompts($project_id, $page, $per_page, $model, $collection_id, $country_code, $language_code, $prompt, $prompt_type, $brand_kind, $from, $to, $output): \LLMPulse\Model\PromptsResponse
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
$model = 'model_example'; // string | Keep only the prompts with at least one execution on this AI model, of any outcome and date (the prompts /dimensions/prompt_executions lists for the same model). Prompts have no model of their own, so a prompt with no execution on this model yet (a newly enabled model, or a locale the model does not cover) is left out. An unknown value, or a model the API key's user has not enabled, returns 422 ERR_INVALID_PARAM. from and to still filter prompt creation.
$collection_id = 12,34; // string | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize.
$country_code = 'country_code_example'; // string | One ISO country code or a comma-separated list (e.g. US,GB,DE)
$language_code = 'language_code_example'; // string | One ISO language code or a comma-separated list (e.g. en,es,de)
$prompt = 56; // int | Filter by prompt ID
$prompt_type = 'prompt_type_example'; // string | One prompt type or a comma-separated list: informational, navigational, commercial, transactional
$brand_kind = 'brand_kind_example'; // string | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default.
$from = new \DateTime('2013-10-20T19:20:30+01:00'); // \DateTime
$to = new \DateTime('2013-10-20T19:20:30+01:00'); // \DateTime | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier.
$output = 'output_example'; // string | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.

try {
    $result = $apiInstance->listPrompts($project_id, $page, $per_page, $model, $collection_id, $country_code, $language_code, $prompt, $prompt_type, $brand_kind, $from, $to, $output);
    print_r($result);
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
| **model** | **string**| Keep only the prompts with at least one execution on this AI model, of any outcome and date (the prompts /dimensions/prompt_executions lists for the same model). Prompts have no model of their own, so a prompt with no execution on this model yet (a newly enabled model, or a locale the model does not cover) is left out. An unknown value, or a model the API key&#39;s user has not enabled, returns 422 ERR_INVALID_PARAM. from and to still filter prompt creation. | [optional] |
| **collection_id** | **string**| One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize. | [optional] |
| **country_code** | **string**| One ISO country code or a comma-separated list (e.g. US,GB,DE) | [optional] |
| **language_code** | **string**| One ISO language code or a comma-separated list (e.g. en,es,de) | [optional] |
| **prompt** | **int**| Filter by prompt ID | [optional] |
| **prompt_type** | **string**| One prompt type or a comma-separated list: informational, navigational, commercial, transactional | [optional] |
| **brand_kind** | **string**| Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. | [optional] |
| **from** | **\DateTime**|  | [optional] |
| **to** | **\DateTime**| End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. | [optional] |
| **output** | **string**| Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] |

### Return type

[**\LLMPulse\Model\PromptsResponse**](../Model/PromptsResponse.md)

### Authorization

[BearerAuth](../../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

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
$model = 'model_example'; // string | Filter by one AI model. It must be a model enabled for the API key's user: an unknown value, or a model the user has not enabled, returns 422 ERR_INVALID_PARAM with the valid values in the message.
$collection_id = 12,34; // string | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize.
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
| **model** | **string**| Filter by one AI model. It must be a model enabled for the API key&#39;s user: an unknown value, or a model the user has not enabled, returns 422 ERR_INVALID_PARAM with the valid values in the message. | [optional] |
| **collection_id** | **string**| One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize. | [optional] |
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

## `listSuggestedPrompts()`

```php
listSuggestedPrompts($project_id, $source, $status, $page, $per_page): \LLMPulse\Model\SuggestedPromptsResponse
```

List suggested prompts

Lists the project's Suggested prompts queue, the same list the app's Suggested Prompts tab shows, oldest first. It holds the suggestions of every generator (website, magic for keyword runs, topic, reddit, paa, reputational, translate, gsc for Search Console, catalog). Pending suggestions by default; status=all also returns accepted (with the prompt they became) and rejected ones. Team members need create access to Prompts, like the app's tab.

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
$source = 'source_example'; // string | Only suggestions from this generator
$status = 'pending'; // string | Only suggestions in this status
$page = 1; // int
$per_page = 50; // int

try {
    $result = $apiInstance->listSuggestedPrompts($project_id, $source, $status, $page, $per_page);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling PromptsApi->listSuggestedPrompts: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **project_id** | **int**| Project ID | |
| **source** | **string**| Only suggestions from this generator | [optional] |
| **status** | **string**| Only suggestions in this status | [optional] [default to &#39;pending&#39;] |
| **page** | **int**|  | [optional] [default to 1] |
| **per_page** | **int**|  | [optional] [default to 50] |

### Return type

[**\LLMPulse\Model\SuggestedPromptsResponse**](../Model/SuggestedPromptsResponse.md)

### Authorization

[BearerAuth](../../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `rejectSuggestedPrompts()`

```php
rejectSuggestedPrompts($suggested_prompt_ids_request): \LLMPulse\Model\SuggestedPromptsRejectResponse
```

Reject suggested prompts

Marks up to 100 pending suggestions as rejected, so they leave the pending list; suggestions that are no longer pending stay as they are. Tracks and deletes nothing. Requires a `read_write` scope API key and, for team members, create access to Prompts.

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
$suggested_prompt_ids_request = new \LLMPulse\Model\SuggestedPromptIdsRequest(); // \LLMPulse\Model\SuggestedPromptIdsRequest

try {
    $result = $apiInstance->rejectSuggestedPrompts($suggested_prompt_ids_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling PromptsApi->rejectSuggestedPrompts: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **suggested_prompt_ids_request** | [**\LLMPulse\Model\SuggestedPromptIdsRequest**](../Model/SuggestedPromptIdsRequest.md)|  | |

### Return type

[**\LLMPulse\Model\SuggestedPromptsRejectResponse**](../Model/SuggestedPromptsRejectResponse.md)

### Authorization

[BearerAuth](../../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `updatePrompt()`

```php
updatePrompt($id, $update_prompt_request): \LLMPulse\Model\PromptCategorizationResponse
```

Edit a prompt's categorization

Manual categorization, exactly like editing the intent and brand badges on the prompt page: send `prompt_type`, `brand_kind` or both. The prompt is marked as manually categorized (`categorization_source` becomes `manual`), so automatic categorization no longer changes it; the prompt page can revert it to automatic. Any other field returns ERR_INVALID_PARAM. Not available from a white-label portal (ERR_INTEGRATION_UNAVAILABLE), where the page hides the editor. Requires a `read_write` scope API key and, for team members, update permission on Prompts.

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
$id = 56; // int
$update_prompt_request = new \LLMPulse\Model\UpdatePromptRequest(); // \LLMPulse\Model\UpdatePromptRequest

try {
    $result = $apiInstance->updatePrompt($id, $update_prompt_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling PromptsApi->updatePrompt: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **int**|  | |
| **update_prompt_request** | [**\LLMPulse\Model\UpdatePromptRequest**](../Model/UpdatePromptRequest.md)|  | |

### Return type

[**\LLMPulse\Model\PromptCategorizationResponse**](../Model/PromptCategorizationResponse.md)

### Authorization

[BearerAuth](../../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
