# TeamMember

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **int** |  |
**email** | **string** |  |
**name** | **string** |  | [optional]
**role** | **string** | The account owner is listed first; everyone else who joined is a member. |
**status** | **string** | A blocked member cannot sign in or use the API until unblocked in the app. |
**permission_role** | **string** | Access level of a member: full_access, view_only, custom or account_role. Null for the owner. |
**account_role** | [**\LLMPulse\Model\TeamAccountRole**](TeamAccountRole.md) |  |
**permissions** | **array<string,string[]>** | What the person can do, feature key to the verbs granted (read, create, update, delete), resolved from their role. Null for the account owner, who can do everything. |
**account_admin** | **bool** | A co-owner, who can manage the team. |
**billing_access** | **bool** | Can open Billing and Plans (always true for the owner). |
**all_projects** | **bool** | Has access to every project of the account, including future ones. |
**project_ids** | **int[]** | The projects a member is limited to; empty when all_projects is true. |
**last_sign_in_at** | **\DateTime** |  | [optional]
**joined_at** | **\DateTime** | When the member accepted the invitation; null for the owner and for members added without one. | [optional]
**created_at** | **\DateTime** |  | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
