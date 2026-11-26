# CitedUrlDetailsResponseStats

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**total_responses** | **int** | Answers citing the URL under the filters |
**total_citations** | **int** |  |
**citation_rate** | **float** | total_responses as a percentage (0-100) of citation_rate_denominator |
**citation_rate_denominator** | **int** | Answers matching the filters |
**avg_citation_position** | **float** | Null when no visible citation has a rank |
**first_seen_at** | **\DateTime** | Null when no citation matches the filters |
**last_seen_at** | **\DateTime** | Null when no citation matches the filters |
**distinct_urls** | **int** | Spellings of the URL cited (tracking parameters, a trailing slash) |
**source_types** | [**\LLMPulse\Model\CitedUrlDetailsResponseStatsSourceTypes**](CitedUrlDetailsResponseStatsSourceTypes.md) |  |
**models** | **array<string,int>** | Answers citing the URL per AI model, keyed by model |

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
