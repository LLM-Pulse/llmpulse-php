# LLMPulse\WebhooksApi

Outbound event notifications: subscribe an HTTPS URL to project events and receive HMAC-signed deliveries with no polling. Scale plan and above.

All URIs are relative to https://api.llmpulse.ai/api/v1, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**createWebhook()**](WebhooksApi.md#createWebhook) | **POST** /webhooks | Create a webhook subscription |
| [**deleteWebhook()**](WebhooksApi.md#deleteWebhook) | **DELETE** /webhooks/{id} | Delete a webhook subscription |
| [**listWebhooks()**](WebhooksApi.md#listWebhooks) | **GET** /webhooks | List webhook subscriptions |
| [**sampleWebhookPayloads()**](WebhooksApi.md#sampleWebhookPayloads) | **GET** /webhooks/sample/{event_type} | Sample event payloads |


## `createWebhook()`

```php
createWebhook($create_webhook_request): \LLMPulse\Model\CreateWebhook201Response
```

Create a webhook subscription

Subscribes a public HTTPS URL to a project event. LLM Pulse POSTs a JSON envelope (`event`, `occurred_at`, `project_id`, `subscription_id`, `data`) to the URL every time the event occurs, signed via the `X-LLMPulse-Signature` header (HMAC-SHA256 of the raw body computed with the subscription secret). Failed deliveries receive up to 5 attempts in total, including the first, with backoff; subscriptions auto-disable after 20 consecutive failed deliveries. Idempotent for the same project + event + URL. Requires a `read_write` scope API key and the Scale plan or above.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: BearerAuth
$config = LLMPulse\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new LLMPulse\Api\WebhooksApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$create_webhook_request = new \LLMPulse\Model\CreateWebhookRequest(); // \LLMPulse\Model\CreateWebhookRequest

try {
    $result = $apiInstance->createWebhook($create_webhook_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling WebhooksApi->createWebhook: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **create_webhook_request** | [**\LLMPulse\Model\CreateWebhookRequest**](../Model/CreateWebhookRequest.md)|  | |

### Return type

[**\LLMPulse\Model\CreateWebhook201Response**](../Model/CreateWebhook201Response.md)

### Authorization

[BearerAuth](../../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `deleteWebhook()`

```php
deleteWebhook($id): \LLMPulse\Model\DeleteWebhook200Response
```

Delete a webhook subscription

Deletes a webhook subscription; the target URL stops receiving events immediately. Requires a `read_write` scope API key and the Scale plan or above.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: BearerAuth
$config = LLMPulse\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new LLMPulse\Api\WebhooksApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 56; // int

try {
    $result = $apiInstance->deleteWebhook($id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling WebhooksApi->deleteWebhook: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **int**|  | |

### Return type

[**\LLMPulse\Model\DeleteWebhook200Response**](../Model/DeleteWebhook200Response.md)

### Authorization

[BearerAuth](../../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `listWebhooks()`

```php
listWebhooks($project_id, $page, $per_page): \LLMPulse\Model\ListWebhooks200Response
```

List webhook subscriptions

Lists active webhook subscriptions for the account, optionally filtered by project. Requires the Scale plan or above.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: BearerAuth
$config = LLMPulse\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new LLMPulse\Api\WebhooksApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$project_id = 56; // int | Optional project filter
$page = 56; // int
$per_page = 56; // int | Max 100

try {
    $result = $apiInstance->listWebhooks($project_id, $page, $per_page);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling WebhooksApi->listWebhooks: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **project_id** | **int**| Optional project filter | [optional] |
| **page** | **int**|  | [optional] |
| **per_page** | **int**| Max 100 | [optional] |

### Return type

[**\LLMPulse\Model\ListWebhooks200Response**](../Model/ListWebhooks200Response.md)

### Authorization

[BearerAuth](../../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `sampleWebhookPayloads()`

```php
sampleWebhookPayloads($event_type, $project_id): \LLMPulse\Model\SampleWebhookPayloads200Response
```

Sample event payloads

Returns up to 3 example event payloads for the event type, built from the project's most recent real data (or a static sample when the project has no data). Used by integration editors such as the Zapier sample loader. Requires the Scale plan or above.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: BearerAuth
$config = LLMPulse\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new LLMPulse\Api\WebhooksApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$event_type = 'event_type_example'; // string
$project_id = 56; // int

try {
    $result = $apiInstance->sampleWebhookPayloads($event_type, $project_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling WebhooksApi->sampleWebhookPayloads: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **event_type** | **string**|  | |
| **project_id** | **int**|  | |

### Return type

[**\LLMPulse\Model\SampleWebhookPayloads200Response**](../Model/SampleWebhookPayloads200Response.md)

### Authorization

[BearerAuth](../../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
