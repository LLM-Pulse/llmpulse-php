# ProjectDetails

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **int** |  | [optional]
**name** | **string** | Internal project label (sidebar, settings, admin) | [optional]
**brand_name** | **string** | LLM-facing brand label (used in prompts and customer-facing charts). Null when not set, in which case prompts and charts use &#x60;name&#x60;. | [optional]
**url** | **string** |  | [optional]
**description** | **string** |  | [optional]
**matching_names** | **string[]** |  | [optional]
**industry** | **mixed** | Industry as stored: one key as a string (e.g. SAAS), or an array of key strings when the project was created with a list or the in-app multi-select. Deliberately untyped so generated clients decode either shape | [optional]
**business_model** | **string** |  | [optional]
**business_model_other** | **string** | Set only when business_model is OTHER | [optional]
**primary_products** | **string[]** |  | [optional]
**target_audience** | **string** |  | [optional]
**brand_voice** | **string** |  | [optional]
**goals** | **string** |  | [optional]
**country_code** | **string** |  | [optional]
**language_code** | **string** |  | [optional]
**paused** | **bool** |  | [optional]
**google_play_id** | **string** |  | [optional]
**app_store_id** | **string** |  | [optional]
**created_at** | **\DateTime** |  | [optional]
**stats** | [**\LLMPulse\Model\ProjectDetailsAllOfStats**](ProjectDetailsAllOfStats.md) |  | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
