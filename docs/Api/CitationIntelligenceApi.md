# LLMPulse\CitationIntelligenceApi



All URIs are relative to https://api.llmpulse.ai/api/v1, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**getCitedUrlContent()**](CitationIntelligenceApi.md#getCitedUrlContent) | **GET** /citation_intelligence/urls/{url_sha256}/content | Cited URL cached content |
| [**getCitedUrlDetail()**](CitationIntelligenceApi.md#getCitedUrlDetail) | **GET** /citation_intelligence/urls/{url_sha256} | Cited URL detail |
| [**getMentionsByCitingDomain()**](CitationIntelligenceApi.md#getMentionsByCitingDomain) | **GET** /citation_intelligence/mentions_by_domain | Mention share by citing domain |
| [**listCitationGroups()**](CitationIntelligenceApi.md#listCitationGroups) | **GET** /citation_intelligence/groups | Grouped citation intelligence |
| [**listCitedUrlOccurrences()**](CitationIntelligenceApi.md#listCitedUrlOccurrences) | **GET** /citation_intelligence/urls/{url_sha256}/occurrences | Cited URL occurrences |


## `getCitedUrlContent()`

```php
getCitedUrlContent($project_id, $url_sha256)
```

Cited URL cached content

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: BearerAuth
$config = LLMPulse\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new LLMPulse\Api\CitationIntelligenceApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$project_id = 56; // int | Project ID
$url_sha256 = 'url_sha256_example'; // string | 64-character hex SHA-256 of the cited URL

try {
    $apiInstance->getCitedUrlContent($project_id, $url_sha256);
} catch (Exception $e) {
    echo 'Exception when calling CitationIntelligenceApi->getCitedUrlContent: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **project_id** | **int**| Project ID | |
| **url_sha256** | **string**| 64-character hex SHA-256 of the cited URL | |

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

## `getCitedUrlDetail()`

```php
getCitedUrlDetail($project_id, $url_sha256)
```

Cited URL detail

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: BearerAuth
$config = LLMPulse\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new LLMPulse\Api\CitationIntelligenceApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$project_id = 56; // int | Project ID
$url_sha256 = 'url_sha256_example'; // string | 64-character hex SHA-256 of the cited URL

try {
    $apiInstance->getCitedUrlDetail($project_id, $url_sha256);
} catch (Exception $e) {
    echo 'Exception when calling CitationIntelligenceApi->getCitedUrlDetail: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **project_id** | **int**| Project ID | |
| **url_sha256** | **string**| 64-character hex SHA-256 of the cited URL | |

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

## `getMentionsByCitingDomain()`

```php
getMentionsByCitingDomain($project_id, $domains, $model, $collection_id, $country_code, $language_code, $prompt, $from, $to)
```

Mention share by citing domain

For the responses where each given source domain is cited, returns the share of those responses that mention the brand vs each competitor (brand + competitors sum to 100% per domain). Pass multiple domains to get the whole matrix in one call.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: BearerAuth
$config = LLMPulse\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new LLMPulse\Api\CitationIntelligenceApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$project_id = 56; // int | Project ID
$domains = array('domains_example'); // string[] | Source domains to analyze, e.g. domains[]=gmac.com&domains[]=educaweb.com
$model = 'model_example'; // string | Filter by AI model. Models the API key's user has not enabled are silently dropped.
$collection_id = 56; // int
$country_code = 'country_code_example'; // string | ISO country code (e.g. US, GB, DE)
$language_code = 'language_code_example'; // string | ISO language code (e.g. en, es, de)
$prompt = 56; // int | Filter by prompt ID
$from = new \DateTime('2013-10-20T19:20:30+01:00'); // \DateTime
$to = new \DateTime('2013-10-20T19:20:30+01:00'); // \DateTime

try {
    $apiInstance->getMentionsByCitingDomain($project_id, $domains, $model, $collection_id, $country_code, $language_code, $prompt, $from, $to);
} catch (Exception $e) {
    echo 'Exception when calling CitationIntelligenceApi->getMentionsByCitingDomain: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **project_id** | **int**| Project ID | |
| **domains** | [**string[]**](../Model/string.md)| Source domains to analyze, e.g. domains[]&#x3D;gmac.com&amp;domains[]&#x3D;educaweb.com | |
| **model** | **string**| Filter by AI model. Models the API key&#39;s user has not enabled are silently dropped. | [optional] |
| **collection_id** | **int**|  | [optional] |
| **country_code** | **string**| ISO country code (e.g. US, GB, DE) | [optional] |
| **language_code** | **string**| ISO language code (e.g. en, es, de) | [optional] |
| **prompt** | **int**| Filter by prompt ID | [optional] |
| **from** | **\DateTime**|  | [optional] |
| **to** | **\DateTime**|  | [optional] |

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

## `listCitationGroups()`

```php
listCitationGroups($project_id, $view, $page, $per_page, $order, $direction, $model, $collection_id, $country_code, $language_code, $prompt, $from, $to, $query, $source_type, $sentiment, $content_gap)
```

Grouped citation intelligence

Grouped citation intelligence by url / domain / host with per-model breakdown, citation rate, and avg citation position. Counts and citation rate include visible citations and background source references. Average position ignores rows with position=0. Owned and competitor source matching honor the project's exact-subdomain setting. Filter vocabulary aligns with `source_type` returned by the API.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: BearerAuth
$config = LLMPulse\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new LLMPulse\Api\CitationIntelligenceApi(
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
$model = 'model_example'; // string | Filter by AI model. Models the API key's user has not enabled are silently dropped.
$collection_id = 56; // int
$country_code = 'country_code_example'; // string | ISO country code (e.g. US, GB, DE)
$language_code = 'language_code_example'; // string | ISO language code (e.g. en, es, de)
$prompt = 56; // int | Filter by prompt ID
$from = new \DateTime('2013-10-20T19:20:30+01:00'); // \DateTime
$to = new \DateTime('2013-10-20T19:20:30+01:00'); // \DateTime
$query = 'query_example'; // string
$source_type = 'source_type_example'; // string
$sentiment = 'sentiment_example'; // string
$content_gap = 'content_gap_example'; // string

try {
    $apiInstance->listCitationGroups($project_id, $view, $page, $per_page, $order, $direction, $model, $collection_id, $country_code, $language_code, $prompt, $from, $to, $query, $source_type, $sentiment, $content_gap);
} catch (Exception $e) {
    echo 'Exception when calling CitationIntelligenceApi->listCitationGroups: ', $e->getMessage(), PHP_EOL;
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
| **model** | **string**| Filter by AI model. Models the API key&#39;s user has not enabled are silently dropped. | [optional] |
| **collection_id** | **int**|  | [optional] |
| **country_code** | **string**| ISO country code (e.g. US, GB, DE) | [optional] |
| **language_code** | **string**| ISO language code (e.g. en, es, de) | [optional] |
| **prompt** | **int**| Filter by prompt ID | [optional] |
| **from** | **\DateTime**|  | [optional] |
| **to** | **\DateTime**|  | [optional] |
| **query** | **string**|  | [optional] |
| **source_type** | **string**|  | [optional] |
| **sentiment** | **string**|  | [optional] |
| **content_gap** | **string**|  | [optional] |

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

## `listCitedUrlOccurrences()`

```php
listCitedUrlOccurrences($project_id, $url_sha256, $page, $per_page)
```

Cited URL occurrences

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: BearerAuth
$config = LLMPulse\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new LLMPulse\Api\CitationIntelligenceApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$project_id = 56; // int | Project ID
$url_sha256 = 'url_sha256_example'; // string | 64-character hex SHA-256 of the cited URL
$page = 1; // int
$per_page = 20; // int

try {
    $apiInstance->listCitedUrlOccurrences($project_id, $url_sha256, $page, $per_page);
} catch (Exception $e) {
    echo 'Exception when calling CitationIntelligenceApi->listCitedUrlOccurrences: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **project_id** | **int**| Project ID | |
| **url_sha256** | **string**| 64-character hex SHA-256 of the cited URL | |
| **page** | **int**|  | [optional] [default to 1] |
| **per_page** | **int**|  | [optional] [default to 20] |

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
