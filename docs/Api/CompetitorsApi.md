# LLMPulse\CompetitorsApi

The brands tracked alongside your own. Competitor ids are the actor_id values the metrics endpoints report against.

All URIs are relative to https://api.llmpulse.ai/api/v1, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**createCompetitor()**](CompetitorsApi.md#createCompetitor) | **POST** /competitors | Add a competitor |
| [**deleteCompetitor()**](CompetitorsApi.md#deleteCompetitor) | **DELETE** /competitors/{id} | Delete a competitor |
| [**getCompetitorDetails()**](CompetitorsApi.md#getCompetitorDetails) | **GET** /dimensions/competitors/{id} | Competitor details |
| [**listCompetitorSuggestions()**](CompetitorsApi.md#listCompetitorSuggestions) | **GET** /competitors/suggestions | List competitor suggestions |
| [**listCompetitors()**](CompetitorsApi.md#listCompetitors) | **GET** /dimensions/competitors | List competitors |
| [**updateCompetitor()**](CompetitorsApi.md#updateCompetitor) | **PATCH** /competitors/{id} | Update a competitor |


## `createCompetitor()`

```php
createCompetitor($create_competitor_request): \LLMPulse\Model\CompetitorCreateResponse
```

Add a competitor

Adds a competitor with its own citation URL matching rule. Honours the per-plan max competitors cap. Requires a `read_write` scope API key.

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
    $result = $apiInstance->createCompetitor($create_competitor_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling CompetitorsApi->createCompetitor: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **create_competitor_request** | [**\LLMPulse\Model\CreateCompetitorRequest**](../Model/CreateCompetitorRequest.md)|  | |

### Return type

[**\LLMPulse\Model\CompetitorCreateResponse**](../Model/CompetitorCreateResponse.md)

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

Deletes a competitor (irreversible). It disappears immediately and frees a competitor slot; a background job then deletes its mentions, citations, sentiment and share of voice history. Its ads, shopping products, local businesses and brand entities are kept and move to the project or another competitor they match, or stay unattributed. Requires a `read_write` scope API key.

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

## `getCompetitorDetails()`

```php
getCompetitorDetails($project_id, $id): \LLMPulse\Model\CompetitorDetails
```

Competitor details

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
    $result = $apiInstance->getCompetitorDetails($project_id, $id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling CompetitorsApi->getCompetitorDetails: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **project_id** | **int**| Project ID | |
| **id** | **int**|  | |

### Return type

[**\LLMPulse\Model\CompetitorDetails**](../Model/CompetitorDetails.md)

### Authorization

[BearerAuth](../../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `listCompetitorSuggestions()`

```php
listCompetitorSuggestions($project_id, $basis, $query, $page, $per_page, $output): \LLMPulse\Model\CompetitorSuggestionsResponse
```

List competitor suggestions

The two lists of the Suggested tab of the Competitors page. `basis=brands` (default) returns the competing brands the AI discovery proposed that are not tracked or rejected yet, with the names it would match and, when counted, how many answers name it (`mentions`). `basis=citations` returns the domains AI answers cite most that are not your own or tracked yet, with how many answers cite each (`citations`). `discovery` tells whether a discovery run is still loading. Read-only: it never starts a discovery run, which the page starts from its Discover button. Add a suggestion with POST /competitors.

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
$basis = 'brands'; // string
$query = 'query_example'; // string | Only suggestions whose brand name or domain contains this text
$page = 1; // int
$per_page = 20; // int
$output = 'output_example'; // string | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.

try {
    $result = $apiInstance->listCompetitorSuggestions($project_id, $basis, $query, $page, $per_page, $output);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling CompetitorsApi->listCompetitorSuggestions: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **project_id** | **int**| Project ID | |
| **basis** | **string**|  | [optional] [default to &#39;brands&#39;] |
| **query** | **string**| Only suggestions whose brand name or domain contains this text | [optional] |
| **page** | **int**|  | [optional] [default to 1] |
| **per_page** | **int**|  | [optional] [default to 20] |
| **output** | **string**| Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] |

### Return type

[**\LLMPulse\Model\CompetitorSuggestionsResponse**](../Model/CompetitorSuggestionsResponse.md)

### Authorization

[BearerAuth](../../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `listCompetitors()`

```php
listCompetitors($project_id, $include_project_brand, $output): \LLMPulse\Model\ListCompetitors200Response
```

List competitors

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
$include_project_brand = false; // bool | When true, prepends the project brand with actor_type=project and is_own=true
$output = 'output_example'; // string | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.

try {
    $result = $apiInstance->listCompetitors($project_id, $include_project_brand, $output);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling CompetitorsApi->listCompetitors: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **project_id** | **int**| Project ID | |
| **include_project_brand** | **bool**| When true, prepends the project brand with actor_type&#x3D;project and is_own&#x3D;true | [optional] [default to false] |
| **output** | **string**| Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] |

### Return type

[**\LLMPulse\Model\ListCompetitors200Response**](../Model/ListCompetitors200Response.md)

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

Updates brand_name, the competitor website domain or host, matching_names (full replacement list; the brand name is always included automatically), color and/or the citation URL matching rule. Website domain/host and citation-rule changes share one seven-day cooldown per competitor; other fields remain editable during the cooldown. Name, website or citation-rule changes re-run historical matching in the background: the competitor shows processing=true for a few minutes and further edits are rejected meanwhile. Requires a `read_write` scope API key.

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
