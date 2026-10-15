# PromptGenerationRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**project_id** | **int** |  |
**source** | **string** | Which Add prompts generator to run |
**query** | **string** | keyword: optional keyword or research query. topic and reddit: required topic (reddit: the brand when search_type&#x3D;brand). paa: one keyword, as an alternative to keywords. | [optional]
**count** | **int** | keyword and topic: how many suggestions to ask for, capped by the prompt slots left | [optional] [default to 20]
**country_code** | **string** | ISO 3166-1 alpha-2 country of the suggestions (default the project country) | [optional]
**language_code** | **string** | ISO language code of the suggestions (default the project language) | [optional]
**competitor_id** | **int** | keyword: write the suggestions around this competitor of the project | [optional]
**search_type** | **string** | reddit: search discussions of a topic or a brand | [optional] [default to 'topic']
**keywords** | **string[]** | paa: up to 5 keywords; each is a People Also Ask lookup counted against the account&#39;s 24-hour allowance | [optional]
**source_country_code** | **string** | translate: country of the prompts to translate | [optional]
**source_language_code** | **string** | translate: language of the prompts to translate | [optional]
**min_words** | **int** | search_console: skip queries shorter than this many words | [optional] [default to 0]
**all_countries** | **bool** | search_console: include queries from every country instead of country_code only | [optional] [default to false]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
