# CreateTeamInvitation201Response

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **int** | Kept by the member once they accept, when they move to GET /team_members. |
**email** | **string** |  |
**permission_role** | **string** |  |
**account_role** | [**\LLMPulse\Model\TeamAccountRole**](TeamAccountRole.md) |  |
**permissions** | **array<string,string[]>** | What the person can do, feature key to the verbs granted (read, create, update, delete), resolved from their role. Null for the account owner, who can do everything. |
**account_admin** | **bool** |  |
**billing_access** | **bool** |  |
**all_projects** | **bool** |  |
**project_ids** | **int[]** |  |
**invited_at** | **\DateTime** | When the invitation email was last sent. | [optional]
**expires_at** | **\DateTime** | When the invitation link stops working. | [optional]
**created_at** | **\DateTime** |  | [optional]
**email_sent** | **bool** | False when the email provider refused the invitation email |
**request_id** | **string** |  | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
