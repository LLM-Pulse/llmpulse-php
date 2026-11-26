# ProjectDraftRecord

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**draft_id** | **string** | Draft id (draft_...) |
**status** | **string** | open, finalized or expired |
**current_step** | **string** | The next step to submit (details, prompts, competitors, owned_media), or ready when the draft can be finalized |
**steps_completed** | **string[]** |  |
**steps_remaining** | **string[]** | Required steps not submitted yet |
**optional_steps** | **string[]** | Steps the plan allows but finalize does not require (owned_media from Growth) |
**finalizable** | **bool** |  |
**website_url** | **string** |  |
**main_country** | **string** |  |
**main_language** | **string** |  |
**use_subdomain** | **bool** |  |
**name** | **string** | Null until the details step |
**brand_name** | **string** |  |
**description** | **string** |  |
**industry** | **string[]** |  |
**matching_names** | **string[]** |  |
**prompts** | **string[]** |  |
**competitors** | [**\LLMPulse\Model\ProjectDraftRecordCompetitorsInner[]**](ProjectDraftRecordCompetitorsInner.md) |  |
**owned_media** | [**\LLMPulse\Model\ProjectDraftRecordOwnedMedia**](ProjectDraftRecordOwnedMedia.md) |  |
**weekly_email_subscribed** | **bool** |  |
**external_identifier** | **string** |  |
**execute_prompts_immediately** | **bool** |  |
**project_id** | **int** | The project the draft became; null until finalized |
**expires_at** | **\DateTime** |  |
**created_at** | **\DateTime** |  |

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
