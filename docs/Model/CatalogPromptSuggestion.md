# CatalogPromptSuggestion

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **int** |  |
**prompt** | **string** |  |
**status** | **string** | pending, accepted or rejected |
**source** | **string** | Always catalog |
**country_code** | **string** |  |
**language_code** | **string** |  |
**product** | [**\LLMPulse\Model\CatalogPromptSuggestionProduct**](CatalogPromptSuggestionProduct.md) |  |
**prompt_id** | **int** | The tracked prompt an accepted suggestion became; null until accepted |
**accepted_at** | **\DateTime** | When the suggestion was accepted; null until then |
**created_at** | **\DateTime** |  |

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
