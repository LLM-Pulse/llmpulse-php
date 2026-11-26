# LLMPulse\AnnotationsApi

Mark a date on the project timeline (a campaign launch, a site migration) so charts show what happened when.

All URIs are relative to https://api.llmpulse.ai/api/v1, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**createAnnotation()**](AnnotationsApi.md#createAnnotation) | **POST** /annotations | Create a timeline annotation |
| [**deleteAnnotation()**](AnnotationsApi.md#deleteAnnotation) | **DELETE** /annotations/{id} | Delete a timeline annotation |
| [**listAnnotations()**](AnnotationsApi.md#listAnnotations) | **GET** /annotations | List timeline annotations |
| [**updateAnnotation()**](AnnotationsApi.md#updateAnnotation) | **PATCH** /annotations/{id} | Update a timeline annotation |


## `createAnnotation()`

```php
createAnnotation($create_annotation_request): \LLMPulse\Model\AnnotationCreateResponse
```

Create a timeline annotation

Marks a date in the project timeseries with a title + description. Available on every plan. Requires a `read_write` scope API key.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: BearerAuth
$config = LLMPulse\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new LLMPulse\Api\AnnotationsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$create_annotation_request = new \LLMPulse\Model\CreateAnnotationRequest(); // \LLMPulse\Model\CreateAnnotationRequest

try {
    $result = $apiInstance->createAnnotation($create_annotation_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AnnotationsApi->createAnnotation: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **create_annotation_request** | [**\LLMPulse\Model\CreateAnnotationRequest**](../Model/CreateAnnotationRequest.md)|  | |

### Return type

[**\LLMPulse\Model\AnnotationCreateResponse**](../Model/AnnotationCreateResponse.md)

### Authorization

[BearerAuth](../../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `deleteAnnotation()`

```php
deleteAnnotation($project_id, $id): \LLMPulse\Model\AnnotationDeleteResponse
```

Delete a timeline annotation

Deletes an annotation. Same ownership rule as PATCH. Available on every plan and requires a `read_write` scope API key.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: BearerAuth
$config = LLMPulse\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new LLMPulse\Api\AnnotationsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$project_id = 56; // int | Project ID
$id = 56; // int

try {
    $result = $apiInstance->deleteAnnotation($project_id, $id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AnnotationsApi->deleteAnnotation: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **project_id** | **int**| Project ID | |
| **id** | **int**|  | |

### Return type

[**\LLMPulse\Model\AnnotationDeleteResponse**](../Model/AnnotationDeleteResponse.md)

### Authorization

[BearerAuth](../../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `listAnnotations()`

```php
listAnnotations($project_id, $from, $to, $annotation_category_id, $page, $per_page): \LLMPulse\Model\AnnotationsResponse
```

List timeline annotations

Lists project timeline annotations, newest first. Rows can come from manual notes, project automations, or platform events. The origin field distinguishes them; editable says whether the requesting user may modify the row. Available on every plan.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: BearerAuth
$config = LLMPulse\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new LLMPulse\Api\AnnotationsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$project_id = 56; // int | Project ID
$from = new \DateTime('2013-10-20T19:20:30+01:00'); // \DateTime
$to = new \DateTime('2013-10-20T19:20:30+01:00'); // \DateTime
$annotation_category_id = 56; // int | Keep the annotations filed under this category, one of the project's or a system category. Any other id returns 422 ERR_INVALID_PARAM.
$page = 1; // int
$per_page = 20; // int

try {
    $result = $apiInstance->listAnnotations($project_id, $from, $to, $annotation_category_id, $page, $per_page);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AnnotationsApi->listAnnotations: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **project_id** | **int**| Project ID | |
| **from** | **\DateTime**|  | [optional] |
| **to** | **\DateTime**|  | [optional] |
| **annotation_category_id** | **int**| Keep the annotations filed under this category, one of the project&#39;s or a system category. Any other id returns 422 ERR_INVALID_PARAM. | [optional] |
| **page** | **int**|  | [optional] [default to 1] |
| **per_page** | **int**|  | [optional] [default to 20] |

### Return type

[**\LLMPulse\Model\AnnotationsResponse**](../Model/AnnotationsResponse.md)

### Authorization

[BearerAuth](../../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `updateAnnotation()`

```php
updateAnnotation($id, $update_annotation_request): \LLMPulse\Model\AnnotationUpdateResponse
```

Update a timeline annotation

Updates title, description, annotation_date, color and/or annotation_category_id. Only user-created annotations belonging to the requesting user can be updated (system annotations never). Available on every plan and requires a `read_write` scope API key.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: BearerAuth
$config = LLMPulse\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new LLMPulse\Api\AnnotationsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 56; // int
$update_annotation_request = new \LLMPulse\Model\UpdateAnnotationRequest(); // \LLMPulse\Model\UpdateAnnotationRequest

try {
    $result = $apiInstance->updateAnnotation($id, $update_annotation_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AnnotationsApi->updateAnnotation: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **int**|  | |
| **update_annotation_request** | [**\LLMPulse\Model\UpdateAnnotationRequest**](../Model/UpdateAnnotationRequest.md)|  | |

### Return type

[**\LLMPulse\Model\AnnotationUpdateResponse**](../Model/AnnotationUpdateResponse.md)

### Authorization

[BearerAuth](../../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
