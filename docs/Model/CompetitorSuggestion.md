# CompetitorSuggestion

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **string** | The suggestion key (brands) or the id of one citing source row (citations) |
**domain** | **string** |  |
**brand_name** | **string** | The proposed brand name; null for a cited domain | [optional]
**matching_names** | **string[]** | The names a tracked competitor would be matched by; empty for a cited domain |
**mentions** | **int** | Answers naming the brand, when the discovery counted them (brands only) | [optional]
**citations** | **int** | Answers citing the domain (citations only) | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
