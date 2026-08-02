# ProjectCreateResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**project** | **object** | Same shape as GET /dimensions/projects/{id} | [optional]
**prompts** | [**\LLMPulse\Model\ProjectCreateResponsePrompts**](ProjectCreateResponsePrompts.md) |  | [optional]
**competitors** | [**\LLMPulse\Model\ProjectCreateResponseCompetitors**](ProjectCreateResponseCompetitors.md) |  | [optional]
**email_subscription** | [**\LLMPulse\Model\ProjectCreateResponseEmailSubscription**](ProjectCreateResponseEmailSubscription.md) |  | [optional]
**limits** | [**\LLMPulse\Model\ProjectCreateResponseLimits**](ProjectCreateResponseLimits.md) |  | [optional]
**idempotent** | **bool** | Present and true only on external_identifier replays | [optional]
**request_id** | **string** |  | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
