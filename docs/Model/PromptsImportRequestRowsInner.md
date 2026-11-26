# PromptsImportRequestRowsInner

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**prompt** | **string** | The prompt text, up to 2,000 bytes of UTF-8 text (about 2,000 characters in English, fewer with accented letters or non-Latin scripts). A longer new prompt skips the row, which comes back in row_errors; a row matching a prompt the project already tracks counts as a duplicate |
**country_code** | **string** | ISO 3166-1 alpha-2 code or country name (default the project country) | [optional]
**language_code** | **string** | ISO language code or language name (default the project language) | [optional]
**tags** | **string[]** | Tag names for this prompt, created when missing | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
