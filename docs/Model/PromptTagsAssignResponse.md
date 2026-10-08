# PromptTagsAssignResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**project_id** | **int** |  |
**prompts_targeted** | **int** | Prompts of the project among prompt_ids |
**tags_attached** | [**\LLMPulse\Model\TagRef[]**](TagRef.md) |  |
**new_links_created** | **int** |  |
**skipped_already_linked** | **int** |  |
**missing_tag_names** | **string[]** | tag_names that matched no tag and were not created |
**ignored_prompt_ids** | **int[]** | prompt_ids that are not prompts of this project |
**request_id** | **string** |  |

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
