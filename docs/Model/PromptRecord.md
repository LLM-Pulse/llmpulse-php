# PromptRecord

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **int** |  |
**prompt_text** | **string** |  |
**collection_id** | **int** | Primary tag, when the prompt has one |
**collection_ids** | **int[]** | Every tag the prompt belongs to |
**tags** | [**\LLMPulse\Model\TagRef[]**](TagRef.md) |  |
**country_code** | **string** |  |
**language_code** | **string** |  |
**prompt_type** | **string** | Search intent: informational, navigational, commercial or transactional. Null until the prompt is classified |
**brand_kind** | **string** | Brand focus: brand, brand_other or non_brand. Null until the prompt is classified |
**last_executed_at** | **\DateTime** | Null until the prompt has run |
**tracked** | **bool** | Whether scheduled runs include this prompt. False when its project is paused or beyond the plan&#39;s project limit, or when the prompt is beyond the plan&#39;s prompt limit (the oldest prompts up to the limit run) |
**untracked_reason** | **string** | Why tracked is false: paused, project_limit or prompt_limit. Null when tracked |
**app_url** | **string** | Opens this prompt in the app. The link names its project, so it opens there for any user with access to that project |

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
