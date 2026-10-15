# PromptTagsRemoveResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**project_id** | **int** |  |
**prompts_targeted** | **int** | Prompts of the project among prompt_ids |
**tags_detached** | [**\LLMPulse\Model\TagRef[]**](TagRef.md) |  |
**links_removed** | **int** |  |
**skipped_not_linked** | **int** |  |
**missing_tag_names** | **string[]** | tag_names that matched no tag |
**ignored_prompt_ids** | **int[]** | prompt_ids that are not prompts of this project |
**request_id** | **string** |  |

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
