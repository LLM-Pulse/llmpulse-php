# LLMPulse\SentimentsApi

Per-execution sentiment analysis records

All URIs are relative to https://api.llmpulse.ai/api/v1, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**listSentimentRecords()**](SentimentsApi.md#listSentimentRecords) | **GET** /sentiments | List sentiment records |


## `listSentimentRecords()`

```php
listSentimentRecords($project_id, $competitor_id, $brand_only, $analysis, $model, $collection_id, $country_code, $language_code, $from, $to, $page, $per_page)
```

List sentiment records

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
$analysis = 'analysis_example'; // string
$model = 'model_example'; // string | Filter by AI model. Models the API key's user has not enabled are silently dropped.
$collection_id = 56; // int
$country_code = 'country_code_example'; // string | ISO country code (e.g. US, GB, DE)
$language_code = 'language_code_example'; // string | ISO language code (e.g. en, es, de)
$from = new \DateTime('2013-10-20T19:20:30+01:00'); // \DateTime
$to = new \DateTime('2013-10-20T19:20:30+01:00'); // \DateTime
$page = 1; // int
$per_page = 20; // int

try {
    $apiInstance->listSentimentRecords($project_id, $competitor_id, $brand_only, $analysis, $model, $collection_id, $country_code, $language_code, $from, $to, $page, $per_page);
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
| **analysis** | **string**|  | [optional] |
| **model** | **string**| Filter by AI model. Models the API key&#39;s user has not enabled are silently dropped. | [optional] |
| **collection_id** | **int**|  | [optional] |
| **country_code** | **string**| ISO country code (e.g. US, GB, DE) | [optional] |
| **language_code** | **string**| ISO language code (e.g. en, es, de) | [optional] |
| **from** | **\DateTime**|  | [optional] |
| **to** | **\DateTime**|  | [optional] |
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
