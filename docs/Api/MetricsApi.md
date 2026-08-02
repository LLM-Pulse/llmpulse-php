# LLMPulse\MetricsApi

Aggregated time-series, summary, Share of Voice, top sources and agent-traffic metrics

All URIs are relative to https://api.llmpulse.ai/api/v1, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**getAgentTraffic()**](MetricsApi.md#getAgentTraffic) | **GET** /metrics/agent_traffic | AI bot crawler traffic (Scale+, Beta) |
| [**getAiTraffic()**](MetricsApi.md#getAiTraffic) | **GET** /metrics/ai_traffic | AI referral traffic (Scale+) |
| [**getPromptSummary()**](MetricsApi.md#getPromptSummary) | **GET** /metrics/prompt_summary | Per-prompt metrics summary |
| [**getShareOfVoice()**](MetricsApi.md#getShareOfVoice) | **GET** /metrics/sov | Share of Voice |
| [**getSummary()**](MetricsApi.md#getSummary) | **GET** /metrics/summary | Aggregated metrics summary |
| [**getTimeseries()**](MetricsApi.md#getTimeseries) | **GET** /metrics/timeseries | Time-series metrics |
| [**getTopSources()**](MetricsApi.md#getTopSources) | **GET** /metrics/top_sources | Top cited sources |


## `getAgentTraffic()`

```php
getAgentTraffic($project_id, $range, $from, $to, $bot, $company, $group_by, $granularity): \LLMPulse\Model\AgentTrafficResponse
```

AI bot crawler traffic (Scale+, Beta)

Aggregated AI bot traffic hitting the project's origin server (GPTBot, PerplexityBot, ClaudeBot, OAI-SearchBot, Google-Extended, etc.). Sourced from Cloudflare or CSV uploads. Requires the Scale plan; lower tiers receive ERR_PLAN_REQUIRED.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: BearerAuth
$config = LLMPulse\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new LLMPulse\Api\MetricsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$project_id = 56; // int | Project ID
$range = 56; // int | Number of days to look back (alternative to from/to)
$from = new \DateTime('2013-10-20T19:20:30+01:00'); // \DateTime
$to = new \DateTime('2013-10-20T19:20:30+01:00'); // \DateTime
$bot = 'bot_example'; // string | Filter by bot slug (e.g. gptbot, claudebot, perplexitybot)
$company = 'company_example'; // string | Filter by company (e.g. openai, anthropic, google)
$group_by = 'bot'; // string
$granularity = 'granularity_example'; // string

try {
    $result = $apiInstance->getAgentTraffic($project_id, $range, $from, $to, $bot, $company, $group_by, $granularity);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling MetricsApi->getAgentTraffic: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **project_id** | **int**| Project ID | |
| **range** | **int**| Number of days to look back (alternative to from/to) | [optional] |
| **from** | **\DateTime**|  | [optional] |
| **to** | **\DateTime**|  | [optional] |
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

AI referral traffic (Scale+)

AI referral traffic for a project: human visits arriving from AI assistants (ChatGPT, Perplexity, Gemini, Claude, etc.), measured from the connected web analytics provider (Google Analytics 4, Adobe Analytics, PostHog, Plausible or Piano). Returns per-source users, sessions and conversions with totals and a conversion rate. Requires a connected provider and the Scale plan; otherwise returns ERR_AI_TRAFFIC_NOT_CONNECTED or ERR_PLAN_REQUIRED.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: BearerAuth
$config = LLMPulse\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new LLMPulse\Api\MetricsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$project_id = 56; // int | Project ID
$range = 56; // int | Number of days to look back (alternative to from/to)
$from = new \DateTime('2013-10-20T19:20:30+01:00'); // \DateTime
$to = new \DateTime('2013-10-20T19:20:30+01:00'); // \DateTime
$source = 'source_example'; // string | Filter by a single AI source slug (e.g. chatgpt, perplexity, gemini, claude)
$granularity = 'granularity_example'; // string

try {
    $apiInstance->getAiTraffic($project_id, $range, $from, $to, $source, $granularity);
} catch (Exception $e) {
    echo 'Exception when calling MetricsApi->getAiTraffic: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **project_id** | **int**| Project ID | |
| **range** | **int**| Number of days to look back (alternative to from/to) | [optional] |
| **from** | **\DateTime**|  | [optional] |
| **to** | **\DateTime**|  | [optional] |
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

## `getPromptSummary()`

```php
getPromptSummary($project_id, $range, $from, $to, $breakdown, $model, $collection_id, $country_code, $language_code, $prompt, $prompt_type, $brand_kind, $sort, $sort_dir, $page, $per_page, $output): \LLMPulse\Model\PromptSummaryResponse
```

Per-prompt metrics summary

Paginated per-prompt aggregated metrics. Returns responses, mentions, citations, mention_rate, citation_rate, avg_mention_position and avg_position per prompt. Citations and citation rate include visible citations and background source references; avg_position uses visible citations only. Pass `breakdown=model` to split each prompt by model.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: BearerAuth
$config = LLMPulse\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new LLMPulse\Api\MetricsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$project_id = 56; // int | Project ID
$range = 56; // int | Number of days to look back (alternative to from/to)
$from = new \DateTime('2013-10-20T19:20:30+01:00'); // \DateTime
$to = new \DateTime('2013-10-20T19:20:30+01:00'); // \DateTime
$breakdown = 'breakdown_example'; // string | Add per-(prompt, model) rows to the output
$model = 'model_example'; // string | Filter by AI model. Models the API key's user has not enabled are silently dropped.
$collection_id = 56; // int
$country_code = 'country_code_example'; // string | ISO country code (e.g. US, GB, DE)
$language_code = 'language_code_example'; // string | ISO language code (e.g. en, es, de)
$prompt = 56; // int | Filter by prompt ID
$prompt_type = 'prompt_type_example'; // string | Filter by prompt type (search intent)
$brand_kind = 'brand_kind_example'; // string | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default.
$sort = 'responses'; // string
$sort_dir = 'desc'; // string
$page = 1; // int
$per_page = 20; // int
$output = 'output_example'; // string | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.

try {
    $result = $apiInstance->getPromptSummary($project_id, $range, $from, $to, $breakdown, $model, $collection_id, $country_code, $language_code, $prompt, $prompt_type, $brand_kind, $sort, $sort_dir, $page, $per_page, $output);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling MetricsApi->getPromptSummary: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **project_id** | **int**| Project ID | |
| **range** | **int**| Number of days to look back (alternative to from/to) | [optional] |
| **from** | **\DateTime**|  | [optional] |
| **to** | **\DateTime**|  | [optional] |
| **breakdown** | **string**| Add per-(prompt, model) rows to the output | [optional] |
| **model** | **string**| Filter by AI model. Models the API key&#39;s user has not enabled are silently dropped. | [optional] |
| **collection_id** | **int**|  | [optional] |
| **country_code** | **string**| ISO country code (e.g. US, GB, DE) | [optional] |
| **language_code** | **string**| ISO language code (e.g. en, es, de) | [optional] |
| **prompt** | **int**| Filter by prompt ID | [optional] |
| **prompt_type** | **string**| Filter by prompt type (search intent) | [optional] |
| **brand_kind** | **string**| Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. | [optional] |
| **sort** | **string**|  | [optional] [default to &#39;responses&#39;] |
| **sort_dir** | **string**|  | [optional] [default to &#39;desc&#39;] |
| **page** | **int**|  | [optional] [default to 1] |
| **per_page** | **int**|  | [optional] [default to 20] |
| **output** | **string**| Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] |

### Return type

[**\LLMPulse\Model\PromptSummaryResponse**](../Model/PromptSummaryResponse.md)

### Authorization

[BearerAuth](../../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getShareOfVoice()`

```php
getShareOfVoice($project_id, $range, $from, $to, $granularity, $competitors, $model, $collection_id, $prompt, $prompt_type, $brand_kind, $output, $view): \LLMPulse\Model\SovResponse
```

Share of Voice

Share of Voice breakdown comparing your project to competitors. Returns over_time, current snapshot, and a Top-4 + Others breakdown.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: BearerAuth
$config = LLMPulse\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new LLMPulse\Api\MetricsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$project_id = 56; // int | Project ID
$range = 56; // int | Number of days to look back (alternative to from/to)
$from = new \DateTime('2013-10-20T19:20:30+01:00'); // \DateTime
$to = new \DateTime('2013-10-20T19:20:30+01:00'); // \DateTime
$granularity = 'granularity_example'; // string
$competitors = 'competitors_example'; // string | Comma-separated competitor IDs (unknown IDs return ERR_INVALID_PARAM)
$model = 'model_example'; // string | Filter by AI model. Models the API key's user has not enabled are silently dropped.
$collection_id = 56; // int
$prompt = 56; // int | Filter by prompt ID
$prompt_type = 'prompt_type_example'; // string | Filter by prompt type (search intent)
$brand_kind = 'brand_kind_example'; // string | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default.
$output = 'output_example'; // string | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
$view = 'over_time'; // string | Which Share of Voice projection to flatten. Only valid together with 'output'. 'over_time' (default) is one row per date and actor, 'current' the ranked snapshot, 'breakdown' the Top 4 plus Others.

try {
    $result = $apiInstance->getShareOfVoice($project_id, $range, $from, $to, $granularity, $competitors, $model, $collection_id, $prompt, $prompt_type, $brand_kind, $output, $view);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling MetricsApi->getShareOfVoice: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **project_id** | **int**| Project ID | |
| **range** | **int**| Number of days to look back (alternative to from/to) | [optional] |
| **from** | **\DateTime**|  | [optional] |
| **to** | **\DateTime**|  | [optional] |
| **granularity** | **string**|  | [optional] |
| **competitors** | **string**| Comma-separated competitor IDs (unknown IDs return ERR_INVALID_PARAM) | [optional] |
| **model** | **string**| Filter by AI model. Models the API key&#39;s user has not enabled are silently dropped. | [optional] |
| **collection_id** | **int**|  | [optional] |
| **prompt** | **int**| Filter by prompt ID | [optional] |
| **prompt_type** | **string**| Filter by prompt type (search intent) | [optional] |
| **brand_kind** | **string**| Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. | [optional] |
| **output** | **string**| Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] |
| **view** | **string**| Which Share of Voice projection to flatten. Only valid together with &#39;output&#39;. &#39;over_time&#39; (default) is one row per date and actor, &#39;current&#39; the ranked snapshot, &#39;breakdown&#39; the Top 4 plus Others. | [optional] [default to &#39;over_time&#39;] |

### Return type

[**\LLMPulse\Model\SovResponse**](../Model/SovResponse.md)

### Authorization

[BearerAuth](../../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getSummary()`

```php
getSummary($project_id, $metrics, $granularity, $range, $from, $to, $competitors, $model, $collection_id, $prompt, $prompt_type, $brand_kind, $output): \LLMPulse\Model\SummaryResponse
```

Aggregated metrics summary

Same as /metrics/timeseries but adds a `summary` block with total/min/max/last per metric per actor, plus a `position_distribution` block (Position 1, Position 2, Position 3+). Citations and citation rate include visible citations and background source references. Background references use position 0 and are excluded from avg_position and position distributions. `total` is a SUM for count metrics (mentions, citations, responses) and an AVERAGE across periods for rate/percentage and average metrics (visibility/mention_rate, citation_rate, ai_visibility_score, sentiment shares, avg_position, avg_mention_position, net_sentiment); rates are never summed. Each summary row carries an `aggregation` field (`sum` or `average`).

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: BearerAuth
$config = LLMPulse\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new LLMPulse\Api\MetricsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$project_id = 56; // int | Project ID
$metrics = 'metrics_example'; // string | Comma-separated list of metrics: mentions, citations, responses, mention_rate, visibility (alias for mention_rate), weighted_visibility, ai_visibility_score (alias for weighted_visibility), citation_rate, avg_position, avg_mention_position, net_sentiment, sentiment_very_positive, sentiment_positive, sentiment_neutral, sentiment_negative, sentiment_very_negative. Citations and citation_rate include visible citations and background source references; avg_position uses visible citations only.
$granularity = 'granularity_example'; // string
$range = 56; // int | Number of days to look back (alternative to from/to)
$from = new \DateTime('2013-10-20T19:20:30+01:00'); // \DateTime
$to = new \DateTime('2013-10-20T19:20:30+01:00'); // \DateTime
$competitors = 'competitors_example'; // string | Comma-separated competitor IDs (unknown IDs return ERR_INVALID_PARAM)
$model = 'model_example'; // string | Filter by AI model. Models the API key's user has not enabled are silently dropped.
$collection_id = 56; // int
$prompt = 56; // int | Filter by prompt ID
$prompt_type = 'prompt_type_example'; // string | Filter by prompt type (search intent)
$brand_kind = 'brand_kind_example'; // string | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default.
$output = 'output_example'; // string | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.

try {
    $result = $apiInstance->getSummary($project_id, $metrics, $granularity, $range, $from, $to, $competitors, $model, $collection_id, $prompt, $prompt_type, $brand_kind, $output);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling MetricsApi->getSummary: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **project_id** | **int**| Project ID | |
| **metrics** | **string**| Comma-separated list of metrics: mentions, citations, responses, mention_rate, visibility (alias for mention_rate), weighted_visibility, ai_visibility_score (alias for weighted_visibility), citation_rate, avg_position, avg_mention_position, net_sentiment, sentiment_very_positive, sentiment_positive, sentiment_neutral, sentiment_negative, sentiment_very_negative. Citations and citation_rate include visible citations and background source references; avg_position uses visible citations only. | [optional] |
| **granularity** | **string**|  | [optional] |
| **range** | **int**| Number of days to look back (alternative to from/to) | [optional] |
| **from** | **\DateTime**|  | [optional] |
| **to** | **\DateTime**|  | [optional] |
| **competitors** | **string**| Comma-separated competitor IDs (unknown IDs return ERR_INVALID_PARAM) | [optional] |
| **model** | **string**| Filter by AI model. Models the API key&#39;s user has not enabled are silently dropped. | [optional] |
| **collection_id** | **int**|  | [optional] |
| **prompt** | **int**| Filter by prompt ID | [optional] |
| **prompt_type** | **string**| Filter by prompt type (search intent) | [optional] |
| **brand_kind** | **string**| Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. | [optional] |
| **output** | **string**| Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] |

### Return type

[**\LLMPulse\Model\SummaryResponse**](../Model/SummaryResponse.md)

### Authorization

[BearerAuth](../../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getTimeseries()`

```php
getTimeseries($project_id, $metrics, $granularity, $range, $from, $to, $competitors, $model, $collection_id, $country_code, $language_code, $prompt, $prompt_type, $brand_kind, $include_project, $output): \LLMPulse\Model\TimeseriesResponse
```

Time-series metrics

Returns time-series data for one or more metrics, broken down by actor (project + competitors). Supports day/week/month granularity, with sticky carry-forward semantics for week/month aggregates.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: BearerAuth
$config = LLMPulse\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new LLMPulse\Api\MetricsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$project_id = 56; // int | Project ID
$metrics = 'metrics_example'; // string | Comma-separated list of metrics: mentions, citations, responses, mention_rate, visibility (alias for mention_rate), weighted_visibility, ai_visibility_score (alias for weighted_visibility), citation_rate, avg_position, avg_mention_position, net_sentiment, sentiment_very_positive, sentiment_positive, sentiment_neutral, sentiment_negative, sentiment_very_negative. Citations and citation_rate include visible citations and background source references; avg_position uses visible citations only.
$granularity = 'granularity_example'; // string
$range = 56; // int | Number of days to look back (alternative to from/to)
$from = new \DateTime('2013-10-20T19:20:30+01:00'); // \DateTime
$to = new \DateTime('2013-10-20T19:20:30+01:00'); // \DateTime
$competitors = 'competitors_example'; // string | Comma-separated competitor IDs (unknown IDs return ERR_INVALID_PARAM)
$model = 'model_example'; // string | Filter by AI model. Models the API key's user has not enabled are silently dropped.
$collection_id = 56; // int
$country_code = 'country_code_example'; // string | ISO country code (e.g. US, GB, DE)
$language_code = 'language_code_example'; // string | ISO language code (e.g. en, es, de)
$prompt = 56; // int | Filter by prompt ID
$prompt_type = 'prompt_type_example'; // string | Filter by prompt type (search intent)
$brand_kind = 'brand_kind_example'; // string | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default.
$include_project = true; // bool
$output = 'output_example'; // string | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.

try {
    $result = $apiInstance->getTimeseries($project_id, $metrics, $granularity, $range, $from, $to, $competitors, $model, $collection_id, $country_code, $language_code, $prompt, $prompt_type, $brand_kind, $include_project, $output);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling MetricsApi->getTimeseries: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **project_id** | **int**| Project ID | |
| **metrics** | **string**| Comma-separated list of metrics: mentions, citations, responses, mention_rate, visibility (alias for mention_rate), weighted_visibility, ai_visibility_score (alias for weighted_visibility), citation_rate, avg_position, avg_mention_position, net_sentiment, sentiment_very_positive, sentiment_positive, sentiment_neutral, sentiment_negative, sentiment_very_negative. Citations and citation_rate include visible citations and background source references; avg_position uses visible citations only. | [optional] |
| **granularity** | **string**|  | [optional] |
| **range** | **int**| Number of days to look back (alternative to from/to) | [optional] |
| **from** | **\DateTime**|  | [optional] |
| **to** | **\DateTime**|  | [optional] |
| **competitors** | **string**| Comma-separated competitor IDs (unknown IDs return ERR_INVALID_PARAM) | [optional] |
| **model** | **string**| Filter by AI model. Models the API key&#39;s user has not enabled are silently dropped. | [optional] |
| **collection_id** | **int**|  | [optional] |
| **country_code** | **string**| ISO country code (e.g. US, GB, DE) | [optional] |
| **language_code** | **string**| ISO language code (e.g. en, es, de) | [optional] |
| **prompt** | **int**| Filter by prompt ID | [optional] |
| **prompt_type** | **string**| Filter by prompt type (search intent) | [optional] |
| **brand_kind** | **string**| Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. | [optional] |
| **include_project** | **bool**|  | [optional] [default to true] |
| **output** | **string**| Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] |

### Return type

[**\LLMPulse\Model\TimeseriesResponse**](../Model/TimeseriesResponse.md)

### Authorization

[BearerAuth](../../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getTopSources()`

```php
getTopSources($project_id, $range, $from, $to, $model, $collection_id, $country_code, $language_code, $prompt, $prompt_type, $brand_kind, $sort, $query, $page, $per_page, $output): \LLMPulse\Model\TopSourcesResponse
```

Top cited sources

Registrable domains most frequently cited in AI responses for the project, including visible citations and background source references. This endpoint remains a domain rollup when exact-subdomain matching is enabled. Results can be sorted by total responses, average mention rate, or average visibility.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: BearerAuth
$config = LLMPulse\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new LLMPulse\Api\MetricsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$project_id = 56; // int | Project ID
$range = 56; // int | Number of days to look back (alternative to from/to)
$from = new \DateTime('2013-10-20T19:20:30+01:00'); // \DateTime
$to = new \DateTime('2013-10-20T19:20:30+01:00'); // \DateTime
$model = 'model_example'; // string | Filter by AI model. Models the API key's user has not enabled are silently dropped.
$collection_id = 56; // int
$country_code = 'country_code_example'; // string | ISO country code (e.g. US, GB, DE)
$language_code = 'language_code_example'; // string | ISO language code (e.g. en, es, de)
$prompt = 56; // int | Filter by prompt ID
$prompt_type = 'prompt_type_example'; // string | Filter by prompt type (search intent)
$brand_kind = 'brand_kind_example'; // string | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default.
$sort = 'total_responses'; // string
$query = 'query_example'; // string | Filter domains by case-insensitive partial match
$page = 1; // int
$per_page = 20; // int
$output = 'output_example'; // string | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.

try {
    $result = $apiInstance->getTopSources($project_id, $range, $from, $to, $model, $collection_id, $country_code, $language_code, $prompt, $prompt_type, $brand_kind, $sort, $query, $page, $per_page, $output);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling MetricsApi->getTopSources: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **project_id** | **int**| Project ID | |
| **range** | **int**| Number of days to look back (alternative to from/to) | [optional] |
| **from** | **\DateTime**|  | [optional] |
| **to** | **\DateTime**|  | [optional] |
| **model** | **string**| Filter by AI model. Models the API key&#39;s user has not enabled are silently dropped. | [optional] |
| **collection_id** | **int**|  | [optional] |
| **country_code** | **string**| ISO country code (e.g. US, GB, DE) | [optional] |
| **language_code** | **string**| ISO language code (e.g. en, es, de) | [optional] |
| **prompt** | **int**| Filter by prompt ID | [optional] |
| **prompt_type** | **string**| Filter by prompt type (search intent) | [optional] |
| **brand_kind** | **string**| Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. | [optional] |
| **sort** | **string**|  | [optional] [default to &#39;total_responses&#39;] |
| **query** | **string**| Filter domains by case-insensitive partial match | [optional] |
| **page** | **int**|  | [optional] [default to 1] |
| **per_page** | **int**|  | [optional] [default to 20] |
| **output** | **string**| Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] |

### Return type

[**\LLMPulse\Model\TopSourcesResponse**](../Model/TopSourcesResponse.md)

### Authorization

[BearerAuth](../../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
