# LLMPulse\TechnicalGEOReportsApi



All URIs are relative to https://api.llmpulse.ai/api/v1, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**createTechnicalGeoReports()**](TechnicalGEOReportsApi.md#createTechnicalGeoReports) | **POST** /technical_geo_reports | Run technical GEO analysis |
| [**getTechnicalGeoReport()**](TechnicalGEOReportsApi.md#getTechnicalGeoReport) | **GET** /technical_geo_reports/{id} | Get a technical GEO report |
| [**listTechnicalGeoReports()**](TechnicalGEOReportsApi.md#listTechnicalGeoReports) | **GET** /technical_geo_reports | List technical GEO reports |


## `createTechnicalGeoReports()`

```php
createTechnicalGeoReports($create_technical_geo_reports_request)
```

Run technical GEO analysis

Launches the full technical GEO analysis bundle (crawlability, schema, content readiness, discoverability, site structure, robots.txt, agent readiness, llms.txt, AI visibility) for a URL + country. Each report runs in a background job. Requires a `read_write` scope API key.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: BearerAuth
$config = LLMPulse\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new LLMPulse\Api\TechnicalGEOReportsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$create_technical_geo_reports_request = new \LLMPulse\Model\CreateTechnicalGeoReportsRequest(); // \LLMPulse\Model\CreateTechnicalGeoReportsRequest

try {
    $apiInstance->createTechnicalGeoReports($create_technical_geo_reports_request);
} catch (Exception $e) {
    echo 'Exception when calling TechnicalGEOReportsApi->createTechnicalGeoReports: ', $e->getMessage(), PHP_EOL;
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

## `getTechnicalGeoReport()`

```php
getTechnicalGeoReport($project_id, $report_type, $id)
```

Get a technical GEO report

Returns the current status and the full result_data once the report is completed. While it is running, result_data is null and poll_after_seconds tells clients when to check again.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: BearerAuth
$config = LLMPulse\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new LLMPulse\Api\TechnicalGEOReportsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$project_id = 56; // int | Project ID
$report_type = 'report_type_example'; // string
$id = 56; // int | Report id returned by POST /technical_geo_reports or GET /technical_geo_reports

try {
    $apiInstance->getTechnicalGeoReport($project_id, $report_type, $id);
} catch (Exception $e) {
    echo 'Exception when calling TechnicalGEOReportsApi->getTechnicalGeoReport: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **project_id** | **int**| Project ID | |
| **report_type** | **string**|  | |
| **id** | **int**| Report id returned by POST /technical_geo_reports or GET /technical_geo_reports | |

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

## `listTechnicalGeoReports()`

```php
listTechnicalGeoReports($project_id, $report_type, $status, $batch_id, $page, $per_page)
```

List technical GEO reports

Lists reports of one technical GEO type for a project, newest first. Use agent_readiness for the AI/Agent Readiness report.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: BearerAuth
$config = LLMPulse\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new LLMPulse\Api\TechnicalGEOReportsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$project_id = 56; // int | Project ID
$report_type = 'report_type_example'; // string
$status = 'status_example'; // string | Optional status filter; valid values depend on report_type
$batch_id = 56; // int | Optional batch id returned when the report bundle was created
$page = 1; // int
$per_page = 20; // int

try {
    $apiInstance->listTechnicalGeoReports($project_id, $report_type, $status, $batch_id, $page, $per_page);
} catch (Exception $e) {
    echo 'Exception when calling TechnicalGEOReportsApi->listTechnicalGeoReports: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **project_id** | **int**| Project ID | |
| **report_type** | **string**|  | |
| **status** | **string**| Optional status filter; valid values depend on report_type | [optional] |
| **batch_id** | **int**| Optional batch id returned when the report bundle was created | [optional] |
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
