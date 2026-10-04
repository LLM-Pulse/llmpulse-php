# IntelligenceTaskCreateRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**project_id** | **int** |  |
**task_type** | **string** | product_listing is API-only: it needs product and returns ready-to-apply product page copy |
**prompt_id** | **int** | Not used by product_listing; send null or omit it | [optional]
**custom_topic** | **string** |  | [optional]
**user_instructions** | **string** |  | [optional]
**output_language_code** | **string** |  | [optional]
**existing_content** | **string** |  | [optional]
**existing_content_url** | **string** |  | [optional]
**product** | [**\LLMPulse\Model\IntelligenceTaskProduct**](IntelligenceTaskProduct.md) |  | [optional]
**prompt_ids** | **int[]** | product_listing only: up to 20 project prompts the copy should answer | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
