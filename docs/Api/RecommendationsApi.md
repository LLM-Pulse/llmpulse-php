# LLMPulse\RecommendationsApi

Recommendation runs that power the in-app Recommendations page, the endpoint that launches a new one, and the one that completes, archives or restores an item.

All URIs are relative to https://api.llmpulse.ai/api/v1, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**getRecommendation()**](RecommendationsApi.md#getRecommendation) | **GET** /recommendations/{id} | Get recommendation run with items |
| [**launchRecommendations()**](RecommendationsApi.md#launchRecommendations) | **POST** /recommendations | Launch a recommendations generation |
| [**listRecommendations()**](RecommendationsApi.md#listRecommendations) | **GET** /recommendations | List recommendation runs |
| [**updateRecommendationItem()**](RecommendationsApi.md#updateRecommendationItem) | **PATCH** /recommendations/{id}/items/{item_id} | Complete, archive or restore a recommendation item |


## `getRecommendation()`

```php
getRecommendation($project_id, $id, $item_status, $resolve_source_refs)
```

Get recommendation run with items

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: BearerAuth
$config = LLMPulse\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new LLMPulse\Api\RecommendationsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$project_id = 56; // int | Project ID
$id = 56; // int
$item_status = 'item_status_example'; // string
$resolve_source_refs = true; // bool

try {
    $apiInstance->getRecommendation($project_id, $id, $item_status, $resolve_source_refs);
} catch (Exception $e) {
    echo 'Exception when calling RecommendationsApi->getRecommendation: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **project_id** | **int**| Project ID | |
| **id** | **int**|  | |
| **item_status** | **string**|  | [optional] |
| **resolve_source_refs** | **bool**|  | [optional] [default to true] |

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

## `launchRecommendations()`

```php
launchRecommendations($launch_recommendations_request)
```

Launch a recommendations generation

Launches a full-scope recommendations generation (async job, 1-3 minutes; poll GET /recommendations/{id} until status is completed). Consumes the project weekly recommendation-item budget: returns ERR_LIMIT_REACHED when it is exhausted or when a generation of the same type is already pending/processing. sentiment_reputation requires the Scale plan or above. Requires a `read_write` scope API key.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: BearerAuth
$config = LLMPulse\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new LLMPulse\Api\RecommendationsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$launch_recommendations_request = new \LLMPulse\Model\LaunchRecommendationsRequest(); // \LLMPulse\Model\LaunchRecommendationsRequest

try {
    $apiInstance->launchRecommendations($launch_recommendations_request);
} catch (Exception $e) {
    echo 'Exception when calling RecommendationsApi->launchRecommendations: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **launch_recommendations_request** | [**\LLMPulse\Model\LaunchRecommendationsRequest**](../Model/LaunchRecommendationsRequest.md)|  | |

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

## `listRecommendations()`

```php
listRecommendations($project_id, $recommendation_type, $status, $page, $per_page): \LLMPulse\Model\RecommendationsResponse
```

List recommendation runs

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: BearerAuth
$config = LLMPulse\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new LLMPulse\Api\RecommendationsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$project_id = 56; // int | Project ID
$recommendation_type = 'recommendation_type_example'; // string
$status = 'status_example'; // string
$page = 1; // int
$per_page = 20; // int

try {
    $result = $apiInstance->listRecommendations($project_id, $recommendation_type, $status, $page, $per_page);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling RecommendationsApi->listRecommendations: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **project_id** | **int**| Project ID | |
| **recommendation_type** | **string**|  | [optional] |
| **status** | **string**|  | [optional] |
| **page** | **int**|  | [optional] [default to 1] |
| **per_page** | **int**|  | [optional] [default to 20] |

### Return type

[**\LLMPulse\Model\RecommendationsResponse**](../Model/RecommendationsResponse.md)

### Authorization

[BearerAuth](../../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `updateRecommendationItem()`

```php
updateRecommendationItem($id, $item_id, $update_recommendation_item_request): \LLMPulse\Model\RecommendationItemUpdateResponse
```

Complete, archive or restore a recommendation item

Moves one item of a recommendation run between `active`, `completed` and `archived`, exactly like the complete, archive and restore buttons on the Recommendations page, and stamps `status_changed_at`. Returns the item in the shape `GET /recommendations/{id}` lists items. Requires a `read_write` scope API key and, for team members, create permission on Recommendations (the permission the page uses for these buttons).

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: BearerAuth
$config = LLMPulse\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new LLMPulse\Api\RecommendationsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 56; // int | Recommendation run id
$item_id = 56; // int | Item id, from the items of GET /recommendations/{id}
$update_recommendation_item_request = new \LLMPulse\Model\UpdateRecommendationItemRequest(); // \LLMPulse\Model\UpdateRecommendationItemRequest

try {
    $result = $apiInstance->updateRecommendationItem($id, $item_id, $update_recommendation_item_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling RecommendationsApi->updateRecommendationItem: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **int**| Recommendation run id | |
| **item_id** | **int**| Item id, from the items of GET /recommendations/{id} | |
| **update_recommendation_item_request** | [**\LLMPulse\Model\UpdateRecommendationItemRequest**](../Model/UpdateRecommendationItemRequest.md)|  | |

### Return type

[**\LLMPulse\Model\RecommendationItemUpdateResponse**](../Model/RecommendationItemUpdateResponse.md)

### Authorization

[BearerAuth](../../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
