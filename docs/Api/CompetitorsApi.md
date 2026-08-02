# LLMPulse\CompetitorsApi



All URIs are relative to https://api.llmpulse.ai/api/v1, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**createCompetitor()**](CompetitorsApi.md#createCompetitor) | **POST** /competitors | Add a competitor |
| [**deleteCompetitor()**](CompetitorsApi.md#deleteCompetitor) | **DELETE** /competitors/{id} | Delete a competitor |
| [**updateCompetitor()**](CompetitorsApi.md#updateCompetitor) | **PATCH** /competitors/{id} | Update a competitor |


## `createCompetitor()`

```php
createCompetitor($create_competitor_request)
```

Add a competitor

Adds a competitor (brand name + domain) to a project. Honours the per-plan max competitors cap. Requires a `read_write` scope API key.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: BearerAuth
$config = LLMPulse\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new LLMPulse\Api\CompetitorsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$create_competitor_request = new \LLMPulse\Model\CreateCompetitorRequest(); // \LLMPulse\Model\CreateCompetitorRequest

try {
    $apiInstance->createCompetitor($create_competitor_request);
} catch (Exception $e) {
    echo 'Exception when calling CompetitorsApi->createCompetitor: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **create_competitor_request** | [**\LLMPulse\Model\CreateCompetitorRequest**](../Model/CreateCompetitorRequest.md)|  | |

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

## `deleteCompetitor()`

```php
deleteCompetitor($project_id, $id)
```

Delete a competitor

Deletes a competitor (irreversible). It disappears immediately and frees a competitor slot; its tracked data is purged by a background job. Requires a `read_write` scope API key.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: BearerAuth
$config = LLMPulse\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new LLMPulse\Api\CompetitorsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$project_id = 56; // int | Project ID
$id = 56; // int

try {
    $apiInstance->deleteCompetitor($project_id, $id);
} catch (Exception $e) {
    echo 'Exception when calling CompetitorsApi->deleteCompetitor: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **project_id** | **int**| Project ID | |
| **id** | **int**|  | |

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

## `updateCompetitor()`

```php
updateCompetitor($id, $update_competitor_request)
```

Update a competitor

Updates brand_name, matching_names (full replacement list; the brand name is always included automatically) and/or color. The domain is immutable after creation. Name changes re-run mention/citation matching in the background: the competitor shows processing=true for a few minutes and further edits are rejected meanwhile. Requires a `read_write` scope API key.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: BearerAuth
$config = LLMPulse\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new LLMPulse\Api\CompetitorsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 56; // int
$update_competitor_request = new \LLMPulse\Model\UpdateCompetitorRequest(); // \LLMPulse\Model\UpdateCompetitorRequest

try {
    $apiInstance->updateCompetitor($id, $update_competitor_request);
} catch (Exception $e) {
    echo 'Exception when calling CompetitorsApi->updateCompetitor: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **int**|  | |
| **update_competitor_request** | [**\LLMPulse\Model\UpdateCompetitorRequest**](../Model/UpdateCompetitorRequest.md)|  | |

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
