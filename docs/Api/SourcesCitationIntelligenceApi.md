# LLMPulse\SourcesCitationIntelligenceApi



All URIs are relative to https://api.llmpulse.ai/api/v1, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**addUrlListEntries()**](SourcesCitationIntelligenceApi.md#addUrlListEntries) | **POST** /url_lists/{id}/entries | Add entries to a URL list |
| [**createUrlList()**](SourcesCitationIntelligenceApi.md#createUrlList) | **POST** /url_lists | Create a URL list |
| [**deleteUrlList()**](SourcesCitationIntelligenceApi.md#deleteUrlList) | **DELETE** /url_lists/{id} | Delete a URL list |
| [**getCitedUrlContent()**](SourcesCitationIntelligenceApi.md#getCitedUrlContent) | **GET** /citation_intelligence/urls/{url_sha256}/content | Cited URL cached content |
| [**getCitedUrlDetail()**](SourcesCitationIntelligenceApi.md#getCitedUrlDetail) | **GET** /citation_intelligence/urls/{url_sha256} | Cited URL detail |
| [**getMentionsByCitingDomain()**](SourcesCitationIntelligenceApi.md#getMentionsByCitingDomain) | **GET** /citation_intelligence/mentions_by_domain | Mention share by citing domain |
| [**getUrlList()**](SourcesCitationIntelligenceApi.md#getUrlList) | **GET** /url_lists/{id} | Get a URL list report |
| [**listCitationGroups()**](SourcesCitationIntelligenceApi.md#listCitationGroups) | **GET** /citation_intelligence/groups | Grouped citation intelligence |
| [**listCitedUrlOccurrences()**](SourcesCitationIntelligenceApi.md#listCitedUrlOccurrences) | **GET** /citation_intelligence/urls/{url_sha256}/occurrences | Cited URL occurrences |
| [**listSources()**](SourcesCitationIntelligenceApi.md#listSources) | **GET** /dimensions/sources | List source URLs |
| [**listUrlLists()**](SourcesCitationIntelligenceApi.md#listUrlLists) | **GET** /url_lists | List URL lists |
| [**removeUrlListEntries()**](SourcesCitationIntelligenceApi.md#removeUrlListEntries) | **POST** /url_lists/{id}/entries/remove | Remove entries from a URL list |
| [**updateUrlList()**](SourcesCitationIntelligenceApi.md#updateUrlList) | **PATCH** /url_lists/{id} | Update a URL list |


## `addUrlListEntries()`

```php
addUrlListEntries($id, $url_list_entries_add_request): \LLMPulse\Model\UrlListEntriesAddResponse
```

Add entries to a URL list

Adds entries, as POST /url_lists reads them. A rule the list already holds keeps its place and takes only the added_on, cost and channel this request sends for it. Values that do not parse come back in invalid_entries. Requires a `read_write` scope API key and the Growth plan.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: BearerAuth
$config = LLMPulse\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new LLMPulse\Api\SourcesCitationIntelligenceApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 56; // int
$url_list_entries_add_request = new \LLMPulse\Model\UrlListEntriesAddRequest(); // \LLMPulse\Model\UrlListEntriesAddRequest

try {
    $result = $apiInstance->addUrlListEntries($id, $url_list_entries_add_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling SourcesCitationIntelligenceApi->addUrlListEntries: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **int**|  | |
| **url_list_entries_add_request** | [**\LLMPulse\Model\UrlListEntriesAddRequest**](../Model/UrlListEntriesAddRequest.md)|  | |

### Return type

[**\LLMPulse\Model\UrlListEntriesAddResponse**](../Model/UrlListEntriesAddResponse.md)

### Authorization

[BearerAuth](../../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `createUrlList()`

```php
createUrlList($url_list_create_request): \LLMPulse\Model\UrlListCreateResponse
```

Create a URL list

Creates a URL list. Each entry is a string or an object with value, match_type, added_on (YYYY-MM-DD, default today), cost (in the list currency) and channel. Without a match_type, \"acme.com/blog/_*\" is a prefix, a value with a path or query an exact URL and a bare host a domain. A list holds at most 1000 entries and a project at most 100 lists; the name is unique per project, case-insensitive. Refusals answer ERR_INVALID_PARAM with a reason token in error.meta.reason. Requires a `read_write` scope API key and the Growth plan.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: BearerAuth
$config = LLMPulse\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new LLMPulse\Api\SourcesCitationIntelligenceApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$url_list_create_request = new \LLMPulse\Model\UrlListCreateRequest(); // \LLMPulse\Model\UrlListCreateRequest

try {
    $result = $apiInstance->createUrlList($url_list_create_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling SourcesCitationIntelligenceApi->createUrlList: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **url_list_create_request** | [**\LLMPulse\Model\UrlListCreateRequest**](../Model/UrlListCreateRequest.md)|  | |

### Return type

[**\LLMPulse\Model\UrlListCreateResponse**](../Model/UrlListCreateResponse.md)

### Authorization

[BearerAuth](../../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `deleteUrlList()`

```php
deleteUrlList($project_id, $id): \LLMPulse\Model\UrlListDeleteResponse
```

Delete a URL list

Deletes a URL list and its entries. Citation data is not affected. Requires a `read_write` scope API key and the Growth plan.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: BearerAuth
$config = LLMPulse\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new LLMPulse\Api\SourcesCitationIntelligenceApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$project_id = 56; // int | Project ID
$id = 56; // int

try {
    $result = $apiInstance->deleteUrlList($project_id, $id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling SourcesCitationIntelligenceApi->deleteUrlList: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **project_id** | **int**| Project ID | |
| **id** | **int**|  | |

### Return type

[**\LLMPulse\Model\UrlListDeleteResponse**](../Model/UrlListDeleteResponse.md)

### Authorization

[BearerAuth](../../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getCitedUrlContent()`

```php
getCitedUrlContent($project_id, $url_sha256): \LLMPulse\Model\CitedUrlContentResponse
```

Cited URL cached content

Unavailable page content keeps the cited URL and citation metrics. Page metadata/content and unknown brand_mentioned/competitor_mentioned return null. content_gap_status is content_unavailable (or missing_page_cache) without usable content, and mentions_not_processed when the page has usable content but its mention analysis has not completed for this project. Mention fields (brand_mentioned, competitor_mentioned, brand_position, brands, mentions, content_gap_status) describe the analysis for the requesting project: a page not yet analyzed for it returns null (never false) brand_mentioned, competitor_mentioned and brand_position, empty brands and mentions arrays and page_cache.mentions_processed false. page_cache.mentions_processed is true exactly when brand_mentioned is not null. An analyzed page keeps its last result until a newer analysis replaces it. status_code shows a saved successful response or observed 404/410; other crawl failures and error_message are hidden. last_crawled_at dates the saved copy. Domain/host crawled_urls_count counts usable copies; brand_mentioned_urls_count and competitor_mentioned_urls_count count only URLs analyzed for the project and are null when none is.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: BearerAuth
$config = LLMPulse\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new LLMPulse\Api\SourcesCitationIntelligenceApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$project_id = 56; // int | Project ID
$url_sha256 = 'url_sha256_example'; // string | 64-character hex SHA-256 of the cited URL

try {
    $result = $apiInstance->getCitedUrlContent($project_id, $url_sha256);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling SourcesCitationIntelligenceApi->getCitedUrlContent: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **project_id** | **int**| Project ID | |
| **url_sha256** | **string**| 64-character hex SHA-256 of the cited URL | |

### Return type

[**\LLMPulse\Model\CitedUrlContentResponse**](../Model/CitedUrlContentResponse.md)

### Authorization

[BearerAuth](../../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getCitedUrlDetail()`

```php
getCitedUrlDetail($project_id, $url_sha256, $model, $collection_id, $country_code, $language_code, $prompt, $brand_kind, $from, $to, $source_type, $sentiment, $content_gap, $include_series): \LLMPulse\Model\CitedUrlDetailsResponse
```

Cited URL detail

Unavailable page content keeps the cited URL and citation metrics. Page metadata/content and unknown brand_mentioned/competitor_mentioned return null. content_gap_status is content_unavailable (or missing_page_cache) without usable content, and mentions_not_processed when the page has usable content but its mention analysis has not completed for this project. Mention fields (brand_mentioned, competitor_mentioned, brand_position, brands, mentions, content_gap_status) describe the analysis for the requesting project: a page not yet analyzed for it returns null (never false) brand_mentioned, competitor_mentioned and brand_position, empty brands and mentions arrays and page_cache.mentions_processed false. page_cache.mentions_processed is true exactly when brand_mentioned is not null. An analyzed page keeps its last result until a newer analysis replaces it. status_code shows a saved successful response or observed 404/410; other crawl failures and error_message are hidden. last_crawled_at dates the saved copy. Domain/host crawled_urls_count counts usable copies; brand_mentioned_urls_count and competitor_mentioned_urls_count count only URLs analyzed for the project and are null when none is. The filters narrow stats and citation_series alike. citation_series (with include_series=true) holds the answers citing the URL under the same filters: granularity (day, week or month, from the account tracking cadence, with weeks when a daily account spans more than 60 days, starting on Monday), total (equal to total_responses), by_model (answers per AI model, largest first, which can include enabled models outside the seven the model filter accepts) and data, one { date, value } point per period that holds a filtered answer, so a zero means answers ran and none cited it. Periods date each answer by the day it was created in Europe/Madrid time, the date from and to filter.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: BearerAuth
$config = LLMPulse\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new LLMPulse\Api\SourcesCitationIntelligenceApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$project_id = 56; // int | Project ID
$url_sha256 = 'url_sha256_example'; // string | 64-character hex SHA-256 of the cited URL
$model = 'model_example'; // string | Filter by one AI model. Only chatgpt, ai_overview, ai_mode, perplexity, gemini, naver_ai, baidu_ai, naver_ai_tab, qwen, doubao, bing_ai_mode and bing_ai_overview are accepted: any other value, including another model enabled for the API key's user, returns 422 ERR_INVALID_PARAM (invalid model). One of those twelve that the user has not enabled also returns 422 ERR_INVALID_PARAM, with the valid values in the message.
$collection_id = 12,34; // string | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize.
$country_code = 'country_code_example'; // string | One ISO country code or a comma-separated list (e.g. US,GB,DE)
$language_code = 'language_code_example'; // string | One ISO language code or a comma-separated list (e.g. en,es,de)
$prompt = 56; // int | Filter by prompt ID. An id that is not a plain positive number, or that names no prompt of the project, returns 422 ERR_INVALID_PARAM.
$brand_kind = 'brand_kind_example'; // string | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default.
$from = new \DateTime('2013-10-20T19:20:30+01:00'); // \DateTime
$to = new \DateTime('2013-10-20T19:20:30+01:00'); // \DateTime | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier.
$source_type = 'source_type_example'; // string
$sentiment = 'sentiment_example'; // string | Keeps the citations of answers with a negative brand sentiment. Needs the Growth plan or above: below it the filter answers 403 ERR_PLAN_REQUIRED.
$content_gap = 'content_gap_example'; // string | mentioned: the cited page mentions your brand. gap: it mentions a competitor but not your brand. Only pages with usable content whose mention analysis has completed for this project match.
$include_series = false; // bool | Adds citation_series. Without it the response is unchanged.

try {
    $result = $apiInstance->getCitedUrlDetail($project_id, $url_sha256, $model, $collection_id, $country_code, $language_code, $prompt, $brand_kind, $from, $to, $source_type, $sentiment, $content_gap, $include_series);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling SourcesCitationIntelligenceApi->getCitedUrlDetail: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **project_id** | **int**| Project ID | |
| **url_sha256** | **string**| 64-character hex SHA-256 of the cited URL | |
| **model** | **string**| Filter by one AI model. Only chatgpt, ai_overview, ai_mode, perplexity, gemini, naver_ai, baidu_ai, naver_ai_tab, qwen, doubao, bing_ai_mode and bing_ai_overview are accepted: any other value, including another model enabled for the API key&#39;s user, returns 422 ERR_INVALID_PARAM (invalid model). One of those twelve that the user has not enabled also returns 422 ERR_INVALID_PARAM, with the valid values in the message. | [optional] |
| **collection_id** | **string**| One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize. | [optional] |
| **country_code** | **string**| One ISO country code or a comma-separated list (e.g. US,GB,DE) | [optional] |
| **language_code** | **string**| One ISO language code or a comma-separated list (e.g. en,es,de) | [optional] |
| **prompt** | **int**| Filter by prompt ID. An id that is not a plain positive number, or that names no prompt of the project, returns 422 ERR_INVALID_PARAM. | [optional] |
| **brand_kind** | **string**| Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. | [optional] |
| **from** | **\DateTime**|  | [optional] |
| **to** | **\DateTime**| End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. | [optional] |
| **source_type** | **string**|  | [optional] |
| **sentiment** | **string**| Keeps the citations of answers with a negative brand sentiment. Needs the Growth plan or above: below it the filter answers 403 ERR_PLAN_REQUIRED. | [optional] |
| **content_gap** | **string**| mentioned: the cited page mentions your brand. gap: it mentions a competitor but not your brand. Only pages with usable content whose mention analysis has completed for this project match. | [optional] |
| **include_series** | **bool**| Adds citation_series. Without it the response is unchanged. | [optional] [default to false] |

### Return type

[**\LLMPulse\Model\CitedUrlDetailsResponse**](../Model/CitedUrlDetailsResponse.md)

### Authorization

[BearerAuth](../../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getMentionsByCitingDomain()`

```php
getMentionsByCitingDomain($project_id, $domains, $model, $collection_id, $country_code, $language_code, $prompt, $brand_kind, $from, $to): \LLMPulse\Model\CitingDomainMentionShareResponse
```

Mention share by citing domain

For the responses where each given source domain is cited, returns the share of those responses that mention the brand vs each competitor (brand + competitors sum to 100% per domain). Pass multiple domains to get the whole matrix in one call.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: BearerAuth
$config = LLMPulse\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new LLMPulse\Api\SourcesCitationIntelligenceApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$project_id = 56; // int | Project ID
$domains = array('domains_example'); // string[] | Source domains to analyze: one domain or a comma-separated list, e.g. domains=gmac.com,educaweb.com. The bracket form domains[]=gmac.com&domains[]=educaweb.com is also accepted.
$model = 'model_example'; // string | Filter by one AI model. Only chatgpt, ai_overview, ai_mode, perplexity, gemini, naver_ai, baidu_ai, naver_ai_tab, qwen, doubao, bing_ai_mode and bing_ai_overview are accepted: any other value, including another model enabled for the API key's user, returns 422 ERR_INVALID_PARAM (invalid model). One of those twelve that the user has not enabled also returns 422 ERR_INVALID_PARAM, with the valid values in the message.
$collection_id = 12,34; // string | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize.
$country_code = 'country_code_example'; // string | One ISO country code or a comma-separated list (e.g. US,GB,DE)
$language_code = 'language_code_example'; // string | One ISO language code or a comma-separated list (e.g. en,es,de)
$prompt = 56; // int | Filter by prompt ID. An id that is not a plain positive number, or that names no prompt of the project, returns 422 ERR_INVALID_PARAM.
$brand_kind = 'brand_kind_example'; // string | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default.
$from = new \DateTime('2013-10-20T19:20:30+01:00'); // \DateTime
$to = new \DateTime('2013-10-20T19:20:30+01:00'); // \DateTime | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier.

try {
    $result = $apiInstance->getMentionsByCitingDomain($project_id, $domains, $model, $collection_id, $country_code, $language_code, $prompt, $brand_kind, $from, $to);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling SourcesCitationIntelligenceApi->getMentionsByCitingDomain: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **project_id** | **int**| Project ID | |
| **domains** | [**string[]**](../Model/string.md)| Source domains to analyze: one domain or a comma-separated list, e.g. domains&#x3D;gmac.com,educaweb.com. The bracket form domains[]&#x3D;gmac.com&amp;domains[]&#x3D;educaweb.com is also accepted. | |
| **model** | **string**| Filter by one AI model. Only chatgpt, ai_overview, ai_mode, perplexity, gemini, naver_ai, baidu_ai, naver_ai_tab, qwen, doubao, bing_ai_mode and bing_ai_overview are accepted: any other value, including another model enabled for the API key&#39;s user, returns 422 ERR_INVALID_PARAM (invalid model). One of those twelve that the user has not enabled also returns 422 ERR_INVALID_PARAM, with the valid values in the message. | [optional] |
| **collection_id** | **string**| One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize. | [optional] |
| **country_code** | **string**| One ISO country code or a comma-separated list (e.g. US,GB,DE) | [optional] |
| **language_code** | **string**| One ISO language code or a comma-separated list (e.g. en,es,de) | [optional] |
| **prompt** | **int**| Filter by prompt ID. An id that is not a plain positive number, or that names no prompt of the project, returns 422 ERR_INVALID_PARAM. | [optional] |
| **brand_kind** | **string**| Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. | [optional] |
| **from** | **\DateTime**|  | [optional] |
| **to** | **\DateTime**| End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. | [optional] |

### Return type

[**\LLMPulse\Model\CitingDomainMentionShareResponse**](../Model/CitingDomainMentionShareResponse.md)

### Authorization

[BearerAuth](../../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getUrlList()`

```php
getUrlList($id, $project_id, $status, $order, $direction, $page, $per_page, $model, $collection_id, $country_code, $language_code, $prompt, $brand_kind, $from, $to, $range): \LLMPulse\Model\UrlListDetailResponse
```

Get a URL list report

The list, its summary (entries_count, cited_entries, citations, answers in the window, citation_rate, avg_citation_position, median_days_to_first_citation, total_cost, cost_per_cited_entry) and a page of its entries. An entry's status is cited (an answer cited it in the window), lost (cited before the window, not in it) or not_cited. first_cited_at reads the filtered answers up to the window's end. days_to_first_citation is null before the first citation or when the page was cited before it was added. brand_mentioned is set for exact URLs once their page was read, else null. Without from/to or range the window is all time. Requires the Growth plan.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: BearerAuth
$config = LLMPulse\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new LLMPulse\Api\SourcesCitationIntelligenceApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 56; // int
$project_id = 56; // int | Project ID
$status = 'status_example'; // string | Only entries with this status.
$order = 'citations'; // string
$direction = 'desc'; // string
$page = 1; // int
$per_page = 20; // int
$model = 'model_example'; // string | Filter by one AI model. Only chatgpt, ai_overview, ai_mode, perplexity, gemini, naver_ai, baidu_ai, naver_ai_tab, qwen, doubao, bing_ai_mode and bing_ai_overview are accepted: any other value, including another model enabled for the API key's user, returns 422 ERR_INVALID_PARAM (invalid model). One of those twelve that the user has not enabled also returns 422 ERR_INVALID_PARAM, with the valid values in the message.
$collection_id = 12,34; // string | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize.
$country_code = 'country_code_example'; // string | One ISO country code or a comma-separated list (e.g. US,GB,DE)
$language_code = 'language_code_example'; // string | One ISO language code or a comma-separated list (e.g. en,es,de)
$prompt = 56; // int | Filter by prompt ID. An id that is not a plain positive number, or that names no prompt of the project, returns 422 ERR_INVALID_PARAM.
$brand_kind = 'brand_kind_example'; // string | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default.
$from = new \DateTime('2013-10-20T19:20:30+01:00'); // \DateTime
$to = new \DateTime('2013-10-20T19:20:30+01:00'); // \DateTime | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier.
$range = 56; // int | Number of days to look back (alternative to from/to, which win when both are given). A value that is not a plain positive number returns 422 ERR_INVALID_PARAM, even beside from/to.

try {
    $result = $apiInstance->getUrlList($id, $project_id, $status, $order, $direction, $page, $per_page, $model, $collection_id, $country_code, $language_code, $prompt, $brand_kind, $from, $to, $range);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling SourcesCitationIntelligenceApi->getUrlList: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **int**|  | |
| **project_id** | **int**| Project ID | |
| **status** | **string**| Only entries with this status. | [optional] |
| **order** | **string**|  | [optional] [default to &#39;citations&#39;] |
| **direction** | **string**|  | [optional] [default to &#39;desc&#39;] |
| **page** | **int**|  | [optional] [default to 1] |
| **per_page** | **int**|  | [optional] [default to 20] |
| **model** | **string**| Filter by one AI model. Only chatgpt, ai_overview, ai_mode, perplexity, gemini, naver_ai, baidu_ai, naver_ai_tab, qwen, doubao, bing_ai_mode and bing_ai_overview are accepted: any other value, including another model enabled for the API key&#39;s user, returns 422 ERR_INVALID_PARAM (invalid model). One of those twelve that the user has not enabled also returns 422 ERR_INVALID_PARAM, with the valid values in the message. | [optional] |
| **collection_id** | **string**| One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize. | [optional] |
| **country_code** | **string**| One ISO country code or a comma-separated list (e.g. US,GB,DE) | [optional] |
| **language_code** | **string**| One ISO language code or a comma-separated list (e.g. en,es,de) | [optional] |
| **prompt** | **int**| Filter by prompt ID. An id that is not a plain positive number, or that names no prompt of the project, returns 422 ERR_INVALID_PARAM. | [optional] |
| **brand_kind** | **string**| Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. | [optional] |
| **from** | **\DateTime**|  | [optional] |
| **to** | **\DateTime**| End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. | [optional] |
| **range** | **int**| Number of days to look back (alternative to from/to, which win when both are given). A value that is not a plain positive number returns 422 ERR_INVALID_PARAM, even beside from/to. | [optional] |

### Return type

[**\LLMPulse\Model\UrlListDetailResponse**](../Model/UrlListDetailResponse.md)

### Authorization

[BearerAuth](../../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `listCitationGroups()`

```php
listCitationGroups($project_id, $view, $page, $per_page, $order, $direction, $model, $collection_id, $country_code, $language_code, $prompt, $brand_kind, $from, $to, $key, $include_series, $query, $source_type, $sentiment, $content_gap): \LLMPulse\Model\CitationGroupsResponse
```

Grouped citation intelligence

Grouped citation intelligence by url / domain / host with per-model breakdown, citation rate, and avg citation position. Counts and citation rate include visible citations and background source references. Average position ignores rows with position=0. Owned and competitor source matching honor the project's exact-subdomain setting. Filter vocabulary aligns with `source_type` returned by the API. Unavailable page content keeps the cited URL and citation metrics. Page metadata/content and unknown brand_mentioned/competitor_mentioned return null. content_gap_status is content_unavailable (or missing_page_cache) without usable content, and mentions_not_processed when the page has usable content but its mention analysis has not completed for this project. Mention fields (brand_mentioned, competitor_mentioned, brand_position, brands, mentions, content_gap_status) describe the analysis for the requesting project: a page not yet analyzed for it returns null (never false) brand_mentioned, competitor_mentioned and brand_position, empty brands and mentions arrays and page_cache.mentions_processed false. page_cache.mentions_processed is true exactly when brand_mentioned is not null. An analyzed page keeps its last result until a newer analysis replaces it. status_code shows a saved successful response or observed 404/410; other crawl failures and error_message are hidden. last_crawled_at dates the saved copy. Domain/host crawled_urls_count counts usable copies; brand_mentioned_urls_count and competitor_mentioned_urls_count count only URLs analyzed for the project and are null when none is. Pass key to read one group; brand_kind filters by the brand focus of the prompts, like the source page. citation_series (with include_series=true) holds the answers citing the URL, domain or host under the same filters: granularity (day, week or month, from the account tracking cadence, with weeks when a daily account spans more than 60 days, starting on Monday), total (equal to total_responses), by_model (answers per AI model, largest first, which can include enabled models outside the seven the model filter accepts) and data, one { date, value } point per period that holds a filtered answer, so a zero means answers ran and none cited it. Periods date each answer by the day it was created in Europe/Madrid time, the date from and to filter.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: BearerAuth
$config = LLMPulse\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new LLMPulse\Api\SourcesCitationIntelligenceApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$project_id = 56; // int | Project ID
$view = 'url'; // string
$page = 1; // int
$per_page = 20; // int
$order = 'order_example'; // string
$direction = 'direction_example'; // string
$model = 'model_example'; // string | Filter by one AI model. Only chatgpt, ai_overview, ai_mode, perplexity, gemini, naver_ai, baidu_ai, naver_ai_tab, qwen, doubao, bing_ai_mode and bing_ai_overview are accepted: any other value, including another model enabled for the API key's user, returns 422 ERR_INVALID_PARAM (invalid model). One of those twelve that the user has not enabled also returns 422 ERR_INVALID_PARAM, with the valid values in the message.
$collection_id = 12,34; // string | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize.
$country_code = 'country_code_example'; // string | One ISO country code or a comma-separated list (e.g. US,GB,DE)
$language_code = 'language_code_example'; // string | One ISO language code or a comma-separated list (e.g. en,es,de)
$prompt = 56; // int | Filter by prompt ID. An id that is not a plain positive number, or that names no prompt of the project, returns 422 ERR_INVALID_PARAM.
$brand_kind = 'brand_kind_example'; // string | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default.
$from = new \DateTime('2013-10-20T19:20:30+01:00'); // \DateTime
$to = new \DateTime('2013-10-20T19:20:30+01:00'); // \DateTime | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier.
$key = 'key_example'; // string | Return only this group of the chosen view: a domain (view=domain), a host (view=host) or a cited URL exactly as listed (view=url). Domains and hosts match case-insensitively, without www. A view=url key is one raw URL, so its variants (a tracking parameter, a trailing slash) stay separate rows; GET /citation_intelligence/urls/{url_sha256} merges them, as the app does. No match returns an empty list (total 0), not an error.
$include_series = false; // bool | Requires key, else 422 ERR_INVALID_PARAM. Adds citation_series to the group's row.
$query = 'query_example'; // string
$source_type = 'source_type_example'; // string
$sentiment = 'sentiment_example'; // string | Keeps the citations of answers with a negative brand sentiment. Needs the Growth plan or above: below it the filter answers 403 ERR_PLAN_REQUIRED.
$content_gap = 'content_gap_example'; // string | mentioned: the cited page mentions your brand. gap: it mentions a competitor but not your brand. Only pages with usable content whose mention analysis has completed for this project match.

try {
    $result = $apiInstance->listCitationGroups($project_id, $view, $page, $per_page, $order, $direction, $model, $collection_id, $country_code, $language_code, $prompt, $brand_kind, $from, $to, $key, $include_series, $query, $source_type, $sentiment, $content_gap);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling SourcesCitationIntelligenceApi->listCitationGroups: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **project_id** | **int**| Project ID | |
| **view** | **string**|  | [optional] [default to &#39;url&#39;] |
| **page** | **int**|  | [optional] [default to 1] |
| **per_page** | **int**|  | [optional] [default to 20] |
| **order** | **string**|  | [optional] |
| **direction** | **string**|  | [optional] |
| **model** | **string**| Filter by one AI model. Only chatgpt, ai_overview, ai_mode, perplexity, gemini, naver_ai, baidu_ai, naver_ai_tab, qwen, doubao, bing_ai_mode and bing_ai_overview are accepted: any other value, including another model enabled for the API key&#39;s user, returns 422 ERR_INVALID_PARAM (invalid model). One of those twelve that the user has not enabled also returns 422 ERR_INVALID_PARAM, with the valid values in the message. | [optional] |
| **collection_id** | **string**| One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize. | [optional] |
| **country_code** | **string**| One ISO country code or a comma-separated list (e.g. US,GB,DE) | [optional] |
| **language_code** | **string**| One ISO language code or a comma-separated list (e.g. en,es,de) | [optional] |
| **prompt** | **int**| Filter by prompt ID. An id that is not a plain positive number, or that names no prompt of the project, returns 422 ERR_INVALID_PARAM. | [optional] |
| **brand_kind** | **string**| Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. | [optional] |
| **from** | **\DateTime**|  | [optional] |
| **to** | **\DateTime**| End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. | [optional] |
| **key** | **string**| Return only this group of the chosen view: a domain (view&#x3D;domain), a host (view&#x3D;host) or a cited URL exactly as listed (view&#x3D;url). Domains and hosts match case-insensitively, without www. A view&#x3D;url key is one raw URL, so its variants (a tracking parameter, a trailing slash) stay separate rows; GET /citation_intelligence/urls/{url_sha256} merges them, as the app does. No match returns an empty list (total 0), not an error. | [optional] |
| **include_series** | **bool**| Requires key, else 422 ERR_INVALID_PARAM. Adds citation_series to the group&#39;s row. | [optional] [default to false] |
| **query** | **string**|  | [optional] |
| **source_type** | **string**|  | [optional] |
| **sentiment** | **string**| Keeps the citations of answers with a negative brand sentiment. Needs the Growth plan or above: below it the filter answers 403 ERR_PLAN_REQUIRED. | [optional] |
| **content_gap** | **string**| mentioned: the cited page mentions your brand. gap: it mentions a competitor but not your brand. Only pages with usable content whose mention analysis has completed for this project match. | [optional] |

### Return type

[**\LLMPulse\Model\CitationGroupsResponse**](../Model/CitationGroupsResponse.md)

### Authorization

[BearerAuth](../../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `listCitedUrlOccurrences()`

```php
listCitedUrlOccurrences($project_id, $url_sha256, $page, $per_page, $sentiment): \LLMPulse\Model\CitedUrlOccurrencesResponse
```

Cited URL occurrences

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: BearerAuth
$config = LLMPulse\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new LLMPulse\Api\SourcesCitationIntelligenceApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$project_id = 56; // int | Project ID
$url_sha256 = 'url_sha256_example'; // string | 64-character hex SHA-256 of the cited URL
$page = 1; // int
$per_page = 20; // int
$sentiment = 'sentiment_example'; // string | Keeps the occurrences in answers with a negative brand sentiment. Needs the Growth plan or above: below it the filter answers 403 ERR_PLAN_REQUIRED.

try {
    $result = $apiInstance->listCitedUrlOccurrences($project_id, $url_sha256, $page, $per_page, $sentiment);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling SourcesCitationIntelligenceApi->listCitedUrlOccurrences: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **project_id** | **int**| Project ID | |
| **url_sha256** | **string**| 64-character hex SHA-256 of the cited URL | |
| **page** | **int**|  | [optional] [default to 1] |
| **per_page** | **int**|  | [optional] [default to 20] |
| **sentiment** | **string**| Keeps the occurrences in answers with a negative brand sentiment. Needs the Growth plan or above: below it the filter answers 403 ERR_PLAN_REQUIRED. | [optional] |

### Return type

[**\LLMPulse\Model\CitedUrlOccurrencesResponse**](../Model/CitedUrlOccurrencesResponse.md)

### Authorization

[BearerAuth](../../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `listSources()`

```php
listSources($project_id, $page, $per_page, $model, $collection_id, $country_code, $language_code, $prompt, $from, $to, $source_type, $mention_filter, $competitors, $output, $prompt_type, $brand_kind, $range): \LLMPulse\Model\SourcesResponse
```

List source URLs

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: BearerAuth
$config = LLMPulse\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new LLMPulse\Api\SourcesCitationIntelligenceApi(
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
$prompt = 56; // int | Filter by prompt ID. An id that is not a plain positive number, or that names no prompt of the project, returns 422 ERR_INVALID_PARAM.
$from = new \DateTime('2013-10-20T19:20:30+01:00'); // \DateTime | Start of the window. Sent alone, the window runs from it to the end of today. A from later than to, or a window longer than 1,500 days, returns 422 ERR_INVALID_PARAM.
$to = new \DateTime('2013-10-20T19:20:30+01:00'); // \DateTime | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. Sent without from, the window covers the 30 days that end on it.
$source_type = 'source_type_example'; // string | Filter by source ownership. Owned and competitor matching honor the project's exact-subdomain setting. Any other value, including a differently cased one, returns ERR_INVALID_PARAM.
$mention_filter = 'mention_filter_example'; // string | Filter by which brands are mentioned, as a two-axis matrix (your brand x competitors): mentions_you / not_mentions_you, mentions_competitor / not_mentions_competitor, and the four combined cells you_and_competitor, competitor_not_you (a rival wins and you are absent), you_not_competitor, no_brands (no tracked brand appears, i.e. open space; on answers, finished answers only). Combine with 'competitors' to narrow the competitor side to specific rivals; on a negative cell that reads 'none of these'. On /dimensions/sources it applies to the crawled content of each cited page instead of the answer text. The legacy value 'competitors_only' is still accepted as an alias of competitor_not_you.
$competitors = 'competitors_example'; // string | Comma-separated competitor IDs (a malformed or unknown ID returns ERR_INVALID_PARAM)
$output = 'output_example'; // string | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
$prompt_type = 'prompt_type_example'; // string | One prompt type or a comma-separated list: informational, navigational, commercial, transactional
$brand_kind = 'brand_kind_example'; // string | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default.
$range = 56; // int | Number of days to look back (alternative to from/to, which win when both are given). A value that is not a plain positive number returns 422 ERR_INVALID_PARAM, even beside from/to.

try {
    $result = $apiInstance->listSources($project_id, $page, $per_page, $model, $collection_id, $country_code, $language_code, $prompt, $from, $to, $source_type, $mention_filter, $competitors, $output, $prompt_type, $brand_kind, $range);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling SourcesCitationIntelligenceApi->listSources: ', $e->getMessage(), PHP_EOL;
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
| **prompt** | **int**| Filter by prompt ID. An id that is not a plain positive number, or that names no prompt of the project, returns 422 ERR_INVALID_PARAM. | [optional] |
| **from** | **\DateTime**| Start of the window. Sent alone, the window runs from it to the end of today. A from later than to, or a window longer than 1,500 days, returns 422 ERR_INVALID_PARAM. | [optional] |
| **to** | **\DateTime**| End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. Sent without from, the window covers the 30 days that end on it. | [optional] |
| **source_type** | **string**| Filter by source ownership. Owned and competitor matching honor the project&#39;s exact-subdomain setting. Any other value, including a differently cased one, returns ERR_INVALID_PARAM. | [optional] |
| **mention_filter** | **string**| Filter by which brands are mentioned, as a two-axis matrix (your brand x competitors): mentions_you / not_mentions_you, mentions_competitor / not_mentions_competitor, and the four combined cells you_and_competitor, competitor_not_you (a rival wins and you are absent), you_not_competitor, no_brands (no tracked brand appears, i.e. open space; on answers, finished answers only). Combine with &#39;competitors&#39; to narrow the competitor side to specific rivals; on a negative cell that reads &#39;none of these&#39;. On /dimensions/sources it applies to the crawled content of each cited page instead of the answer text. The legacy value &#39;competitors_only&#39; is still accepted as an alias of competitor_not_you. | [optional] |
| **competitors** | **string**| Comma-separated competitor IDs (a malformed or unknown ID returns ERR_INVALID_PARAM) | [optional] |
| **output** | **string**| Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] |
| **prompt_type** | **string**| One prompt type or a comma-separated list: informational, navigational, commercial, transactional | [optional] |
| **brand_kind** | **string**| Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. | [optional] |
| **range** | **int**| Number of days to look back (alternative to from/to, which win when both are given). A value that is not a plain positive number returns 422 ERR_INVALID_PARAM, even beside from/to. | [optional] |

### Return type

[**\LLMPulse\Model\SourcesResponse**](../Model/SourcesResponse.md)

### Authorization

[BearerAuth](../../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `listUrlLists()`

```php
listUrlLists($project_id, $model, $collection_id, $country_code, $language_code, $prompt, $brand_kind, $from, $to, $range): \LLMPulse\Model\UrlListsResponse
```

List URL lists

A URL list is a named set of rules, each an exact URL (matched over http and https, with or without www), a URL prefix (every page under host/path) or a domain (the site and its subdomains). Its numbers count the AI answers to the prompts tracked in the project: cited_entries is the entries an answer cited in the window and citations the answers citing any entry, each once. Without from/to or range the window is all time. Requires the Growth plan; lower tiers receive ERR_PLAN_REQUIRED.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: BearerAuth
$config = LLMPulse\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new LLMPulse\Api\SourcesCitationIntelligenceApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$project_id = 56; // int | Project ID
$model = 'model_example'; // string | Filter by one AI model. Only chatgpt, ai_overview, ai_mode, perplexity, gemini, naver_ai, baidu_ai, naver_ai_tab, qwen, doubao, bing_ai_mode and bing_ai_overview are accepted: any other value, including another model enabled for the API key's user, returns 422 ERR_INVALID_PARAM (invalid model). One of those twelve that the user has not enabled also returns 422 ERR_INVALID_PARAM, with the valid values in the message.
$collection_id = 12,34; // string | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize.
$country_code = 'country_code_example'; // string | One ISO country code or a comma-separated list (e.g. US,GB,DE)
$language_code = 'language_code_example'; // string | One ISO language code or a comma-separated list (e.g. en,es,de)
$prompt = 56; // int | Filter by prompt ID. An id that is not a plain positive number, or that names no prompt of the project, returns 422 ERR_INVALID_PARAM.
$brand_kind = 'brand_kind_example'; // string | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default.
$from = new \DateTime('2013-10-20T19:20:30+01:00'); // \DateTime
$to = new \DateTime('2013-10-20T19:20:30+01:00'); // \DateTime | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier.
$range = 56; // int | Number of days to look back (alternative to from/to, which win when both are given). A value that is not a plain positive number returns 422 ERR_INVALID_PARAM, even beside from/to.

try {
    $result = $apiInstance->listUrlLists($project_id, $model, $collection_id, $country_code, $language_code, $prompt, $brand_kind, $from, $to, $range);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling SourcesCitationIntelligenceApi->listUrlLists: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **project_id** | **int**| Project ID | |
| **model** | **string**| Filter by one AI model. Only chatgpt, ai_overview, ai_mode, perplexity, gemini, naver_ai, baidu_ai, naver_ai_tab, qwen, doubao, bing_ai_mode and bing_ai_overview are accepted: any other value, including another model enabled for the API key&#39;s user, returns 422 ERR_INVALID_PARAM (invalid model). One of those twelve that the user has not enabled also returns 422 ERR_INVALID_PARAM, with the valid values in the message. | [optional] |
| **collection_id** | **string**| One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize. | [optional] |
| **country_code** | **string**| One ISO country code or a comma-separated list (e.g. US,GB,DE) | [optional] |
| **language_code** | **string**| One ISO language code or a comma-separated list (e.g. en,es,de) | [optional] |
| **prompt** | **int**| Filter by prompt ID. An id that is not a plain positive number, or that names no prompt of the project, returns 422 ERR_INVALID_PARAM. | [optional] |
| **brand_kind** | **string**| Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. | [optional] |
| **from** | **\DateTime**|  | [optional] |
| **to** | **\DateTime**| End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. | [optional] |
| **range** | **int**| Number of days to look back (alternative to from/to, which win when both are given). A value that is not a plain positive number returns 422 ERR_INVALID_PARAM, even beside from/to. | [optional] |

### Return type

[**\LLMPulse\Model\UrlListsResponse**](../Model/UrlListsResponse.md)

### Authorization

[BearerAuth](../../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `removeUrlListEntries()`

```php
removeUrlListEntries($id, $url_list_entries_remove_request): \LLMPulse\Model\UrlListEntriesRemoveResponse
```

Remove entries from a URL list

Removes entries by id (from GET /url_lists/{id}) or by value as written (\"https://acme.com/a\", \"acme.com/blog/_*\", \"acme.com\"). Sending neither answers ERR_INVALID_PARAM. Requires a `read_write` scope API key and the Growth plan.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: BearerAuth
$config = LLMPulse\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new LLMPulse\Api\SourcesCitationIntelligenceApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 56; // int
$url_list_entries_remove_request = new \LLMPulse\Model\UrlListEntriesRemoveRequest(); // \LLMPulse\Model\UrlListEntriesRemoveRequest

try {
    $result = $apiInstance->removeUrlListEntries($id, $url_list_entries_remove_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling SourcesCitationIntelligenceApi->removeUrlListEntries: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **int**|  | |
| **url_list_entries_remove_request** | [**\LLMPulse\Model\UrlListEntriesRemoveRequest**](../Model/UrlListEntriesRemoveRequest.md)|  | |

### Return type

[**\LLMPulse\Model\UrlListEntriesRemoveResponse**](../Model/UrlListEntriesRemoveResponse.md)

### Authorization

[BearerAuth](../../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `updateUrlList()`

```php
updateUrlList($id, $url_list_update_request): \LLMPulse\Model\UrlListUpdateResponse
```

Update a URL list

Changes the name, description or currency of a URL list. Entries are added with POST /url_lists/{id}/entries and removed with POST /url_lists/{id}/entries/remove. Requires a `read_write` scope API key and the Growth plan.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: BearerAuth
$config = LLMPulse\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new LLMPulse\Api\SourcesCitationIntelligenceApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 56; // int
$url_list_update_request = new \LLMPulse\Model\UrlListUpdateRequest(); // \LLMPulse\Model\UrlListUpdateRequest

try {
    $result = $apiInstance->updateUrlList($id, $url_list_update_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling SourcesCitationIntelligenceApi->updateUrlList: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **int**|  | |
| **url_list_update_request** | [**\LLMPulse\Model\UrlListUpdateRequest**](../Model/UrlListUpdateRequest.md)|  | |

### Return type

[**\LLMPulse\Model\UrlListUpdateResponse**](../Model/UrlListUpdateResponse.md)

### Authorization

[BearerAuth](../../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
