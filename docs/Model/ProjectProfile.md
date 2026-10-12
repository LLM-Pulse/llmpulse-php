# ProjectProfile

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **int** |  |
**name** | **string** |  |
**brand_name** | **string** |  | [optional]
**description** | **string** |  | [optional]
**industry** | **mixed** | Industry as stored: one key as a string (e.g. SAAS), or an array of key strings. Deliberately untyped so generated clients decode either shape | [optional]
**business_model** | **string** |  | [optional]
**business_model_other** | **string** | Set only when business_model is OTHER | [optional]
**target_audience** | **string** |  | [optional]
**primary_products** | **string[]** |  | [optional]
**brand_voice** | **string** |  | [optional]
**goals** | **string** |  | [optional]
**matching_names** | **string[]** |  |
**additional_owned_domains** | **string[]** | Other domains the brand owns (at most 10, each a website&#39;s own domain covering its subdomains), whose citations count as owned like the project website. Empty when none |

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
