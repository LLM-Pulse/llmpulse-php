# LLMPulse\CustomReportsApi



All URIs are relative to https://api.llmpulse.ai/api/v1, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**getCustomReport()**](CustomReportsApi.md#getCustomReport) | **GET** /custom_reports/{id} | Get a custom report with its widget data |
| [**listCustomReports()**](CustomReportsApi.md#listCustomReports) | **GET** /custom_reports | List custom reports |
| [**sendCustomReport()**](CustomReportsApi.md#sendCustomReport) | **POST** /custom_reports/{id}/send | Send a custom report now |


## `getCustomReport()`

```php
getCustomReport($project_id, $id): \LLMPulse\Model\CustomReportDetailResponse
```

Get a custom report with its widget data

The configuration of one custom report (date range, filters, schedule, layout) and the data of every widget computed for today, the same numbers the report page, its shared link and its PDF show. Each widget carries its `kind` and a `data` object shaped by it: `series` for `timeseries`, `slices` for `donut`, `bars` for `bar`, `values` and `changes` for `kpi_grid`, `rows` for `table`. A widget whose data source is not connected has `available: false` and `data: null`. Nothing is saved or sent. Requires the Scale plan or above.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: BearerAuth
$config = LLMPulse\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new LLMPulse\Api\CustomReportsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$project_id = 56; // int | Project ID
$id = 56; // int | Custom report id, from GET /custom_reports

try {
    $result = $apiInstance->getCustomReport($project_id, $id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling CustomReportsApi->getCustomReport: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **project_id** | **int**| Project ID | |
| **id** | **int**| Custom report id, from GET /custom_reports | |

### Return type

[**\LLMPulse\Model\CustomReportDetailResponse**](../Model/CustomReportDetailResponse.md)

### Authorization

[BearerAuth](../../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `listCustomReports()`

```php
listCustomReports($project_id, $page, $per_page, $output): \LLMPulse\Model\CustomReportsResponse
```

List custom reports

The custom reports of the project, newest first, as the Reports > Custom Reports list shows them. Recipient addresses, the shared-link token and the password are never returned. Requires the Scale plan or above.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: BearerAuth
$config = LLMPulse\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new LLMPulse\Api\CustomReportsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$project_id = 56; // int | Project ID
$page = 1; // int
$per_page = 20; // int
$output = 'output_example'; // string | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.

try {
    $result = $apiInstance->listCustomReports($project_id, $page, $per_page, $output);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling CustomReportsApi->listCustomReports: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **project_id** | **int**| Project ID | |
| **page** | **int**|  | [optional] [default to 1] |
| **per_page** | **int**|  | [optional] [default to 20] |
| **output** | **string**| Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] |

### Return type

[**\LLMPulse\Model\CustomReportsResponse**](../Model/CustomReportsResponse.md)

### Authorization

[BearerAuth](../../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `sendCustomReport()`

```php
sendCustomReport($id, $send_custom_report_request): \LLMPulse\Model\CustomReportSendResponse
```

Send a custom report now

Queues the report's PDF for its recipients, like the Send now button on the report page: the report must be published and have at least one recipient (ERR_INVALID_PARAM otherwise), and each report can be sent once every 10 minutes (429 ERR_RATE_LIMITED with Retry-After). Not available from a white-label portal or for a report made inside one (ERR_INTEGRATION_UNAVAILABLE). Requires the Scale plan or above, a `read_write` scope API key and, for team members, update permission on Custom Reports.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: BearerAuth
$config = LLMPulse\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new LLMPulse\Api\CustomReportsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 56; // int | Custom report id, from GET /custom_reports
$send_custom_report_request = new \LLMPulse\Model\SendCustomReportRequest(); // \LLMPulse\Model\SendCustomReportRequest

try {
    $result = $apiInstance->sendCustomReport($id, $send_custom_report_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling CustomReportsApi->sendCustomReport: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **int**| Custom report id, from GET /custom_reports | |
| **send_custom_report_request** | [**\LLMPulse\Model\SendCustomReportRequest**](../Model/SendCustomReportRequest.md)|  | |

### Return type

[**\LLMPulse\Model\CustomReportSendResponse**](../Model/CustomReportSendResponse.md)

### Authorization

[BearerAuth](../../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
