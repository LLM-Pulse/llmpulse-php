# SourceRecord

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **int** |  |
**prompt_execution_id** | **int** |  |
**domain** | **string** | Registrable domain of the cited URL |
**url** | **string** | Normalized cited URL (tracking parameters and fragment removed) |
**url_sha256** | **string** | Key of the cited page, as GET /citation_intelligence/urls/{url_sha256} takes it |
**position** | **int** | Rank of the citation in the answer; 0 for a background source reference with no visible rank |
**source_type** | **string** | owned (the project&#39;s domains), competitor or third_party |
**is_google_play_link** | **bool** |  |
**is_app_store_link** | **bool** |  |
**created_at** | **\DateTime** |  |

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
