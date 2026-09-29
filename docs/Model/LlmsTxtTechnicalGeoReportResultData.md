# LlmsTxtTechnicalGeoReportResultData

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**llms_txt_content** | **string** | Current llms.txt, manual edits included | [optional]
**llms_full_txt_content** | **string** | Current llms-full.txt, manual edits included | [optional]
**manually_edited_at** | **\DateTime** | When the files were last edited by hand in the app, the API or MCP; null while they are as generated | [optional]
**content_version** | **string** | Send it back as content_version when editing the files. It changes on every save | [optional]
**original_llms_txt_content** | **string** | The generated llms.txt, kept from the first manual edit; null while the files are as generated | [optional]
**original_llms_full_txt_content** | **string** | The generated llms-full.txt, kept from the first manual edit; null while the files are as generated | [optional]
**crawl_data** | **object** |  | [optional]
**metadata** | **object** | Generation details, including output_language_code, the language the files were written in | [optional]
**pages_crawled** | **int** |  | [optional]
**generation_time_ms** | **int** |  | [optional]
**openai_tokens_used** | **int** |  | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
