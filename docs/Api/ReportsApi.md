# LLMPulse\ReportsApi



All URIs are relative to https://api.llmpulse.ai/api/v1, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**createTechnicalGeoReports()**](ReportsApi.md#createTechnicalGeoReports) | **POST** /technical_geo_reports | Run technical GEO analysis |


## `createTechnicalGeoReports()`

```php
createTechnicalGeoReports($create_technical_geo_reports_request)
```

Run technical GEO analysis

Launches the full technical GEO analysis bundle (crawlability, schema, content readiness, discoverability, site structure, robots.txt, llms.txt, AI visibility) for a URL + country. Each report runs in a background job. Requires a `read_write` scope API key.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: BearerAuth
$config = LLMPulse\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new LLMPulse\Api\ReportsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$create_technical_geo_reports_request = new \LLMPulse\Model\CreateTechnicalGeoReportsRequest(); // \LLMPulse\Model\CreateTechnicalGeoReportsRequest

try {
    $apiInstance->createTechnicalGeoReports($create_technical_geo_reports_request);
} catch (Exception $e) {
    echo 'Exception when calling ReportsApi->createTechnicalGeoReports: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **create_technical_geo_reports_request** | [**\LLMPulse\Model\CreateTechnicalGeoReportsRequest**](../Model/CreateTechnicalGeoReportsRequest.md)|  | |

### Return type

void (empty response body)

### Authorization

[BearerAuth](../../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
