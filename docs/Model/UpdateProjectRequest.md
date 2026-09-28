# UpdateProjectRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**name** | **string** | Project name shown in the app. A label: it does not change mention detection unless brand_name is empty. Cannot be blank | [optional]
**brand_name** | **string** | Brand name used to detect mentions. Applies to future runs; it does not rewrite history | [optional]
**description** | **string** | What the brand does. Context for Recommendations and GEO Writer (Brand Book) | [optional]
**industry** | **string** | Single industry key (e.g. SAAS), stored as sent; an array of keys is also accepted and stored as an array, like the in-app multi-select. Unknown keys are rejected with the valid keys listed | [optional]
**business_model** | **string** | Business model key (e.g. B2B_SAAS); unknown keys are rejected | [optional]
**business_model_other** | **string** | Free-text business model, only accepted when business_model is OTHER; rejected against any other key | [optional]
**target_audience** | **string** | Who the brand sells to (Brand Book) | [optional]
**brand_voice** | **string** | Tone of voice guidance for generated content (Brand Book) | [optional]
**goals** | **string** | What the brand wants to achieve. Context for GEO Writer and prompt suggestions | [optional]
**primary_products** | **string[]** | Full replacement list of the main products or services | [optional]
**matching_names** | **string[]** | FULL replacement list of the brand-name variants used to detect mentions; send every variant to keep | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
