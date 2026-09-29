# LLMPulse\TechnicalGEOReportsApi



All URIs are relative to https://api.llmpulse.ai/api/v1, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**createTechnicalGeoReports()**](TechnicalGEOReportsApi.md#createTechnicalGeoReports) | **POST** /technical_geo_reports | Run technical GEO analysis |
| [**getTechnicalGeoReport()**](TechnicalGEOReportsApi.md#getTechnicalGeoReport) | **GET** /technical_geo_reports/{id} | Get a technical GEO report |
| [**listTechnicalGeoReports()**](TechnicalGEOReportsApi.md#listTechnicalGeoReports) | **GET** /technical_geo_reports | List technical GEO reports |
| [**revertTechnicalGeoReportContent()**](TechnicalGEOReportsApi.md#revertTechnicalGeoReportContent) | **POST** /technical_geo_reports/{id}/revert_content | Revert llms.txt report content |
| [**updateTechnicalGeoReportContent()**](TechnicalGEOReportsApi.md#updateTechnicalGeoReportContent) | **PATCH** /technical_geo_reports/{id}/content | Edit llms.txt report content |


## `createTechnicalGeoReports()`

```php
createTechnicalGeoReports($create_technical_geo_reports_request)
```

Run technical GEO analysis

Launches the full nine-report technical GEO analysis bundle for a URL + country. The bundle starts only when at least nine daily units remain. Each successfully created report uses one unit; a report that is not created uses none. Daily allocations vary by account. Each report runs in a background job. Requires a `read_write` scope API key.

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

Returns the current status and the full result_data once the report is completed. While it is running, result_data is null and poll_after_seconds tells clients when to check again. Summaries carry output_language_code (the ISO 639-1 code an llms_txt report was requested in; null for an llms_txt report written in the website's own language, requested as auto or chosen in the app, and for every other report type); a completed llms_txt result_data also returns content_version (send it back to PATCH /technical_geo_reports/{id}/content), manually_edited_at, original_llms_txt_content and original_llms_full_txt_content (the generated files, kept from the first manual edit in the app, the API or MCP) and metadata.output_language_code.

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

## `revertTechnicalGeoReportContent()`

```php
revertTechnicalGeoReportContent($id, $technical_geo_report_content_revert_request): \LLMPulse\Model\LlmsTxtTechnicalGeoReport
```

Revert llms.txt report content

Discards every manual edit on the llms_txt report and restores the llms.txt and llms-full.txt files exactly as they were generated. Returns ERR_INVALID_PARAM when the report has no manual edits or report_type is not llms_txt. Requires a `read_write` scope API key and, for team members, create permission on GEO Optimization.

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
$id = 56; // int | Report id returned by POST /technical_geo_reports or GET /technical_geo_reports
$technical_geo_report_content_revert_request = new \LLMPulse\Model\TechnicalGeoReportContentRevertRequest(); // \LLMPulse\Model\TechnicalGeoReportContentRevertRequest

try {
    $result = $apiInstance->revertTechnicalGeoReportContent($id, $technical_geo_report_content_revert_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling TechnicalGEOReportsApi->revertTechnicalGeoReportContent: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **int**| Report id returned by POST /technical_geo_reports or GET /technical_geo_reports | |
| **technical_geo_report_content_revert_request** | [**\LLMPulse\Model\TechnicalGeoReportContentRevertRequest**](../Model/TechnicalGeoReportContentRevertRequest.md)|  | |

### Return type

[**\LLMPulse\Model\LlmsTxtTechnicalGeoReport**](../Model/LlmsTxtTechnicalGeoReport.md)

### Authorization

[BearerAuth](../../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `updateTechnicalGeoReportContent()`

```php
updateTechnicalGeoReportContent($id, $technical_geo_report_content_update_request): \LLMPulse\Model\TechnicalGeoReportContentUpdateResponse
```

Edit llms.txt report content

Replaces the llms.txt and llms-full.txt files of a completed llms_txt report in place, without generating them again. `edits` maps llms_txt and/or llms_full_txt to the full replacement text. `content_version` must equal result_data.content_version of the report as last read; when the report changed since, the edit is refused as stale and the message names the current version. A missing or stale content_version, a blank file, a file over 200,000 characters, a value that is not text, an unknown file key, an empty `edits` object, a report that has not completed or a report_type other than llms_txt is rejected with ERR_INVALID_PARAM and nothing is written. Files are stored with Unix line endings and one trailing newline. A file identical to the stored one is ignored, and the response lists the files that actually changed. The first edit keeps the generated files in original_llms_txt_content and original_llms_full_txt_content so POST /technical_geo_reports/{id}/revert_content can restore them; running the report again creates a new report without these edits. Requires a `read_write` scope API key and, for team members, create permission on GEO Optimization.

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
$id = 56; // int | Report id returned by POST /technical_geo_reports or GET /technical_geo_reports
$technical_geo_report_content_update_request = new \LLMPulse\Model\TechnicalGeoReportContentUpdateRequest(); // \LLMPulse\Model\TechnicalGeoReportContentUpdateRequest

try {
    $result = $apiInstance->updateTechnicalGeoReportContent($id, $technical_geo_report_content_update_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling TechnicalGEOReportsApi->updateTechnicalGeoReportContent: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **int**| Report id returned by POST /technical_geo_reports or GET /technical_geo_reports | |
| **technical_geo_report_content_update_request** | [**\LLMPulse\Model\TechnicalGeoReportContentUpdateRequest**](../Model/TechnicalGeoReportContentUpdateRequest.md)|  | |

### Return type

[**\LLMPulse\Model\TechnicalGeoReportContentUpdateResponse**](../Model/TechnicalGeoReportContentUpdateResponse.md)

### Authorization

[BearerAuth](../../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
