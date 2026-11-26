# AnalystScoreRow

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**brand** | **string** | Brand name; the subject name in a custom study |
**is_project** | **bool** | Whether it is the project&#39;s own brand; in a custom study, the focus subject |
**model** | **string** |  |
**report_date** | **\DateTime** |  |
**dimension** | **string** | Dimension key, as the dimension filter takes it |
**dimension_name** | **string** |  |
**attribute** | **string** | Attribute key within the dimension |
**attribute_name** | **string** |  |
**score** | **mixed** | The 0-100 score as the analyst model wrote it, normally a number, or null when it gave none. Deliberately untyped, as the model&#39;s output is stored without coercion |
**reasoning** | **string** | Why the model gave this score; null when it gave no reasoning |

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
