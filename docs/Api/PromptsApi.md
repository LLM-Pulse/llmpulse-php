# LLMPulse\PromptsApi

Bulk-create prompts

All URIs are relative to https://api.llmpulse.ai/api/v1, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**assignPromptTags()**](PromptsApi.md#assignPromptTags) | **POST** /prompts/assign_tags | Bulk-attach tags to prompts |
| [**createPrompts()**](PromptsApi.md#createPrompts) | **POST** /prompts | Bulk-create prompts |
| [**deletePrompt()**](PromptsApi.md#deletePrompt) | **DELETE** /prompts/{id} | Delete a prompt |


## `assignPromptTags()`

```php
assignPromptTags($assign_prompt_tags_request)
```

Bulk-attach tags to prompts

Idempotent bulk assignment of tags (Collections) to existing prompts. Tags can be resolved by id or by name (case-insensitive). Use `create_missing: true` to auto-create unknown tag names. Requires a `read_write` scope API key.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: BearerAuth
$config = LLMPulse\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new LLMPulse\Api\PromptsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$assign_prompt_tags_request = new \LLMPulse\Model\AssignPromptTagsRequest(); // \LLMPulse\Model\AssignPromptTagsRequest

try {
    $apiInstance->assignPromptTags($assign_prompt_tags_request);
} catch (Exception $e) {
    echo 'Exception when calling PromptsApi->assignPromptTags: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **assign_prompt_tags_request** | [**\LLMPulse\Model\AssignPromptTagsRequest**](../Model/AssignPromptTagsRequest.md)|  | |

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

## `createPrompts()`

```php
createPrompts($prompts_create_request): \LLMPulse\Model\PromptsCreateResponse
```

Bulk-create prompts

Add prompts to a project in bulk (up to 100 per request). Validates the account prompt quota and skips duplicates. Requires a `read_write` scope API key.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: BearerAuth
$config = LLMPulse\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new LLMPulse\Api\PromptsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$prompts_create_request = new \LLMPulse\Model\PromptsCreateRequest(); // \LLMPulse\Model\PromptsCreateRequest

try {
    $result = $apiInstance->createPrompts($prompts_create_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling PromptsApi->createPrompts: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **prompts_create_request** | [**\LLMPulse\Model\PromptsCreateRequest**](../Model/PromptsCreateRequest.md)|  | |

### Return type

[**\LLMPulse\Model\PromptsCreateResponse**](../Model/PromptsCreateResponse.md)

### Authorization

[BearerAuth](../../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `deletePrompt()`

```php
deletePrompt($project_id, $id)
```

Delete a prompt

Deletes a prompt (irreversible). The prompt disappears immediately and frees a prompt slot; its historical data (executions, mentions, citations, sentiment) is purged by a background job. Requires a `read_write` scope API key.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: BearerAuth
$config = LLMPulse\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new LLMPulse\Api\PromptsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$project_id = 56; // int | Project ID
$id = 56; // int

try {
    $apiInstance->deletePrompt($project_id, $id);
} catch (Exception $e) {
    echo 'Exception when calling PromptsApi->deletePrompt: ', $e->getMessage(), PHP_EOL;
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
