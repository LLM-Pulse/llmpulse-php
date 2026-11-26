# AllCitationRecord

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **int** | The citation&#39;s id, unique within its actor_type |
**actor_type** | **string** | project (your brand) or competitor |
**competitor_id** | **int** | Competitor rows only | [optional]
**name** | **string** | The project&#39;s brand name (its name when no brand name is set), or the competitor&#39;s brand name |
**domain** | **string** | On project rows the host of the cited URL without www. (null when it has no parsable host); on competitor rows the competitor&#39;s bare domain |
**prompt_id** | **int** |  |
**prompt_execution_id** | **int** |  |
**url** | **string** | Normalized cited URL (tracking parameters and fragment removed) |
**position** | **int** | Rank of the citation in the answer; 0 for a background source reference with no visible rank |
**created_at** | **\DateTime** |  |

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
