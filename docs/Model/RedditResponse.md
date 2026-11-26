# RedditResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**project_id** | **int** |  |
**page** | **int** |  |
**per_page** | **int** |  |
**total** | **int** | Rows matching the filters across every page |
**request_id** | **string** |  |
**view** | **string** | subreddits, authors, threads or breakdowns |
**from** | **\DateTime** | Start of the window, 30 days back by default |
**to** | **\DateTime** |  |
**citations** | **int** | Reddit citations after the filters (view&#x3D;breakdowns) | [optional]
**data** | [**\LLMPulse\Model\RedditRow[]**](RedditRow.md) |  |

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
