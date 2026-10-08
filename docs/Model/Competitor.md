# Competitor

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **int** |  | [optional]
**name** | **string** |  | [optional]
**domain** | **string** | Bare (scheme-less) domain. Null only on the own-brand row (include_project_brand&#x3D;true) when the project has no URL. | [optional]
**matching_names** | **string[]** | Alternative names matched as this competitor. Absent on the own-brand row | [optional]
**citation_match_mode** | [**\LLMPulse\Model\CitationMatchMode**](CitationMatchMode.md) |  | [optional]
**citation_match_path** | **string** | Set only when citation_match_mode is path_prefix | [optional]
**actor_type** | **string** | Only present when include_project_brand&#x3D;true | [optional]
**is_own** | **bool** | Only present when include_project_brand&#x3D;true | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
