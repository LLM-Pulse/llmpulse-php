# LLMPulse\StoreIntegrationsApi



All URIs are relative to https://api.llmpulse.ai/api/v1, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**acceptCatalogPromptSuggestions()**](StoreIntegrationsApi.md#acceptCatalogPromptSuggestions) | **POST** /catalog_prompt_suggestions/accept | Accept catalog prompt suggestions |
| [**createCatalogPromptSuggestions()**](StoreIntegrationsApi.md#createCatalogPromptSuggestions) | **POST** /catalog_prompt_suggestions | Suggest buyer prompts from catalog products |
| [**getStoreConnection()**](StoreIntegrationsApi.md#getStoreConnection) | **GET** /store_connection | Match a store to a project |
| [**listAiOrders()**](StoreIntegrationsApi.md#listAiOrders) | **GET** /ai_orders | Read AI-referred store orders |
| [**listCatalogPromptSuggestions()**](StoreIntegrationsApi.md#listCatalogPromptSuggestions) | **GET** /catalog_prompt_suggestions | List catalog prompt suggestions |
| [**rejectCatalogPromptSuggestions()**](StoreIntegrationsApi.md#rejectCatalogPromptSuggestions) | **POST** /catalog_prompt_suggestions/reject | Reject catalog prompt suggestions |
| [**replaceAiOrders()**](StoreIntegrationsApi.md#replaceAiOrders) | **PUT** /ai_orders | Replace AI-referred store orders for a window |


## `acceptCatalogPromptSuggestions()`

```php
acceptCatalogPromptSuggestions($catalog_prompt_suggestion_ids_request): \LLMPulse\Model\CatalogPromptSuggestionsAcceptResponse
```

Accept catalog prompt suggestions

Starts tracking pending suggestions: each one becomes a prompt, tagged with a collection named after its product. Suggestions that are no longer pending come back in skipped. All accepted suggestions must share one country and language. When the new prompts would exceed the plan, the call returns ERR_LIMIT_REACHED and accepts nothing. Requires a `read_write` scope API key and, for team members, create access to Prompts. Not available to accounts with a white-label portal or an embed (ERR_INTEGRATION_UNAVAILABLE).

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: BearerAuth
$config = LLMPulse\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new LLMPulse\Api\StoreIntegrationsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$catalog_prompt_suggestion_ids_request = new \LLMPulse\Model\CatalogPromptSuggestionIdsRequest(); // \LLMPulse\Model\CatalogPromptSuggestionIdsRequest

try {
    $result = $apiInstance->acceptCatalogPromptSuggestions($catalog_prompt_suggestion_ids_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling StoreIntegrationsApi->acceptCatalogPromptSuggestions: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **catalog_prompt_suggestion_ids_request** | [**\LLMPulse\Model\CatalogPromptSuggestionIdsRequest**](../Model/CatalogPromptSuggestionIdsRequest.md)|  | |

### Return type

[**\LLMPulse\Model\CatalogPromptSuggestionsAcceptResponse**](../Model/CatalogPromptSuggestionsAcceptResponse.md)

### Authorization

[BearerAuth](../../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `createCatalogPromptSuggestions()`

```php
createCatalogPromptSuggestions($catalog_prompt_suggestions_create_request): \LLMPulse\Model\CatalogPromptSuggestionsCreateResponse
```

Suggest buyer prompts from catalog products

Writes buyer prompts for up to 20 catalog products and saves them as pending suggestions in the project's Suggested prompts queue, with the product recorded on each. Generation draws on the hourly prompt-suggestion allowance the app also uses (ERR_QUOTA_EXCEEDED once it is used up); a failed generation returns ERR_GENERATION_FAILED (502) and can be retried. Requires a `read_write` scope API key and, for team members, create access to Prompts. Not available to accounts with a white-label portal or an embed (ERR_INTEGRATION_UNAVAILABLE).

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: BearerAuth
$config = LLMPulse\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new LLMPulse\Api\StoreIntegrationsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$catalog_prompt_suggestions_create_request = new \LLMPulse\Model\CatalogPromptSuggestionsCreateRequest(); // \LLMPulse\Model\CatalogPromptSuggestionsCreateRequest

try {
    $result = $apiInstance->createCatalogPromptSuggestions($catalog_prompt_suggestions_create_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling StoreIntegrationsApi->createCatalogPromptSuggestions: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **catalog_prompt_suggestions_create_request** | [**\LLMPulse\Model\CatalogPromptSuggestionsCreateRequest**](../Model/CatalogPromptSuggestionsCreateRequest.md)|  | |

### Return type

[**\LLMPulse\Model\CatalogPromptSuggestionsCreateResponse**](../Model/CatalogPromptSuggestionsCreateResponse.md)

### Authorization

[BearerAuth](../../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getStoreConnection()`

```php
getStoreConnection($platform, $domain): \LLMPulse\Model\StoreConnectionResponse
```

Match a store to a project

Tells a store app whether the API key's account can use it and which project the store belongs to: the live project whose domain equals the store domain, else one whose domain is a parent or a subdomain of it, else null. candidates lists every live project of the account so the app can offer a picker. Takes no project_id. Not available to accounts with a white-label portal or an embed (ERR_INTEGRATION_UNAVAILABLE).

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: BearerAuth
$config = LLMPulse\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new LLMPulse\Api\StoreIntegrationsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$platform = 'platform_example'; // string | Store platform
$domain = 'domain_example'; // string | Store domain, with or without scheme, e.g. acme-store.com

try {
    $result = $apiInstance->getStoreConnection($platform, $domain);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling StoreIntegrationsApi->getStoreConnection: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **platform** | **string**| Store platform | |
| **domain** | **string**| Store domain, with or without scheme, e.g. acme-store.com | |

### Return type

[**\LLMPulse\Model\StoreConnectionResponse**](../Model/StoreConnectionResponse.md)

### Authorization

[BearerAuth](../../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `listAiOrders()`

```php
listAiOrders($project_id, $platform, $from, $to): \LLMPulse\Model\AiOrdersResponse
```

Read AI-referred store orders

Reads back the AI-referred orders a store app pushed for a project: totals, one row per AI assistant and a daily series of the days with orders. Revenue values are decimal strings in currency. Team members need read access to AI Traffic. Not available to accounts with a white-label portal or an embed (ERR_INTEGRATION_UNAVAILABLE).

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: BearerAuth
$config = LLMPulse\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new LLMPulse\Api\StoreIntegrationsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$project_id = 56; // int | Project ID
$platform = 'shopify'; // string | Store platform
$from = new \DateTime('2013-10-20T19:20:30+01:00'); // \DateTime | First day (YYYY-MM-DD). Defaults to 89 days before to
$to = new \DateTime('2013-10-20T19:20:30+01:00'); // \DateTime | Last day (YYYY-MM-DD). Defaults to today; the window is at most 400 days

try {
    $result = $apiInstance->listAiOrders($project_id, $platform, $from, $to);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling StoreIntegrationsApi->listAiOrders: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **project_id** | **int**| Project ID | |
| **platform** | **string**| Store platform | [optional] [default to &#39;shopify&#39;] |
| **from** | **\DateTime**| First day (YYYY-MM-DD). Defaults to 89 days before to | [optional] |
| **to** | **\DateTime**| Last day (YYYY-MM-DD). Defaults to today; the window is at most 400 days | [optional] |

### Return type

[**\LLMPulse\Model\AiOrdersResponse**](../Model/AiOrdersResponse.md)

### Authorization

[BearerAuth](../../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `listCatalogPromptSuggestions()`

```php
listCatalogPromptSuggestions($project_id, $status, $product_external_id, $page, $per_page): \LLMPulse\Model\CatalogPromptSuggestionsResponse
```

List catalog prompt suggestions

Lists the buyer prompts suggested from a store catalog, oldest first, with their status and the product each one came from. Team members need read access to Prompts. Not available to accounts with a white-label portal or an embed (ERR_INTEGRATION_UNAVAILABLE).

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: BearerAuth
$config = LLMPulse\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new LLMPulse\Api\StoreIntegrationsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$project_id = 56; // int | Project ID
$status = 'status_example'; // string | Only suggestions in this status
$product_external_id = 'product_external_id_example'; // string | Only suggestions for this store product id
$page = 1; // int
$per_page = 50; // int

try {
    $result = $apiInstance->listCatalogPromptSuggestions($project_id, $status, $product_external_id, $page, $per_page);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling StoreIntegrationsApi->listCatalogPromptSuggestions: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **project_id** | **int**| Project ID | |
| **status** | **string**| Only suggestions in this status | [optional] |
| **product_external_id** | **string**| Only suggestions for this store product id | [optional] |
| **page** | **int**|  | [optional] [default to 1] |
| **per_page** | **int**|  | [optional] [default to 50] |

### Return type

[**\LLMPulse\Model\CatalogPromptSuggestionsResponse**](../Model/CatalogPromptSuggestionsResponse.md)

### Authorization

[BearerAuth](../../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `rejectCatalogPromptSuggestions()`

```php
rejectCatalogPromptSuggestions($catalog_prompt_suggestion_ids_request): \LLMPulse\Model\CatalogPromptSuggestionsRejectResponse
```

Reject catalog prompt suggestions

Marks pending suggestions as rejected; suggestions that are no longer pending stay as they are. Requires a `read_write` scope API key and, for team members, update access to Prompts. Not available to accounts with a white-label portal or an embed (ERR_INTEGRATION_UNAVAILABLE).

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: BearerAuth
$config = LLMPulse\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new LLMPulse\Api\StoreIntegrationsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$catalog_prompt_suggestion_ids_request = new \LLMPulse\Model\CatalogPromptSuggestionIdsRequest(); // \LLMPulse\Model\CatalogPromptSuggestionIdsRequest

try {
    $result = $apiInstance->rejectCatalogPromptSuggestions($catalog_prompt_suggestion_ids_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling StoreIntegrationsApi->rejectCatalogPromptSuggestions: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **catalog_prompt_suggestion_ids_request** | [**\LLMPulse\Model\CatalogPromptSuggestionIdsRequest**](../Model/CatalogPromptSuggestionIdsRequest.md)|  | |

### Return type

[**\LLMPulse\Model\CatalogPromptSuggestionsRejectResponse**](../Model/CatalogPromptSuggestionsRejectResponse.md)

### Authorization

[BearerAuth](../../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `replaceAiOrders()`

```php
replaceAiOrders($ai_orders_update_request): \LLMPulse\Model\AiOrdersUpdateResponse
```

Replace AI-referred store orders for a window

Replaces the daily AI-referred orders and revenue of the from..to window. Send the raw referring host or utm_source of each order's first visit as referrer: LLM Pulse classifies it and ignores anything that is not an AI assistant. Entries for the same day and assistant are summed. Every stored row of that project and platform inside the window is replaced, so pushing the same window again converges instead of counting twice. Rows are kept per project and platform, not per store, so one store reports per project. Requires a `read_write` scope API key and, for team members, update access to AI Traffic. Not available to accounts with a white-label portal or an embed (ERR_INTEGRATION_UNAVAILABLE).

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: BearerAuth
$config = LLMPulse\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new LLMPulse\Api\StoreIntegrationsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$ai_orders_update_request = new \LLMPulse\Model\AiOrdersUpdateRequest(); // \LLMPulse\Model\AiOrdersUpdateRequest

try {
    $result = $apiInstance->replaceAiOrders($ai_orders_update_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling StoreIntegrationsApi->replaceAiOrders: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **ai_orders_update_request** | [**\LLMPulse\Model\AiOrdersUpdateRequest**](../Model/AiOrdersUpdateRequest.md)|  | |

### Return type

[**\LLMPulse\Model\AiOrdersUpdateResponse**](../Model/AiOrdersUpdateResponse.md)

### Authorization

[BearerAuth](../../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
