# LLMPulse\OwnedMediaCommunitiesApi



All URIs are relative to https://api.llmpulse.ai/api/v1, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**getOwnedMediaProfiles()**](OwnedMediaCommunitiesApi.md#getOwnedMediaProfiles) | **GET** /projects/{id}/owned_media | Get a project&#39;s owned-media profiles |
| [**getOwnedMediaSummary()**](OwnedMediaCommunitiesApi.md#getOwnedMediaSummary) | **GET** /dimensions/owned_media/summary | Get an owned-media summary |
| [**listOwnedMedia()**](OwnedMediaCommunitiesApi.md#listOwnedMedia) | **GET** /dimensions/owned_media | List owned-media citations |
| [**listOwnedMediaCitingPrompts()**](OwnedMediaCommunitiesApi.md#listOwnedMediaCitingPrompts) | **GET** /dimensions/owned_media/citing_prompts | List the answers citing an owned-media item |
| [**listRedditCitations()**](OwnedMediaCommunitiesApi.md#listRedditCitations) | **GET** /dimensions/reddit | List cited Reddit content |
| [**updateOwnedMediaProfiles()**](OwnedMediaCommunitiesApi.md#updateOwnedMediaProfiles) | **PATCH** /projects/{id}/owned_media | Update a project&#39;s owned-media profiles |


## `getOwnedMediaProfiles()`

```php
getOwnedMediaProfiles($id): \LLMPulse\Model\OwnedMediaProfilesResponse
```

Get a project's owned-media profiles

The profiles whose citations count as yours in the Owned Media and YouTube Intelligence reports, as Project Settings > Owned Media shows them. platforms holds one entry per platform with whether it is connected, how many extra profiles it accepts and its profiles: the main one, the extra ones, and on Reddit the claimed subreddits and usernames, each with its URL, handle, store (for apps), name, avatar and the state of the scrape that reads them. settings holds the current value of every field PATCH accepts, ready to edit and send back. Requires the Growth plan or above.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: BearerAuth
$config = LLMPulse\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new LLMPulse\Api\OwnedMediaCommunitiesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 56; // int | Project ID

try {
    $result = $apiInstance->getOwnedMediaProfiles($id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling OwnedMediaCommunitiesApi->getOwnedMediaProfiles: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **int**| Project ID | |

### Return type

[**\LLMPulse\Model\OwnedMediaProfilesResponse**](../Model/OwnedMediaProfilesResponse.md)

### Authorization

[BearerAuth](../../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getOwnedMediaSummary()`

```php
getOwnedMediaSummary($project_id, $provider, $model, $collection_id, $country_code, $language_code, $brand_kind, $range, $from, $to): \LLMPulse\Model\OwnedMediaSummaryResponse
```

Get an owned-media summary

The numbers behind one Owned Media tab. kpis gives the platform citations (total), yours (your profiles and their content), your_profile and your_content apart, and share_pct; previous gives the same KPIs for the period of the same length that ends just before from, and changes the difference (percent for counts, percentage points for share_pct, null when there is nothing to compare). weekly is the citations per week, yours against everyone else. by_model and by_country split every citation of the platform; content_types (reel, post, tv, pulse, or regular, shorts and live on YouTube) and age_buckets cover posts and videos. provider=mobile_apps adds stores, the per-store totals, and has no content type or age; provider=overview returns platforms, one rollup per platform the caller can read, and no breakdowns. A team member also needs the YouTube Intelligence permission for provider=youtube. Defaults to the last 30 days. Requires the Growth plan or above.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: BearerAuth
$config = LLMPulse\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new LLMPulse\Api\OwnedMediaCommunitiesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$project_id = 56; // int | Project ID
$provider = 'provider_example'; // string | The platform to summarize, or overview for every platform at once
$model = 'model_example'; // string | Filter by one AI model. It must be a model enabled for the API key's user: an unknown value, or a model the user has not enabled, returns 422 ERR_INVALID_PARAM with the valid values in the message.
$collection_id = 12,34; // string | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize.
$country_code = 'country_code_example'; // string | One ISO country code or a comma-separated list (e.g. US,GB,DE)
$language_code = 'language_code_example'; // string | One ISO language code or a comma-separated list (e.g. en,es,de)
$brand_kind = 'brand_kind_example'; // string | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default.
$range = 56; // int | Number of days to look back (alternative to from/to)
$from = new \DateTime('2013-10-20T19:20:30+01:00'); // \DateTime
$to = new \DateTime('2013-10-20T19:20:30+01:00'); // \DateTime | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier.

try {
    $result = $apiInstance->getOwnedMediaSummary($project_id, $provider, $model, $collection_id, $country_code, $language_code, $brand_kind, $range, $from, $to);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling OwnedMediaCommunitiesApi->getOwnedMediaSummary: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **project_id** | **int**| Project ID | |
| **provider** | **string**| The platform to summarize, or overview for every platform at once | |
| **model** | **string**| Filter by one AI model. It must be a model enabled for the API key&#39;s user: an unknown value, or a model the user has not enabled, returns 422 ERR_INVALID_PARAM with the valid values in the message. | [optional] |
| **collection_id** | **string**| One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize. | [optional] |
| **country_code** | **string**| One ISO country code or a comma-separated list (e.g. US,GB,DE) | [optional] |
| **language_code** | **string**| One ISO language code or a comma-separated list (e.g. en,es,de) | [optional] |
| **brand_kind** | **string**| Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. | [optional] |
| **range** | **int**| Number of days to look back (alternative to from/to) | [optional] |
| **from** | **\DateTime**|  | [optional] |
| **to** | **\DateTime**| End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. | [optional] |

### Return type

[**\LLMPulse\Model\OwnedMediaSummaryResponse**](../Model/OwnedMediaSummaryResponse.md)

### Authorization

[BearerAuth](../../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `listOwnedMedia()`

```php
listOwnedMedia($project_id, $provider, $page, $per_page, $view, $store, $owned, $model, $collection_id, $country_code, $language_code, $brand_kind, $range, $from, $to, $output): \LLMPulse\Model\OwnedMediaListResponse
```

List owned-media citations

Which owned-media content AI answers cite, by platform. `provider` is required. Each row carries a `yours` flag so you can compare your own presence against everyone else cited on the same platform. Video, post, channel and profile rows also carry their image (thumbnail_url or avatar_url, our cached copy where one exists), their average position in the answers and, on YouTube, the video id, the channel handle and URL, and the channel key that /dimensions/owned_media/citing_prompts accepts. view=own_citations returns the raw citations of the connected profile only and stays empty until a profile is connected. For Reddit use /dimensions/reddit. Requires the Growth plan or above.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: BearerAuth
$config = LLMPulse\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new LLMPulse\Api\OwnedMediaCommunitiesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$project_id = 56; // int | Project ID
$provider = 'provider_example'; // string | The platform to report on
$page = 1; // int
$per_page = 20; // int
$view = 'view_example'; // string | Row shape; the allowed set depends on provider
$store = 'google_play'; // string | provider=mobile_apps only
$owned = True; // bool | Return only rows belonging to the account's own connected profile
$model = 'model_example'; // string | Filter by one AI model. It must be a model enabled for the API key's user: an unknown value, or a model the user has not enabled, returns 422 ERR_INVALID_PARAM with the valid values in the message.
$collection_id = 12,34; // string | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize.
$country_code = 'country_code_example'; // string | One ISO country code or a comma-separated list (e.g. US,GB,DE)
$language_code = 'language_code_example'; // string | One ISO language code or a comma-separated list (e.g. en,es,de)
$brand_kind = 'brand_kind_example'; // string | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default.
$range = 56; // int | Number of days to look back (alternative to from/to)
$from = new \DateTime('2013-10-20T19:20:30+01:00'); // \DateTime
$to = new \DateTime('2013-10-20T19:20:30+01:00'); // \DateTime | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier.
$output = 'output_example'; // string | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.

try {
    $result = $apiInstance->listOwnedMedia($project_id, $provider, $page, $per_page, $view, $store, $owned, $model, $collection_id, $country_code, $language_code, $brand_kind, $range, $from, $to, $output);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling OwnedMediaCommunitiesApi->listOwnedMedia: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **project_id** | **int**| Project ID | |
| **provider** | **string**| The platform to report on | |
| **page** | **int**|  | [optional] [default to 1] |
| **per_page** | **int**|  | [optional] [default to 20] |
| **view** | **string**| Row shape; the allowed set depends on provider | [optional] |
| **store** | **string**| provider&#x3D;mobile_apps only | [optional] [default to &#39;google_play&#39;] |
| **owned** | **bool**| Return only rows belonging to the account&#39;s own connected profile | [optional] |
| **model** | **string**| Filter by one AI model. It must be a model enabled for the API key&#39;s user: an unknown value, or a model the user has not enabled, returns 422 ERR_INVALID_PARAM with the valid values in the message. | [optional] |
| **collection_id** | **string**| One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize. | [optional] |
| **country_code** | **string**| One ISO country code or a comma-separated list (e.g. US,GB,DE) | [optional] |
| **language_code** | **string**| One ISO language code or a comma-separated list (e.g. en,es,de) | [optional] |
| **brand_kind** | **string**| Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. | [optional] |
| **range** | **int**| Number of days to look back (alternative to from/to) | [optional] |
| **from** | **\DateTime**|  | [optional] |
| **to** | **\DateTime**| End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. | [optional] |
| **output** | **string**| Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] |

### Return type

[**\LLMPulse\Model\OwnedMediaListResponse**](../Model/OwnedMediaListResponse.md)

### Authorization

[BearerAuth](../../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `listOwnedMediaCitingPrompts()`

```php
listOwnedMediaCitingPrompts($project_id, $provider, $page, $per_page, $url, $profile, $model, $collection_id, $country_code, $language_code, $brand_kind, $range, $from, $to, $output): \LLMPulse\Model\OwnedMediaCitingPromptsResponse
```

List the answers citing an owned-media item

The drill-down behind one row of an Owned Media or YouTube Intelligence table. Pass exactly one of url (a post or video URL, any variant of it) or profile (a handle with or without @, a profile or channel URL, or the channel key the YouTube channels rows return). item describes it (title, image, owner, whether it is yours and its stats), citation_count and prompt_count count its citations in the window, and data lists the citing answers newest first, each with its prompt, answer id, model, country, language, execution date, a plain-text excerpt and its link in the app. It shows prompt and answer text, so a team member also needs the Prompts permission, and YouTube Intelligence for provider=youtube. Defaults to the last 30 days. Requires the Growth plan or above.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: BearerAuth
$config = LLMPulse\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new LLMPulse\Api\OwnedMediaCommunitiesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$project_id = 56; // int | Project ID
$provider = 'provider_example'; // string | The platform the item belongs to
$page = 1; // int
$per_page = 20; // int
$url = 'url_example'; // string | A post or video URL, or a profile or channel URL. Exclusive with profile
$profile = 'profile_example'; // string | A handle (with or without @), a profile or channel URL, or a YouTube channel key (handle:..., channel:... or name:...). Exclusive with url
$model = 'model_example'; // string | Filter by one AI model. It must be a model enabled for the API key's user: an unknown value, or a model the user has not enabled, returns 422 ERR_INVALID_PARAM with the valid values in the message.
$collection_id = 12,34; // string | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize.
$country_code = 'country_code_example'; // string | One ISO country code or a comma-separated list (e.g. US,GB,DE)
$language_code = 'language_code_example'; // string | One ISO language code or a comma-separated list (e.g. en,es,de)
$brand_kind = 'brand_kind_example'; // string | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default.
$range = 56; // int | Number of days to look back (alternative to from/to)
$from = new \DateTime('2013-10-20T19:20:30+01:00'); // \DateTime
$to = new \DateTime('2013-10-20T19:20:30+01:00'); // \DateTime | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier.
$output = 'output_example'; // string | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.

try {
    $result = $apiInstance->listOwnedMediaCitingPrompts($project_id, $provider, $page, $per_page, $url, $profile, $model, $collection_id, $country_code, $language_code, $brand_kind, $range, $from, $to, $output);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling OwnedMediaCommunitiesApi->listOwnedMediaCitingPrompts: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **project_id** | **int**| Project ID | |
| **provider** | **string**| The platform the item belongs to | |
| **page** | **int**|  | [optional] [default to 1] |
| **per_page** | **int**|  | [optional] [default to 20] |
| **url** | **string**| A post or video URL, or a profile or channel URL. Exclusive with profile | [optional] |
| **profile** | **string**| A handle (with or without @), a profile or channel URL, or a YouTube channel key (handle:..., channel:... or name:...). Exclusive with url | [optional] |
| **model** | **string**| Filter by one AI model. It must be a model enabled for the API key&#39;s user: an unknown value, or a model the user has not enabled, returns 422 ERR_INVALID_PARAM with the valid values in the message. | [optional] |
| **collection_id** | **string**| One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize. | [optional] |
| **country_code** | **string**| One ISO country code or a comma-separated list (e.g. US,GB,DE) | [optional] |
| **language_code** | **string**| One ISO language code or a comma-separated list (e.g. en,es,de) | [optional] |
| **brand_kind** | **string**| Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. | [optional] |
| **range** | **int**| Number of days to look back (alternative to from/to) | [optional] |
| **from** | **\DateTime**|  | [optional] |
| **to** | **\DateTime**| End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. | [optional] |
| **output** | **string**| Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] |

### Return type

[**\LLMPulse\Model\OwnedMediaCitingPromptsResponse**](../Model/OwnedMediaCitingPromptsResponse.md)

### Authorization

[BearerAuth](../../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `listRedditCitations()`

```php
listRedditCitations($project_id, $page, $per_page, $view, $subreddit, $author, $status, $owned, $brand, $order, $direction, $model, $collection_id, $country_code, $language_code, $brand_kind, $range, $from, $to, $output)
```

List cited Reddit content

Which Reddit content AI answers cite for your tracked prompts. view=subreddits (default) returns one row per subreddit with its citation count, unique authors and positive/negative sentiment split; view=authors returns one row per author; view=threads returns the individual cited threads with upvotes, comments, average position and dominant sentiment. Requires the Growth plan or above.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: BearerAuth
$config = LLMPulse\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new LLMPulse\Api\OwnedMediaCommunitiesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$project_id = 56; // int | Project ID
$page = 1; // int
$per_page = 20; // int
$view = 'subreddits'; // string
$subreddit = 'subreddit_example'; // string | Filter to one subreddit (name without the r/ prefix)
$author = 'author_example'; // string | Filter to one Reddit author
$status = 'status_example'; // string | view=threads only
$owned = True; // bool | Return only subreddits/authors the account has claimed as its own
$brand = 'brand_example'; // string | Filter to citations whose scraped Reddit content mentions a brand: 'brand' for the tracked brand, or a competitor id. Reads the page content, not the AI answer.
$order = 'order_example'; // string | Sort field; the allowed set depends on view
$direction = 'desc'; // string
$model = 'model_example'; // string | Filter by one AI model. It must be a model enabled for the API key's user: an unknown value, or a model the user has not enabled, returns 422 ERR_INVALID_PARAM with the valid values in the message.
$collection_id = 12,34; // string | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize.
$country_code = 'country_code_example'; // string | One ISO country code or a comma-separated list (e.g. US,GB,DE)
$language_code = 'language_code_example'; // string | One ISO language code or a comma-separated list (e.g. en,es,de)
$brand_kind = 'brand_kind_example'; // string | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default.
$range = 56; // int | Number of days to look back (alternative to from/to)
$from = new \DateTime('2013-10-20T19:20:30+01:00'); // \DateTime
$to = new \DateTime('2013-10-20T19:20:30+01:00'); // \DateTime | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier.
$output = 'output_example'; // string | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.

try {
    $apiInstance->listRedditCitations($project_id, $page, $per_page, $view, $subreddit, $author, $status, $owned, $brand, $order, $direction, $model, $collection_id, $country_code, $language_code, $brand_kind, $range, $from, $to, $output);
} catch (Exception $e) {
    echo 'Exception when calling OwnedMediaCommunitiesApi->listRedditCitations: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **project_id** | **int**| Project ID | |
| **page** | **int**|  | [optional] [default to 1] |
| **per_page** | **int**|  | [optional] [default to 20] |
| **view** | **string**|  | [optional] [default to &#39;subreddits&#39;] |
| **subreddit** | **string**| Filter to one subreddit (name without the r/ prefix) | [optional] |
| **author** | **string**| Filter to one Reddit author | [optional] |
| **status** | **string**| view&#x3D;threads only | [optional] |
| **owned** | **bool**| Return only subreddits/authors the account has claimed as its own | [optional] |
| **brand** | **string**| Filter to citations whose scraped Reddit content mentions a brand: &#39;brand&#39; for the tracked brand, or a competitor id. Reads the page content, not the AI answer. | [optional] |
| **order** | **string**| Sort field; the allowed set depends on view | [optional] |
| **direction** | **string**|  | [optional] [default to &#39;desc&#39;] |
| **model** | **string**| Filter by one AI model. It must be a model enabled for the API key&#39;s user: an unknown value, or a model the user has not enabled, returns 422 ERR_INVALID_PARAM with the valid values in the message. | [optional] |
| **collection_id** | **string**| One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize. | [optional] |
| **country_code** | **string**| One ISO country code or a comma-separated list (e.g. US,GB,DE) | [optional] |
| **language_code** | **string**| One ISO language code or a comma-separated list (e.g. en,es,de) | [optional] |
| **brand_kind** | **string**| Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. | [optional] |
| **range** | **int**| Number of days to look back (alternative to from/to) | [optional] |
| **from** | **\DateTime**|  | [optional] |
| **to** | **\DateTime**| End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. | [optional] |
| **output** | **string**| Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] |

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

## `updateOwnedMediaProfiles()`

```php
updateOwnedMediaProfiles($id, $update_owned_media_profiles_request): \LLMPulse\Model\OwnedMediaProfilesUpdateResponse
```

Update a project's owned-media profiles

Sets the profiles whose citations count as yours, like Project Settings > Owned Media. Send only the fields to change: a URL field takes a URL, or an empty string or null to clear it, and every list REPLACES the stored one ([] clears it). URLs are normalized like the app (a profile URL is stored in its canonical form, a Google Play package name becomes its listing URL), and anything the app would refuse (a URL from another platform, an extra profile equal to the main one, more than 10 extra profiles, a malformed subreddit) is rejected with ERR_INVALID_PARAM and nothing is applied. A new main or extra profile is scraped in the background for its name and avatar, listed in profile_scrapes_queued. The response is the GET payload after the change. A team member needs the Owned Media create permission, and YouTube Intelligence create to change the YouTube channel. Requires the Growth plan or above and a `read_write` scope API key.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: BearerAuth
$config = LLMPulse\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new LLMPulse\Api\OwnedMediaCommunitiesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 56; // int | Project ID
$update_owned_media_profiles_request = new \LLMPulse\Model\UpdateOwnedMediaProfilesRequest(); // \LLMPulse\Model\UpdateOwnedMediaProfilesRequest

try {
    $result = $apiInstance->updateOwnedMediaProfiles($id, $update_owned_media_profiles_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling OwnedMediaCommunitiesApi->updateOwnedMediaProfiles: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **int**| Project ID | |
| **update_owned_media_profiles_request** | [**\LLMPulse\Model\UpdateOwnedMediaProfilesRequest**](../Model/UpdateOwnedMediaProfilesRequest.md)|  | |

### Return type

[**\LLMPulse\Model\OwnedMediaProfilesUpdateResponse**](../Model/OwnedMediaProfilesUpdateResponse.md)

### Authorization

[BearerAuth](../../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
