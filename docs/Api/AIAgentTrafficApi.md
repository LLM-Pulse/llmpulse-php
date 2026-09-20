# LLMPulse\AIAgentTrafficApi



All URIs are relative to https://api.llmpulse.ai/api/v1, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**getAgentTraffic()**](AIAgentTrafficApi.md#getAgentTraffic) | **GET** /metrics/agent_traffic | AI bot crawler traffic (Scale plan or above, Beta) |
| [**getAiTraffic()**](AIAgentTrafficApi.md#getAiTraffic) | **GET** /metrics/ai_traffic | AI referral traffic (Scale plan or above) |
| [**listAgentBots()**](AIAgentTrafficApi.md#listAgentBots) | **GET** /dimensions/agent_bots | AI bot catalog (Scale plan or above) |


## `getAgentTraffic()`

```php
getAgentTraffic($project_id, $range, $from, $to, $bot, $company, $group_by, $granularity): \LLMPulse\Model\AgentTrafficResponse
```

AI bot crawler traffic (Scale plan or above, Beta)

Aggregated AI bot traffic hitting the project's origin server (GPTBot, PerplexityBot, ClaudeBot, OAI-SearchBot, Google-Extended, etc.). Sourced from Cloudflare or CSV uploads. Requires the Scale plan; lower tiers receive ERR_PLAN_REQUIRED.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: BearerAuth
$config = LLMPulse\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new LLMPulse\Api\AIAgentTrafficApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$project_id = 56; // int | Project ID
$range = 56; // int | Number of days to look back (alternative to from/to)
$from = new \DateTime('2013-10-20T19:20:30+01:00'); // \DateTime
$to = new \DateTime('2013-10-20T19:20:30+01:00'); // \DateTime | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier.
$bot = 'bot_example'; // string | Filter by bot slug (e.g. gptbot, claudebot, perplexitybot)
$company = 'company_example'; // string | Filter by company (e.g. openai, anthropic, google)
$group_by = 'bot'; // string
$granularity = 'granularity_example'; // string

try {
    $result = $apiInstance->getAgentTraffic($project_id, $range, $from, $to, $bot, $company, $group_by, $granularity);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AIAgentTrafficApi->getAgentTraffic: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **project_id** | **int**| Project ID | |
| **range** | **int**| Number of days to look back (alternative to from/to) | [optional] |
| **from** | **\DateTime**|  | [optional] |
| **to** | **\DateTime**| End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. | [optional] |
| **bot** | **string**| Filter by bot slug (e.g. gptbot, claudebot, perplexitybot) | [optional] |
| **company** | **string**| Filter by company (e.g. openai, anthropic, google) | [optional] |
| **group_by** | **string**|  | [optional] [default to &#39;bot&#39;] |
| **granularity** | **string**|  | [optional] |

### Return type

[**\LLMPulse\Model\AgentTrafficResponse**](../Model/AgentTrafficResponse.md)

### Authorization

[BearerAuth](../../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getAiTraffic()`

```php
getAiTraffic($project_id, $range, $from, $to, $source, $granularity)
```

AI referral traffic (Scale plan or above)

AI referral traffic for a project: human visits arriving from AI assistants (ChatGPT, Perplexity, Gemini, Claude, etc.), measured from the connected web analytics provider (Google Analytics 4, Adobe Analytics, PostHog, Plausible or Piano). Returns per-source users, sessions and conversions with totals and a conversion rate. Requires a connected provider and the Scale plan; otherwise returns ERR_AI_TRAFFIC_NOT_CONNECTED or ERR_PLAN_REQUIRED.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: BearerAuth
$config = LLMPulse\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new LLMPulse\Api\AIAgentTrafficApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$project_id = 56; // int | Project ID
$range = 56; // int | Number of days to look back (alternative to from/to)
$from = new \DateTime('2013-10-20T19:20:30+01:00'); // \DateTime
$to = new \DateTime('2013-10-20T19:20:30+01:00'); // \DateTime | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier.
$source = 'source_example'; // string | Filter by a single AI source slug (e.g. chatgpt, perplexity, gemini, claude)
$granularity = 'granularity_example'; // string

try {
    $apiInstance->getAiTraffic($project_id, $range, $from, $to, $source, $granularity);
} catch (Exception $e) {
    echo 'Exception when calling AIAgentTrafficApi->getAiTraffic: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **project_id** | **int**| Project ID | |
| **range** | **int**| Number of days to look back (alternative to from/to) | [optional] |
| **from** | **\DateTime**|  | [optional] |
| **to** | **\DateTime**| End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. | [optional] |
| **source** | **string**| Filter by a single AI source slug (e.g. chatgpt, perplexity, gemini, claude) | [optional] |
| **granularity** | **string**|  | [optional] |

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

## `listAgentBots()`

```php
listAgentBots($project_id, $output): \LLMPulse\Model\AgentBotsResponse
```

AI bot catalog (Scale plan or above)

Static catalog of AI bots that Agent Analytics can identify. Useful for rendering filter UIs that mirror our internal classification (slug, display name, company, category, Cloudflare verified-bot mapping, description). Requires the Scale plan; lower tiers receive ERR_PLAN_REQUIRED. The equivalent MCP tool list_agent_bots is available on the Scale plan or above.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: BearerAuth
$config = LLMPulse\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new LLMPulse\Api\AIAgentTrafficApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$project_id = 56; // int | Project ID
$output = 'output_example'; // string | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.

try {
    $result = $apiInstance->listAgentBots($project_id, $output);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AIAgentTrafficApi->listAgentBots: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **project_id** | **int**| Project ID | |
| **output** | **string**| Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] |

### Return type

[**\LLMPulse\Model\AgentBotsResponse**](../Model/AgentBotsResponse.md)

### Authorization

[BearerAuth](../../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
