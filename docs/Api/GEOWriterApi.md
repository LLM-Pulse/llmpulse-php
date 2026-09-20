# LLMPulse\GEOWriterApi



All URIs are relative to https://api.llmpulse.ai/api/v1, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**createIntelligenceTask()**](GEOWriterApi.md#createIntelligenceTask) | **POST** /intelligence_tasks | Create a GEO Writer task |
| [**getIntelligenceTask()**](GEOWriterApi.md#getIntelligenceTask) | **GET** /intelligence_tasks/{id} | Get a GEO Writer task |
| [**listIntelligenceTasks()**](GEOWriterApi.md#listIntelligenceTasks) | **GET** /intelligence_tasks | List GEO Writer tasks |
| [**revertIntelligenceTaskContent()**](GEOWriterApi.md#revertIntelligenceTaskContent) | **POST** /intelligence_tasks/{id}/revert | Revert GEO Writer task content |
| [**updateIntelligenceTaskContent()**](GEOWriterApi.md#updateIntelligenceTaskContent) | **PATCH** /intelligence_tasks/{id} | Edit GEO Writer task content |


## `createIntelligenceTask()`

```php
createIntelligenceTask($intelligence_task_create_request): \LLMPulse\Model\IntelligenceTask
```

Create a GEO Writer task

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: BearerAuth
$config = LLMPulse\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new LLMPulse\Api\GEOWriterApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$intelligence_task_create_request = new \LLMPulse\Model\IntelligenceTaskCreateRequest(); // \LLMPulse\Model\IntelligenceTaskCreateRequest

try {
    $result = $apiInstance->createIntelligenceTask($intelligence_task_create_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling GEOWriterApi->createIntelligenceTask: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **intelligence_task_create_request** | [**\LLMPulse\Model\IntelligenceTaskCreateRequest**](../Model/IntelligenceTaskCreateRequest.md)|  | |

### Return type

[**\LLMPulse\Model\IntelligenceTask**](../Model/IntelligenceTask.md)

### Authorization

[BearerAuth](../../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getIntelligenceTask()`

```php
getIntelligenceTask($project_id, $id): \LLMPulse\Model\IntelligenceTask
```

Get a GEO Writer task

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: BearerAuth
$config = LLMPulse\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new LLMPulse\Api\GEOWriterApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$project_id = 56; // int | Project ID
$id = 'id_example'; // string | Numeric task ID or public_id string token

try {
    $result = $apiInstance->getIntelligenceTask($project_id, $id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling GEOWriterApi->getIntelligenceTask: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **project_id** | **int**| Project ID | |
| **id** | **string**| Numeric task ID or public_id string token | |

### Return type

[**\LLMPulse\Model\IntelligenceTask**](../Model/IntelligenceTask.md)

### Authorization

[BearerAuth](../../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `listIntelligenceTasks()`

```php
listIntelligenceTasks($project_id, $task_type, $status, $page, $per_page)
```

List GEO Writer tasks

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: BearerAuth
$config = LLMPulse\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new LLMPulse\Api\GEOWriterApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$project_id = 56; // int | Project ID
$task_type = 'task_type_example'; // string
$status = 'status_example'; // string
$page = 1; // int
$per_page = 20; // int

try {
    $apiInstance->listIntelligenceTasks($project_id, $task_type, $status, $page, $per_page);
} catch (Exception $e) {
    echo 'Exception when calling GEOWriterApi->listIntelligenceTasks: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **project_id** | **int**| Project ID | |
| **task_type** | **string**|  | [optional] |
| **status** | **string**|  | [optional] |
| **page** | **int**|  | [optional] [default to 1] |
| **per_page** | **int**|  | [optional] [default to 20] |

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

## `revertIntelligenceTaskContent()`

```php
revertIntelligenceTaskContent($project_id, $id): \LLMPulse\Model\IntelligenceTask
```

Revert GEO Writer task content

Discards every manual edit on the task and restores the output exactly as it was generated. Returns ERR_INVALID_PARAM when the task has no manual edits. Requires a `read_write` scope API key and, for team members, update permission on GEO Writer.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: BearerAuth
$config = LLMPulse\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new LLMPulse\Api\GEOWriterApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$project_id = 56; // int | Project ID
$id = 'id_example'; // string | Numeric task ID or public_id string token

try {
    $result = $apiInstance->revertIntelligenceTaskContent($project_id, $id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling GEOWriterApi->revertIntelligenceTaskContent: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **project_id** | **int**| Project ID | |
| **id** | **string**| Numeric task ID or public_id string token | |

### Return type

[**\LLMPulse\Model\IntelligenceTask**](../Model/IntelligenceTask.md)

### Authorization

[BearerAuth](../../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `updateIntelligenceTaskContent()`

```php
updateIntelligenceTaskContent($id, $intelligence_task_update_request): \LLMPulse\Model\IntelligenceTaskUpdateResponse
```

Edit GEO Writer task content

Edits the text of a completed task in place. `edits` maps dotted paths into result_data (for example `title` or `sections.0.content`) to replacement text. Only string fields that already exist can change: a path that does not resolve to text, a blank `title`, a value over 20,000 characters or an empty `edits` object is rejected with ERR_INVALID_PARAM and nothing is written. Values identical to the stored text are ignored, and the response lists the paths that actually changed. The first edit keeps a copy of the generated output so POST /intelligence_tasks/{id}/revert can restore it; regenerating the task replaces the edited content. Requires a `read_write` scope API key and, for team members, update permission on GEO Writer.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: BearerAuth
$config = LLMPulse\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new LLMPulse\Api\GEOWriterApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string | Numeric task ID or public_id string token
$intelligence_task_update_request = new \LLMPulse\Model\IntelligenceTaskUpdateRequest(); // \LLMPulse\Model\IntelligenceTaskUpdateRequest

try {
    $result = $apiInstance->updateIntelligenceTaskContent($id, $intelligence_task_update_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling GEOWriterApi->updateIntelligenceTaskContent: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Numeric task ID or public_id string token | |
| **intelligence_task_update_request** | [**\LLMPulse\Model\IntelligenceTaskUpdateRequest**](../Model/IntelligenceTaskUpdateRequest.md)|  | |

### Return type

[**\LLMPulse\Model\IntelligenceTaskUpdateResponse**](../Model/IntelligenceTaskUpdateResponse.md)

### Authorization

[BearerAuth](../../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
