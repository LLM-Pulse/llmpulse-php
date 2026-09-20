# LLMPulse\HealthApi

Health check that validates an API key and, optionally, access to a project.

All URIs are relative to https://api.llmpulse.ai/api/v1, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**ping()**](HealthApi.md#ping) | **GET** /ping | Health check |


## `ping()`

```php
ping($project_id): \LLMPulse\Model\Ping200Response
```

Health check

Validates the API key and optionally pings a project. Returns the authenticated user_id, project (if project_id is supplied), and a request_id.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: BearerAuth
$config = LLMPulse\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new LLMPulse\Api\HealthApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$project_id = 56; // int | Optional project to verify access for

try {
    $result = $apiInstance->ping($project_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling HealthApi->ping: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **project_id** | **int**| Optional project to verify access for | [optional] |

### Return type

[**\LLMPulse\Model\Ping200Response**](../Model/Ping200Response.md)

### Authorization

[BearerAuth](../../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
