# AiModelPositionDistributionBrand

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**type** | **string** | project or competitor |
**id** | **int** | Project id, or competitor id |
**competitor_id** | **int** | Null for the project, the competitor id otherwise |
**name** | **string** |  |
**domain** | **string** | Bare (scheme-less) domain. Null for the project when it has no URL. |
**buckets** | [**\LLMPulse\Model\AiModelPositionDistributionBrandBucketsInner[]**](AiModelPositionDistributionBrandBucketsInner.md) | One per position bucket, in order: position_1, position_2_3, position_4_7 and position_8_plus |
**max_stacked_value** | **int** | The brand&#39;s largest mentions count of one period, its buckets added up |

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
