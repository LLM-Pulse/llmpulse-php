# LLMPulse\BingWebmasterToolsApi



All URIs are relative to https://api.llmpulse.ai/api/v1, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**getBingWebmasterPages()**](BingWebmasterToolsApi.md#getBingWebmasterPages) | **GET** /bing_webmaster/pages | Top Bing Webmaster Tools pages (Growth+) |
| [**getBingWebmasterQueries()**](BingWebmasterToolsApi.md#getBingWebmasterQueries) | **GET** /bing_webmaster/queries | Top Bing Webmaster Tools queries (Growth+) |
| [**getBingWebmasterSummary()**](BingWebmasterToolsApi.md#getBingWebmasterSummary) | **GET** /bing_webmaster/summary | Bing Webmaster Tools summary (Growth+) |
| [**getBingWebmasterTimeseries()**](BingWebmasterToolsApi.md#getBingWebmasterTimeseries) | **GET** /bing_webmaster/timeseries | Bing Webmaster Tools time series (Growth+) |


## `getBingWebmasterPages()`

```php
getBingWebmasterPages($project_id, $range, $from, $to, $sort, $page, $per_page, $output): \LLMPulse\Model\BingWebmasterListResponse
```

Top Bing Webmaster Tools pages (Growth+)

The landing pages of the project's connected Bing Webmaster Tools site in Bing Search, ranked and paginated. Each row sums the weekly figures Bing reports for the weeks whose week_ending (the Friday that closes a Bing week) falls in the window: clicks, impressions, ctr (a 0..1 fraction), avg_impression_position weighted by impressions and avg_click_position weighted by clicks (null without clicks). Bing reports only its top pages of each week, about 100, so the rows are not a complete set and never add up to /bing_webmaster/summary. weeks_covered counts the weeks found in the window and data_through is the last week_ending synced. history_current is false right after the site was changed and before its first sync: data is then empty. Requires a connected Bing Webmaster Tools site (ERR_BING_WEBMASTER_NOT_CONNECTED) and the Growth plan or above.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: BearerAuth
$config = LLMPulse\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new LLMPulse\Api\BingWebmasterToolsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$project_id = 56; // int | Project ID
$range = 56; // int | Number of days to look back, today included (alternative to from/to, which win when both are given). At most 487, the window the Search Console endpoints accept; about 13 months of Bing data are kept. A value that is not a plain positive number returns 422 ERR_INVALID_PARAM even beside from/to.
$from = new \DateTime('2013-10-20T19:20:30+01:00'); // \DateTime | Start date (YYYY-MM-DD). Without from and to, the window is the last 30 days, today included; with only to, from is 30 days before today.
$to = new \DateTime('2013-10-20T19:20:30+01:00'); // \DateTime | End date (YYYY-MM-DD), inclusive. Defaults to today. data_through in the response says how far the synced data reaches.
$sort = 'impressions'; // string | Sort key. impressions, clicks and ctr sort descending, the two positions ascending; rows without a value sort last.
$page = 1; // int
$per_page = 20; // int
$output = 'output_example'; // string | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.

try {
    $result = $apiInstance->getBingWebmasterPages($project_id, $range, $from, $to, $sort, $page, $per_page, $output);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling BingWebmasterToolsApi->getBingWebmasterPages: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **project_id** | **int**| Project ID | |
| **range** | **int**| Number of days to look back, today included (alternative to from/to, which win when both are given). At most 487, the window the Search Console endpoints accept; about 13 months of Bing data are kept. A value that is not a plain positive number returns 422 ERR_INVALID_PARAM even beside from/to. | [optional] |
| **from** | **\DateTime**| Start date (YYYY-MM-DD). Without from and to, the window is the last 30 days, today included; with only to, from is 30 days before today. | [optional] |
| **to** | **\DateTime**| End date (YYYY-MM-DD), inclusive. Defaults to today. data_through in the response says how far the synced data reaches. | [optional] |
| **sort** | **string**| Sort key. impressions, clicks and ctr sort descending, the two positions ascending; rows without a value sort last. | [optional] [default to &#39;impressions&#39;] |
| **page** | **int**|  | [optional] [default to 1] |
| **per_page** | **int**|  | [optional] [default to 20] |
| **output** | **string**| Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] |

### Return type

[**\LLMPulse\Model\BingWebmasterListResponse**](../Model/BingWebmasterListResponse.md)

### Authorization

[BearerAuth](../../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getBingWebmasterQueries()`

```php
getBingWebmasterQueries($project_id, $range, $from, $to, $sort, $page, $per_page, $output): \LLMPulse\Model\BingWebmasterListResponse
```

Top Bing Webmaster Tools queries (Growth+)

The Bing search queries of the project's connected Bing Webmaster Tools site, ranked and paginated. Each row sums the weekly figures Bing reports for the weeks whose week_ending (the Friday that closes a Bing week) falls in the window: clicks, impressions, ctr (a 0..1 fraction), avg_impression_position weighted by impressions and avg_click_position weighted by clicks (null without clicks). Bing reports only its top queries of each week, about 100, so the rows are not a complete set and never add up to /bing_webmaster/summary. weeks_covered counts the weeks found in the window and data_through is the last week_ending synced. history_current is false right after the site was changed and before its first sync: data is then empty. Requires a connected Bing Webmaster Tools site (ERR_BING_WEBMASTER_NOT_CONNECTED) and the Growth plan or above.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: BearerAuth
$config = LLMPulse\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new LLMPulse\Api\BingWebmasterToolsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$project_id = 56; // int | Project ID
$range = 56; // int | Number of days to look back, today included (alternative to from/to, which win when both are given). At most 487, the window the Search Console endpoints accept; about 13 months of Bing data are kept. A value that is not a plain positive number returns 422 ERR_INVALID_PARAM even beside from/to.
$from = new \DateTime('2013-10-20T19:20:30+01:00'); // \DateTime | Start date (YYYY-MM-DD). Without from and to, the window is the last 30 days, today included; with only to, from is 30 days before today.
$to = new \DateTime('2013-10-20T19:20:30+01:00'); // \DateTime | End date (YYYY-MM-DD), inclusive. Defaults to today. data_through in the response says how far the synced data reaches.
$sort = 'impressions'; // string | Sort key. impressions, clicks and ctr sort descending, the two positions ascending; rows without a value sort last.
$page = 1; // int
$per_page = 20; // int
$output = 'output_example'; // string | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.

try {
    $result = $apiInstance->getBingWebmasterQueries($project_id, $range, $from, $to, $sort, $page, $per_page, $output);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling BingWebmasterToolsApi->getBingWebmasterQueries: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **project_id** | **int**| Project ID | |
| **range** | **int**| Number of days to look back, today included (alternative to from/to, which win when both are given). At most 487, the window the Search Console endpoints accept; about 13 months of Bing data are kept. A value that is not a plain positive number returns 422 ERR_INVALID_PARAM even beside from/to. | [optional] |
| **from** | **\DateTime**| Start date (YYYY-MM-DD). Without from and to, the window is the last 30 days, today included; with only to, from is 30 days before today. | [optional] |
| **to** | **\DateTime**| End date (YYYY-MM-DD), inclusive. Defaults to today. data_through in the response says how far the synced data reaches. | [optional] |
| **sort** | **string**| Sort key. impressions, clicks and ctr sort descending, the two positions ascending; rows without a value sort last. | [optional] [default to &#39;impressions&#39;] |
| **page** | **int**|  | [optional] [default to 1] |
| **per_page** | **int**|  | [optional] [default to 20] |
| **output** | **string**| Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] |

### Return type

[**\LLMPulse\Model\BingWebmasterListResponse**](../Model/BingWebmasterListResponse.md)

### Authorization

[BearerAuth](../../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getBingWebmasterSummary()`

```php
getBingWebmasterSummary($project_id, $range, $from, $to): \LLMPulse\Model\BingWebmasterSummaryResponse
```

Bing Webmaster Tools summary (Growth+)

Bing Search clicks, impressions and ctr (a 0..1 fraction) of the project's connected Bing Webmaster Tools site over a date range, summed from the daily site totals synced once a day. Bing reports no average position in its daily totals. About 13 months of history are kept; data_through is the last day synced, and later days are missing, not zero. history_current is false right after the site was changed in Preferences > Project Settings > Connections and before its first sync: the totals are then zero and data_through and last_synced_at null. A connection whose sync_status is on_hold (Bing refused the stored API key, or the site is no longer verified) still answers from the data already synced. Requires a connected Bing Webmaster Tools site and the Growth plan or above; otherwise returns ERR_BING_WEBMASTER_NOT_CONNECTED (with meta.connect_url) or ERR_PLAN_REQUIRED.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: BearerAuth
$config = LLMPulse\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new LLMPulse\Api\BingWebmasterToolsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$project_id = 56; // int | Project ID
$range = 56; // int | Number of days to look back, today included (alternative to from/to, which win when both are given). At most 487, the window the Search Console endpoints accept; about 13 months of Bing data are kept. A value that is not a plain positive number returns 422 ERR_INVALID_PARAM even beside from/to.
$from = new \DateTime('2013-10-20T19:20:30+01:00'); // \DateTime | Start date (YYYY-MM-DD). Without from and to, the window is the last 30 days, today included; with only to, from is 30 days before today.
$to = new \DateTime('2013-10-20T19:20:30+01:00'); // \DateTime | End date (YYYY-MM-DD), inclusive. Defaults to today. data_through in the response says how far the synced data reaches.

try {
    $result = $apiInstance->getBingWebmasterSummary($project_id, $range, $from, $to);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling BingWebmasterToolsApi->getBingWebmasterSummary: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **project_id** | **int**| Project ID | |
| **range** | **int**| Number of days to look back, today included (alternative to from/to, which win when both are given). At most 487, the window the Search Console endpoints accept; about 13 months of Bing data are kept. A value that is not a plain positive number returns 422 ERR_INVALID_PARAM even beside from/to. | [optional] |
| **from** | **\DateTime**| Start date (YYYY-MM-DD). Without from and to, the window is the last 30 days, today included; with only to, from is 30 days before today. | [optional] |
| **to** | **\DateTime**| End date (YYYY-MM-DD), inclusive. Defaults to today. data_through in the response says how far the synced data reaches. | [optional] |

### Return type

[**\LLMPulse\Model\BingWebmasterSummaryResponse**](../Model/BingWebmasterSummaryResponse.md)

### Authorization

[BearerAuth](../../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getBingWebmasterTimeseries()`

```php
getBingWebmasterTimeseries($project_id, $range, $from, $to, $granularity, $output): \LLMPulse\Model\BingWebmasterTimeseriesResponse
```

Bing Webmaster Tools time series (Growth+)

Bing Search clicks, impressions and ctr (a 0..1 fraction) of the project's connected Bing Webmaster Tools site, bucketed by day, week (starting Monday) or month from the daily site totals synced once a day. Days without synced data are left out of the series, not reported as zero. Bing reports no average position in its daily totals. About 13 months of history are kept. history_current is false right after the site was changed and before its first sync: data is then empty. Requires a connected Bing Webmaster Tools site (ERR_BING_WEBMASTER_NOT_CONNECTED) and the Growth plan or above.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: BearerAuth
$config = LLMPulse\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new LLMPulse\Api\BingWebmasterToolsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$project_id = 56; // int | Project ID
$range = 56; // int | Number of days to look back, today included (alternative to from/to, which win when both are given). At most 487, the window the Search Console endpoints accept; about 13 months of Bing data are kept. A value that is not a plain positive number returns 422 ERR_INVALID_PARAM even beside from/to.
$from = new \DateTime('2013-10-20T19:20:30+01:00'); // \DateTime | Start date (YYYY-MM-DD). Without from and to, the window is the last 30 days, today included; with only to, from is 30 days before today.
$to = new \DateTime('2013-10-20T19:20:30+01:00'); // \DateTime | End date (YYYY-MM-DD), inclusive. Defaults to today. data_through in the response says how far the synced data reaches.
$granularity = 'granularity_example'; // string
$output = 'output_example'; // string | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.

try {
    $result = $apiInstance->getBingWebmasterTimeseries($project_id, $range, $from, $to, $granularity, $output);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling BingWebmasterToolsApi->getBingWebmasterTimeseries: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **project_id** | **int**| Project ID | |
| **range** | **int**| Number of days to look back, today included (alternative to from/to, which win when both are given). At most 487, the window the Search Console endpoints accept; about 13 months of Bing data are kept. A value that is not a plain positive number returns 422 ERR_INVALID_PARAM even beside from/to. | [optional] |
| **from** | **\DateTime**| Start date (YYYY-MM-DD). Without from and to, the window is the last 30 days, today included; with only to, from is 30 days before today. | [optional] |
| **to** | **\DateTime**| End date (YYYY-MM-DD), inclusive. Defaults to today. data_through in the response says how far the synced data reaches. | [optional] |
| **granularity** | **string**|  | [optional] |
| **output** | **string**| Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] |

### Return type

[**\LLMPulse\Model\BingWebmasterTimeseriesResponse**](../Model/BingWebmasterTimeseriesResponse.md)

### Authorization

[BearerAuth](../../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
