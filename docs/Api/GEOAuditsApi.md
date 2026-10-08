# LLMPulse\GEOAuditsApi



All URIs are relative to https://api.llmpulse.ai/api/v1, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**compareGeoAuditRuns()**](GEOAuditsApi.md#compareGeoAuditRuns) | **GET** /geo_audits/{id}/comparison | Compare two GEO audit runs |
| [**createGeoAudits()**](GEOAuditsApi.md#createGeoAudits) | **POST** /geo_audits | Create GEO audits |
| [**deleteGeoAudit()**](GEOAuditsApi.md#deleteGeoAudit) | **DELETE** /geo_audits/{id} | Delete (archive) a GEO audit |
| [**getGeoAudit()**](GEOAuditsApi.md#getGeoAudit) | **GET** /geo_audits/{id} | Get a GEO audit |
| [**getGeoAuditRun()**](GEOAuditsApi.md#getGeoAuditRun) | **GET** /geo_audits/{geo_audit_id}/runs/{sequence} | Get a GEO audit run |
| [**listGeoAlerts()**](GEOAuditsApi.md#listGeoAlerts) | **GET** /geo_alerts | List GEO audit alerts |
| [**listGeoAuditFindings()**](GEOAuditsApi.md#listGeoAuditFindings) | **GET** /geo_audits/{geo_audit_id}/runs/{sequence}/findings | List the findings of a GEO audit run |
| [**listGeoAuditIssues()**](GEOAuditsApi.md#listGeoAuditIssues) | **GET** /geo_audits/{geo_audit_id}/issues | List the issues of a GEO audit |
| [**listGeoAuditRuns()**](GEOAuditsApi.md#listGeoAuditRuns) | **GET** /geo_audits/{geo_audit_id}/runs | List the runs of a GEO audit |
| [**listGeoAudits()**](GEOAuditsApi.md#listGeoAudits) | **GET** /geo_audits | List GEO audits |
| [**runGeoAudit()**](GEOAuditsApi.md#runGeoAudit) | **POST** /geo_audits/{geo_audit_id}/runs | Run a GEO audit now |
| [**updateGeoAudit()**](GEOAuditsApi.md#updateGeoAudit) | **PATCH** /geo_audits/{id} | Update a GEO audit |
| [**updateGeoAuditIssue()**](GEOAuditsApi.md#updateGeoAuditIssue) | **PATCH** /geo_audits/{geo_audit_id}/issues/{id} | Accept or reopen a GEO audit issue |


## `compareGeoAuditRuns()`

```php
compareGeoAuditRuns($project_id, $id, $from_run, $to_run): \LLMPulse\Model\GeoAuditComparison
```

Compare two GEO audit runs

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: BearerAuth
$config = LLMPulse\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new LLMPulse\Api\GEOAuditsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$project_id = 56; // int | Project ID
$id = 'id_example'; // string | Audit id
$from_run = 56; // int | Run number to compare from (default the run before to_run)
$to_run = 56; // int | Run number to compare to (default the latest completed run)

try {
    $result = $apiInstance->compareGeoAuditRuns($project_id, $id, $from_run, $to_run);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling GEOAuditsApi->compareGeoAuditRuns: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **project_id** | **int**| Project ID | |
| **id** | **string**| Audit id | |
| **from_run** | **int**| Run number to compare from (default the run before to_run) | [optional] |
| **to_run** | **int**| Run number to compare to (default the latest completed run) | [optional] |

### Return type

[**\LLMPulse\Model\GeoAuditComparison**](../Model/GeoAuditComparison.md)

### Authorization

[BearerAuth](../../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `createGeoAudits()`

```php
createGeoAudits($geo_audit_create_request): \LLMPulse\Model\GeoAuditCreateResponse
```

Create GEO audits

Creates one audit per entry of audit_types and starts the first run of each (it counts against the manual run limits: 6 per audit per hour, 200 per account per day). cadence weekly or monthly is accepted only for types whose checks are tracked run to run, and counts against the plan limit of active recurring audits (ERR_LIMIT_REACHED). Creating an audit that was archived restores it with its history. Requires a `read_write` scope API key.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: BearerAuth
$config = LLMPulse\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new LLMPulse\Api\GEOAuditsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$geo_audit_create_request = new \LLMPulse\Model\GeoAuditCreateRequest(); // \LLMPulse\Model\GeoAuditCreateRequest

try {
    $result = $apiInstance->createGeoAudits($geo_audit_create_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling GEOAuditsApi->createGeoAudits: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **geo_audit_create_request** | [**\LLMPulse\Model\GeoAuditCreateRequest**](../Model/GeoAuditCreateRequest.md)|  | |

### Return type

[**\LLMPulse\Model\GeoAuditCreateResponse**](../Model/GeoAuditCreateResponse.md)

### Authorization

[BearerAuth](../../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `deleteGeoAudit()`

```php
deleteGeoAudit($project_id, $id): \LLMPulse\Model\GeoAuditArchived
```

Delete (archive) a GEO audit

Archives the audit. Requires a `read_write` scope API key and, for team members, delete permission on GEO Optimization.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: BearerAuth
$config = LLMPulse\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new LLMPulse\Api\GEOAuditsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$project_id = 56; // int | Project ID
$id = 'id_example'; // string | Audit id

try {
    $result = $apiInstance->deleteGeoAudit($project_id, $id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling GEOAuditsApi->deleteGeoAudit: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **project_id** | **int**| Project ID | |
| **id** | **string**| Audit id | |

### Return type

[**\LLMPulse\Model\GeoAuditArchived**](../Model/GeoAuditArchived.md)

### Authorization

[BearerAuth](../../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getGeoAudit()`

```php
getGeoAudit($project_id, $id): \LLMPulse\Model\GeoAuditResponse
```

Get a GEO audit

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: BearerAuth
$config = LLMPulse\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new LLMPulse\Api\GEOAuditsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$project_id = 56; // int | Project ID
$id = 'id_example'; // string | Audit id

try {
    $result = $apiInstance->getGeoAudit($project_id, $id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling GEOAuditsApi->getGeoAudit: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **project_id** | **int**| Project ID | |
| **id** | **string**| Audit id | |

### Return type

[**\LLMPulse\Model\GeoAuditResponse**](../Model/GeoAuditResponse.md)

### Authorization

[BearerAuth](../../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getGeoAuditRun()`

```php
getGeoAuditRun($project_id, $geo_audit_id, $sequence): \LLMPulse\Model\GeoAuditRunDetail
```

Get a GEO audit run

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: BearerAuth
$config = LLMPulse\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new LLMPulse\Api\GEOAuditsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$project_id = 56; // int | Project ID
$geo_audit_id = 'geo_audit_id_example'; // string | Audit id
$sequence = 56; // int | Run number within the audit

try {
    $result = $apiInstance->getGeoAuditRun($project_id, $geo_audit_id, $sequence);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling GEOAuditsApi->getGeoAuditRun: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **project_id** | **int**| Project ID | |
| **geo_audit_id** | **string**| Audit id | |
| **sequence** | **int**| Run number within the audit | |

### Return type

[**\LLMPulse\Model\GeoAuditRunDetail**](../Model/GeoAuditRunDetail.md)

### Authorization

[BearerAuth](../../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `listGeoAlerts()`

```php
listGeoAlerts($project_id, $audit_id, $page, $per_page): \LLMPulse\Model\GeoAlertList
```

List GEO audit alerts

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: BearerAuth
$config = LLMPulse\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new LLMPulse\Api\GEOAuditsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$project_id = 56; // int | Project ID
$audit_id = 'audit_id_example'; // string | Only alerts of this audit
$page = 1; // int
$per_page = 20; // int

try {
    $result = $apiInstance->listGeoAlerts($project_id, $audit_id, $page, $per_page);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling GEOAuditsApi->listGeoAlerts: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **project_id** | **int**| Project ID | |
| **audit_id** | **string**| Only alerts of this audit | [optional] |
| **page** | **int**|  | [optional] [default to 1] |
| **per_page** | **int**|  | [optional] [default to 20] |

### Return type

[**\LLMPulse\Model\GeoAlertList**](../Model/GeoAlertList.md)

### Authorization

[BearerAuth](../../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `listGeoAuditFindings()`

```php
listGeoAuditFindings($project_id, $geo_audit_id, $sequence, $page, $per_page, $output): \LLMPulse\Model\GeoAuditFindingList
```

List the findings of a GEO audit run

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: BearerAuth
$config = LLMPulse\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new LLMPulse\Api\GEOAuditsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$project_id = 56; // int | Project ID
$geo_audit_id = 'geo_audit_id_example'; // string | Audit id
$sequence = 56; // int | Run number within the audit
$page = 1; // int
$per_page = 20; // int
$output = 'output_example'; // string | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.

try {
    $result = $apiInstance->listGeoAuditFindings($project_id, $geo_audit_id, $sequence, $page, $per_page, $output);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling GEOAuditsApi->listGeoAuditFindings: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **project_id** | **int**| Project ID | |
| **geo_audit_id** | **string**| Audit id | |
| **sequence** | **int**| Run number within the audit | |
| **page** | **int**|  | [optional] [default to 1] |
| **per_page** | **int**|  | [optional] [default to 20] |
| **output** | **string**| Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] |

### Return type

[**\LLMPulse\Model\GeoAuditFindingList**](../Model/GeoAuditFindingList.md)

### Authorization

[BearerAuth](../../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `listGeoAuditIssues()`

```php
listGeoAuditIssues($project_id, $geo_audit_id, $state, $page, $per_page): \LLMPulse\Model\GeoAuditIssueList
```

List the issues of a GEO audit

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: BearerAuth
$config = LLMPulse\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new LLMPulse\Api\GEOAuditsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$project_id = 56; // int | Project ID
$geo_audit_id = 'geo_audit_id_example'; // string | Audit id
$state = 'state_example'; // string | open means open and not accepted; default all
$page = 1; // int
$per_page = 20; // int

try {
    $result = $apiInstance->listGeoAuditIssues($project_id, $geo_audit_id, $state, $page, $per_page);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling GEOAuditsApi->listGeoAuditIssues: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **project_id** | **int**| Project ID | |
| **geo_audit_id** | **string**| Audit id | |
| **state** | **string**| open means open and not accepted; default all | [optional] |
| **page** | **int**|  | [optional] [default to 1] |
| **per_page** | **int**|  | [optional] [default to 20] |

### Return type

[**\LLMPulse\Model\GeoAuditIssueList**](../Model/GeoAuditIssueList.md)

### Authorization

[BearerAuth](../../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `listGeoAuditRuns()`

```php
listGeoAuditRuns($project_id, $geo_audit_id, $page, $per_page, $output): \LLMPulse\Model\GeoAuditRunList
```

List the runs of a GEO audit

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: BearerAuth
$config = LLMPulse\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new LLMPulse\Api\GEOAuditsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$project_id = 56; // int | Project ID
$geo_audit_id = 'geo_audit_id_example'; // string | Audit id
$page = 1; // int
$per_page = 20; // int
$output = 'output_example'; // string | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.

try {
    $result = $apiInstance->listGeoAuditRuns($project_id, $geo_audit_id, $page, $per_page, $output);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling GEOAuditsApi->listGeoAuditRuns: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **project_id** | **int**| Project ID | |
| **geo_audit_id** | **string**| Audit id | |
| **page** | **int**|  | [optional] [default to 1] |
| **per_page** | **int**|  | [optional] [default to 20] |
| **output** | **string**| Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] |

### Return type

[**\LLMPulse\Model\GeoAuditRunList**](../Model/GeoAuditRunList.md)

### Authorization

[BearerAuth](../../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `listGeoAudits()`

```php
listGeoAudits($project_id, $audit_type, $status, $cadence, $page, $per_page): \LLMPulse\Model\GeoAuditList
```

List GEO audits

Lists the project's audits, most recently updated first. Archived audits are left out unless status=archived.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: BearerAuth
$config = LLMPulse\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new LLMPulse\Api\GEOAuditsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$project_id = 56; // int | Project ID
$audit_type = 'audit_type_example'; // string
$status = 'status_example'; // string
$cadence = 'cadence_example'; // string
$page = 1; // int
$per_page = 20; // int

try {
    $result = $apiInstance->listGeoAudits($project_id, $audit_type, $status, $cadence, $page, $per_page);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling GEOAuditsApi->listGeoAudits: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **project_id** | **int**| Project ID | |
| **audit_type** | **string**|  | [optional] |
| **status** | **string**|  | [optional] |
| **cadence** | **string**|  | [optional] |
| **page** | **int**|  | [optional] [default to 1] |
| **per_page** | **int**|  | [optional] [default to 20] |

### Return type

[**\LLMPulse\Model\GeoAuditList**](../Model/GeoAuditList.md)

### Authorization

[BearerAuth](../../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `runGeoAudit()`

```php
runGeoAudit($project_id, $geo_audit_id): \LLMPulse\Model\GeoAuditRunResponse
```

Run a GEO audit now

Starts a run and returns it with status queued; poll GET /geo_audits/{geo_audit_id}/runs/{sequence} until status is completed, failed or unreachable. Limited to 6 manual runs per audit per rolling hour and 200 per account per day (ERR_LIMIT_REACHED); scheduled runs do not count. Requires a `read_write` scope API key.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: BearerAuth
$config = LLMPulse\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new LLMPulse\Api\GEOAuditsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$project_id = 56; // int | Project ID
$geo_audit_id = 'geo_audit_id_example'; // string | Audit id

try {
    $result = $apiInstance->runGeoAudit($project_id, $geo_audit_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling GEOAuditsApi->runGeoAudit: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **project_id** | **int**| Project ID | |
| **geo_audit_id** | **string**| Audit id | |

### Return type

[**\LLMPulse\Model\GeoAuditRunResponse**](../Model/GeoAuditRunResponse.md)

### Authorization

[BearerAuth](../../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `updateGeoAudit()`

```php
updateGeoAudit($id, $geo_audit_update_request): \LLMPulse\Model\GeoAuditResponse
```

Update a GEO audit

Updates the schedule, the email alerts or the status. Making an audit recurring or resuming it counts against the plan limit of active recurring audits (ERR_LIMIT_REACHED). Requires a `read_write` scope API key and, for team members, update permission on GEO Optimization.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: BearerAuth
$config = LLMPulse\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new LLMPulse\Api\GEOAuditsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string | Audit id
$geo_audit_update_request = new \LLMPulse\Model\GeoAuditUpdateRequest(); // \LLMPulse\Model\GeoAuditUpdateRequest

try {
    $result = $apiInstance->updateGeoAudit($id, $geo_audit_update_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling GEOAuditsApi->updateGeoAudit: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Audit id | |
| **geo_audit_update_request** | [**\LLMPulse\Model\GeoAuditUpdateRequest**](../Model/GeoAuditUpdateRequest.md)|  | |

### Return type

[**\LLMPulse\Model\GeoAuditResponse**](../Model/GeoAuditResponse.md)

### Authorization

[BearerAuth](../../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `updateGeoAuditIssue()`

```php
updateGeoAuditIssue($geo_audit_id, $id, $geo_audit_issue_update_request): \LLMPulse\Model\GeoAuditIssueResponse
```

Accept or reopen a GEO audit issue

Requires a `read_write` scope API key and, for team members, update permission on GEO Optimization.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: BearerAuth
$config = LLMPulse\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new LLMPulse\Api\GEOAuditsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$geo_audit_id = 'geo_audit_id_example'; // string | Audit id
$id = 56; // int | Issue id
$geo_audit_issue_update_request = new \LLMPulse\Model\GeoAuditIssueUpdateRequest(); // \LLMPulse\Model\GeoAuditIssueUpdateRequest

try {
    $result = $apiInstance->updateGeoAuditIssue($geo_audit_id, $id, $geo_audit_issue_update_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling GEOAuditsApi->updateGeoAuditIssue: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **geo_audit_id** | **string**| Audit id | |
| **id** | **int**| Issue id | |
| **geo_audit_issue_update_request** | [**\LLMPulse\Model\GeoAuditIssueUpdateRequest**](../Model/GeoAuditIssueUpdateRequest.md)|  | |

### Return type

[**\LLMPulse\Model\GeoAuditIssueResponse**](../Model/GeoAuditIssueResponse.md)

### Authorization

[BearerAuth](../../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
