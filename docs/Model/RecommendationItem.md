# RecommendationItem

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **int** |  |
**recommendation_id** | **int** |  |
**recommendation_type** | **string** |  |
**category** | **string** |  |
**title** | **string** |  |
**description** | **string** |  | [optional]
**priority** | **string** |  |
**estimated_impact** | **string** |  | [optional]
**action_items** | **string[]** |  |
**source_refs** | **string[]** | Evidence codes (e.g. P1, C2) resolved in resolved_source_refs |
**status** | **string** |  |
**status_changed_at** | **\DateTime** |  | [optional]
**position** | **int** |  |
**metadata** | **array<string,mixed>** |  | [optional]
**created_at** | **\DateTime** |  |
**updated_at** | **\DateTime** |  |
**resolved_source_refs** | **array<string,mixed>[]** | The evidence each source_refs code points to (prompt, citation or own page) | [optional]
**unresolved_source_refs** | **string[]** | Present only when a code points to no stored evidence | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
