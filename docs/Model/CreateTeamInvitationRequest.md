# CreateTeamInvitationRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**email** | **string** |  |
**project_ids** | **int[]** | Projects the member can access. Send this or all_projects true. | [optional]
**all_projects** | **bool** | Access to every project, including future ones | [optional]
**permission_role** | **string** | Default full_access. Owner and co-owners only. | [optional]
**account_role_id** | **int** | One of the account&#39;s roles, with permission_role account_role | [optional]
**permissions** | **array<string,string[]>** | With permission_role custom: feature key to the verbs granted (read, create, update, delete), for example {\&quot;overview\&quot;: [\&quot;read\&quot;], \&quot;prompts\&quot;: [\&quot;read\&quot;, \&quot;create\&quot;]} | [optional]
**account_admin** | **bool** | Make the member a co-owner. Account owner only. | [optional]
**billing_access** | **bool** | Access to Billing and Plans. Account owner only. | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
