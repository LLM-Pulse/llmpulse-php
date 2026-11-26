# QueryFanOutsResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**project_id** | **int** |  |
**page** | **int** |  |
**per_page** | **int** |  |
**total** | **int** | Rows matching the filters across every page |
**request_id** | **string** |  |
**view** | **string** | query or prompt, the row shape of data |
**total_occurrences** | **int** | Sub-query occurrences across every page (view&#x3D;query) | [optional]
**data** | [**\LLMPulse\Model\QueryFanOutRow[]**](QueryFanOutRow.md) |  |

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
