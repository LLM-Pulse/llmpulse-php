# CreateCompetitorRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**project_id** | **int** |  |
**brand_name** | **string** |  |
**domain** | **string** | URL is accepted and normalised to host (e.g. https://www.openai.com → openai.com) |
**matching_names** | **string[]** |  | [optional]
**citation_match_mode** | **string** | domain includes the registrable domain and all subdomains; host requires the exact hostname; path_prefix also requires citation_match_path | [optional] [default to 'domain']
**citation_match_path** | **string** | Required when citation_match_mode&#x3D;path_prefix, e.g. /es. Case-sensitive; trailing slash is optional; query and fragment are ignored | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
