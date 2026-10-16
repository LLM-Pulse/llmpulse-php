# ProjectUpdateResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**project** | [**\LLMPulse\Model\ProjectProfile**](ProjectProfile.md) |  |
**updated_fields** | **string[]** | The fields the request sent |
**rematching** | **bool** | True when a matching_names or additional_owned_domains change started a background recalculation of past answers; further edits are rejected until it finishes |
**note** | **string** | What the change does to mention detection, citation ownership, historical numbers and the prompts the project can hold |
**request_id** | **string** |  |

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
