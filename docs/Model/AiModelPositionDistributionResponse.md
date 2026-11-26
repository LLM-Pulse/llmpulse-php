# AiModelPositionDistributionResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**project_id** | **int** |  |
**from** | **\DateTime** |  |
**to** | **\DateTime** |  |
**filters** | [**\LLMPulse\Model\AiModelInsightsReportFiltersEcho**](AiModelInsightsReportFiltersEcho.md) |  |
**granularity** | **string** |  |
**brands** | [**\LLMPulse\Model\AiModelPositionDistributionBrand[]**](AiModelPositionDistributionBrand.md) | The first brand (brand1, else the project) and the second (brand2, else the competitor with the most mentions, else the project), each left out when it has no mention in the window |
**max_stacked_value** | **int** | The largest mentions count of one period across the brands, for a shared chart axis |
**request_id** | **string** |  |

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
