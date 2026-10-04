# StoreConnectionResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**platform** | **string** | The store platform, e.g. shopify |
**domain** | **string** | The store domain as compared: lowercase, without scheme, www or path |
**project** | [**\LLMPulse\Model\StoreConnectionResponseProject**](StoreConnectionResponseProject.md) |  |
**ambiguous** | **bool** | True when several live projects match the store domain (for example one project per market). project is then null and the app asks the key holder to pick from candidates. |
**candidates** | [**\LLMPulse\Model\StoreConnectionResponseCandidatesInner[]**](StoreConnectionResponseCandidatesInner.md) | Every live project of the account, for a project picker |
**account** | [**\LLMPulse\Model\StoreConnectionResponseAccount**](StoreConnectionResponseAccount.md) |  |
**request_id** | **string** |  |

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
