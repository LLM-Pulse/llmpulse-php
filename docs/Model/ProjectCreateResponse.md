# ProjectCreateResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**project** | **object** | Same shape as GET /dimensions/projects/{id} | [optional]
**prompts** | [**\LLMPulse\Model\ProjectCreateResponsePrompts**](ProjectCreateResponsePrompts.md) |  | [optional]
**competitors** | [**\LLMPulse\Model\ProjectCreateResponseCompetitors**](ProjectCreateResponseCompetitors.md) |  | [optional]
**collections** | [**\LLMPulse\Model\ProjectCreateResponseCollectionsInner[]**](ProjectCreateResponseCollectionsInner.md) | Collections created from the request&#39;s collections field (empty when none were sent; absent on an idempotent replay) | [optional]
**same_domain_projects** | [**\LLMPulse\Model\ProjectCreateResponseSameDomainProjectsInner[]**](ProjectCreateResponseSameDomainProjectsInner.md) | Projects the caller can already see on the same domain (absent on an idempotent replay). Informational only: the create is never blocked, since one domain tracked per market is a normal setup. | [optional]
**email_subscription** | [**\LLMPulse\Model\ProjectCreateResponseEmailSubscription**](ProjectCreateResponseEmailSubscription.md) |  | [optional]
**limits** | [**\LLMPulse\Model\ProjectCreateResponseLimits**](ProjectCreateResponseLimits.md) |  | [optional]
**idempotent** | **bool** | Present and true only on external_identifier replays | [optional]
**request_id** | **string** |  | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
