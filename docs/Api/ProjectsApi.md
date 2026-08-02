# LLMPulse\ProjectsApi



All URIs are relative to https://api.llmpulse.ai/api/v1, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**createProject()**](ProjectsApi.md#createProject) | **POST** /projects | Create a project (fast mode) |
| [**createProjectDraft()**](ProjectsApi.md#createProjectDraft) | **POST** /project_drafts | Start a project draft (wizard step 1) |
| [**finalizeProjectDraft()**](ProjectsApi.md#finalizeProjectDraft) | **POST** /project_drafts/{id}/finalize | Finalize a draft into a real project |
| [**getProjectDraft()**](ProjectsApi.md#getProjectDraft) | **GET** /project_drafts/{id} | Read a project draft |
| [**updateProjectDraft()**](ProjectsApi.md#updateProjectDraft) | **PATCH** /project_drafts/{id} | Submit a wizard step |


## `createProject()`

```php
createProject($project_create_request): \LLMPulse\Model\ProjectCreateResponse
```

Create a project (fast mode)

Create a complete project in one call: project fields, prompts (queued for execution and categorization), competitors, weekly email subscription. Idempotent via `external_identifier` (embed-enabled accounts only; replay returns 200 with the existing project). Requires a `read_write` scope API key.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: BearerAuth
$config = LLMPulse\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new LLMPulse\Api\ProjectsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$project_create_request = new \LLMPulse\Model\ProjectCreateRequest(); // \LLMPulse\Model\ProjectCreateRequest

try {
    $result = $apiInstance->createProject($project_create_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ProjectsApi->createProject: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **project_create_request** | [**\LLMPulse\Model\ProjectCreateRequest**](../Model/ProjectCreateRequest.md)|  | |

### Return type

[**\LLMPulse\Model\ProjectCreateResponse**](../Model/ProjectCreateResponse.md)

### Authorization

[BearerAuth](../../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `createProjectDraft()`

```php
createProjectDraft($create_project_draft_request)
```

Start a project draft (wizard step 1)

Start the multi-step project-creation wizard. Returns a draft_id plus AI suggestions (name, description, industry, brand aliases) for the URL. Cold URLs can take up to ~2 minutes to analyze; pass suggest=false to skip AI and respond instantly. Drafts expire after 24h. Requires a `read_write` scope API key.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: BearerAuth
$config = LLMPulse\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new LLMPulse\Api\ProjectsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$create_project_draft_request = new \LLMPulse\Model\CreateProjectDraftRequest(); // \LLMPulse\Model\CreateProjectDraftRequest

try {
    $apiInstance->createProjectDraft($create_project_draft_request);
} catch (Exception $e) {
    echo 'Exception when calling ProjectsApi->createProjectDraft: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **create_project_draft_request** | [**\LLMPulse\Model\CreateProjectDraftRequest**](../Model/CreateProjectDraftRequest.md)|  | |

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

## `finalizeProjectDraft()`

```php
finalizeProjectDraft($id, $finalize_project_draft_request)
```

Finalize a draft into a real project

Creates the project with all accumulated draft data (same effects as POST /projects). Idempotent: finalizing an already-finalized draft returns 200 with the existing project. Optional overrides: weekly_email_subscribed, execute_prompts_immediately.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: BearerAuth
$config = LLMPulse\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new LLMPulse\Api\ProjectsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string
$finalize_project_draft_request = new \LLMPulse\Model\FinalizeProjectDraftRequest(); // \LLMPulse\Model\FinalizeProjectDraftRequest

try {
    $apiInstance->finalizeProjectDraft($id, $finalize_project_draft_request);
} catch (Exception $e) {
    echo 'Exception when calling ProjectsApi->finalizeProjectDraft: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**|  | |
| **finalize_project_draft_request** | [**\LLMPulse\Model\FinalizeProjectDraftRequest**](../Model/FinalizeProjectDraftRequest.md)|  | [optional] |

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

## `getProjectDraft()`

```php
getProjectDraft($id, $include_suggestions)
```

Read a project draft

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: BearerAuth
$config = LLMPulse\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new LLMPulse\Api\ProjectsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string | Draft id (draft_...)
$include_suggestions = false; // bool | Cache-only: returns suggestions for the current step if already generated, never triggers AI

try {
    $apiInstance->getProjectDraft($id, $include_suggestions);
} catch (Exception $e) {
    echo 'Exception when calling ProjectsApi->getProjectDraft: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**| Draft id (draft_...) | |
| **include_suggestions** | **bool**| Cache-only: returns suggestions for the current step if already generated, never triggers AI | [optional] [default to false] |

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

## `updateProjectDraft()`

```php
updateProjectDraft($id, $update_project_draft_request)
```

Submit a wizard step

Submit one step (details, prompts, competitors, owned_media). Strict forward gating: a step is only accepted when every previous step is complete (`ERR_DRAFT_STATE` otherwise); completed steps can be resubmitted. Responds with the updated draft plus AI suggestions for the next step.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: BearerAuth
$config = LLMPulse\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new LLMPulse\Api\ProjectsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string
$update_project_draft_request = new \LLMPulse\Model\UpdateProjectDraftRequest(); // \LLMPulse\Model\UpdateProjectDraftRequest

try {
    $apiInstance->updateProjectDraft($id, $update_project_draft_request);
} catch (Exception $e) {
    echo 'Exception when calling ProjectsApi->updateProjectDraft: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**|  | |
| **update_project_draft_request** | [**\LLMPulse\Model\UpdateProjectDraftRequest**](../Model/UpdateProjectDraftRequest.md)|  | |

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
