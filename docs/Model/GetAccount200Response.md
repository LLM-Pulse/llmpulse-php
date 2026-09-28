# GetAccount200Response

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**plan** | **string** | Plan key (starter, growth, scale, ...) | [optional]
**plan_name** | **string** | Display name of the plan to show people (e.g. Scale++ for the scaleplusplus key) | [optional]
**tracking_frequency** | **string** | How often prompts run (weekly, daily, monthly, ...) | [optional]
**role** | **string** | Whether the key belongs to the account owner or a team member | [optional]
**subscription** | [**\LLMPulse\Model\GetAccount200ResponseSubscription**](GetAccount200ResponseSubscription.md) |  | [optional]
**limits** | [**\LLMPulse\Model\GetAccount200ResponseLimits**](GetAccount200ResponseLimits.md) |  | [optional]
**rate_limits** | [**\LLMPulse\Model\GetAccount200ResponseRateLimits**](GetAccount200ResponseRateLimits.md) |  | [optional]
**request_id** | **string** |  | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
