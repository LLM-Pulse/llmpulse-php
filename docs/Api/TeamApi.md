# LLMPulse\TeamApi

The account team: list members and pending invitations, invite someone by email with their projects and access, revoke an invitation or remove a member, with the same rules as the Team Members settings page. Not available to a key limited to some projects.

All URIs are relative to https://api.llmpulse.ai/api/v1, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**createTeamInvitation()**](TeamApi.md#createTeamInvitation) | **POST** /team_invitations | Invite a team member |
| [**listTeamInvitations()**](TeamApi.md#listTeamInvitations) | **GET** /team_invitations | List pending team invitations |
| [**listTeamMembers()**](TeamApi.md#listTeamMembers) | **GET** /team_members | List team members |
| [**removeTeamMember()**](TeamApi.md#removeTeamMember) | **DELETE** /team_members/{id} | Remove a team member |
| [**revokeTeamInvitation()**](TeamApi.md#revokeTeamInvitation) | **DELETE** /team_invitations/{id} | Revoke a pending team invitation |


## `createTeamInvitation()`

```php
createTeamInvitation($create_team_invitation_request): \LLMPulse\Model\CreateTeamInvitation201Response
```

Invite a team member

Invites someone to the account team with the same rules as the Team Members settings page, and sends them the invitation email (email_sent is false when the email provider refused it; the invitation still exists, so revoke it and invite again once the address is fixed). Send project_ids, or all_projects: true for every project (for a team member inviting, every project they can access). The account owner and co-owners choose the access with permission_role: full_access (default), view_only, custom (with permissions, feature key to verbs) or account_role (with account_role_id). A team member with permission to invite cannot choose access: leave those fields out and the invitation copies their own permissions. Only the account owner can set account_admin (co-owner) or billing_access. An address already registered on the platform, or with an invitation pending, is refused with ERR_INVALID_PARAM (revoke the pending one first). An account that cannot add more team members, or that reached its daily limit of invitations sent through the API and MCP (revoked ones count), answers ERR_LIMIT_REACHED; the message says which. Requires a `read_write` scope API key.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: BearerAuth
$config = LLMPulse\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new LLMPulse\Api\TeamApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$create_team_invitation_request = new \LLMPulse\Model\CreateTeamInvitationRequest(); // \LLMPulse\Model\CreateTeamInvitationRequest

try {
    $result = $apiInstance->createTeamInvitation($create_team_invitation_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling TeamApi->createTeamInvitation: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **create_team_invitation_request** | [**\LLMPulse\Model\CreateTeamInvitationRequest**](../Model/CreateTeamInvitationRequest.md)|  | |

### Return type

[**\LLMPulse\Model\CreateTeamInvitation201Response**](../Model/CreateTeamInvitation201Response.md)

### Authorization

[BearerAuth](../../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `listTeamInvitations()`

```php
listTeamInvitations($page, $per_page): \LLMPulse\Model\ListTeamInvitations200Response
```

List pending team invitations

Lists invitations that have not been accepted yet: the address, the access and projects the person will get, when the invitation was sent and when its link expires. An accepted invitation keeps its id and moves to GET /team_members. Same access rules as GET /team_members.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: BearerAuth
$config = LLMPulse\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new LLMPulse\Api\TeamApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$page = 56; // int
$per_page = 56; // int | Default 20, max 100

try {
    $result = $apiInstance->listTeamInvitations($page, $per_page);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling TeamApi->listTeamInvitations: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **page** | **int**|  | [optional] |
| **per_page** | **int**| Default 20, max 100 | [optional] |

### Return type

[**\LLMPulse\Model\ListTeamInvitations200Response**](../Model/ListTeamInvitations200Response.md)

### Authorization

[BearerAuth](../../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `listTeamMembers()`

```php
listTeamMembers($page, $per_page): \LLMPulse\Model\ListTeamMembers200Response
```

List team members

Lists the account owner first, then every team member who joined, with their access level (permission_role, account role and the resulting permissions), co-owner and billing flags, project access, status (active or blocked) and last sign-in. Pending invitations are listed by GET /team_invitations; GET /account limits.team_members.used counts both. Available to the account owner, co-owners and team members with the Team Members permission. A key limited to some projects answers ERR_KEY_PROJECT_SCOPED: the team belongs to the whole account.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: BearerAuth
$config = LLMPulse\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new LLMPulse\Api\TeamApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$page = 56; // int
$per_page = 56; // int | Default 20, max 100

try {
    $result = $apiInstance->listTeamMembers($page, $per_page);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling TeamApi->listTeamMembers: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **page** | **int**|  | [optional] |
| **per_page** | **int**| Default 20, max 100 | [optional] |

### Return type

[**\LLMPulse\Model\ListTeamMembers200Response**](../Model/ListTeamMembers200Response.md)

### Authorization

[BearerAuth](../../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `removeTeamMember()`

```php
removeTeamMember($id): \LLMPulse\Model\RemoveTeamMember200Response
```

Remove a team member

Removes a member from the team, as the settings page does: their sessions and API keys stop working at once and their user account is deleted in the background shortly after. Account owner or co-owner only; a co-owner cannot remove the owner, another co-owner or themselves. The owner cannot be removed. Pending invitations are revoked with DELETE /team_invitations/{id}; an id that is not a member of the account answers ERR_NOT_FOUND. Requires a `read_write` scope API key.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: BearerAuth
$config = LLMPulse\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new LLMPulse\Api\TeamApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 56; // int | The member id from GET /team_members

try {
    $result = $apiInstance->removeTeamMember($id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling TeamApi->removeTeamMember: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **int**| The member id from GET /team_members | |

### Return type

[**\LLMPulse\Model\RemoveTeamMember200Response**](../Model/RemoveTeamMember200Response.md)

### Authorization

[BearerAuth](../../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `revokeTeamInvitation()`

```php
revokeTeamInvitation($id): \LLMPulse\Model\RevokeTeamInvitation200Response
```

Revoke a pending team invitation

Revokes a pending invitation: its link stops working immediately. Account owner or co-owner only, and a co-owner cannot revoke an invitation that makes someone a co-owner. Members who already joined are removed with DELETE /team_members/{id}; an id that is not a pending invitation of the account answers ERR_NOT_FOUND. Requires a `read_write` scope API key.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: BearerAuth
$config = LLMPulse\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new LLMPulse\Api\TeamApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 56; // int | The invitation id from GET /team_invitations

try {
    $result = $apiInstance->revokeTeamInvitation($id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling TeamApi->revokeTeamInvitation: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **int**| The invitation id from GET /team_invitations | |

### Return type

[**\LLMPulse\Model\RevokeTeamInvitation200Response**](../Model/RevokeTeamInvitation200Response.md)

### Authorization

[BearerAuth](../../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
