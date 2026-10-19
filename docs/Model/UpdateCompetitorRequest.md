# UpdateCompetitorRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**project_id** | **int** |  |
**brand_name** | **string** |  | [optional]
**domain** | **string** | Website domain or host used for citation matching. A full URL is accepted and normalised to its host. | [optional]
**matching_names** | **string[]** | FULL replacement list of the names this competitor is matched by; brand_name is added automatically. At most 50 names in all, brand_name included, of up to 100 characters each; a longer list or name is refused with ERR_INVALID_PARAM (422) and nothing in the request is applied | [optional]
**color** | **string** | Hex color, e.g. #1a2b3c | [optional]
**citation_match_mode** | **string** |  | [optional]
**citation_match_path** | **string** | Required when changing citation_match_mode to path_prefix | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
