# ProjectCreateRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**website_url** | **string** | Public HTTP(S) URL with a DNS hostname or public IP address. Credentials, private and special IP addresses, localhost and internal hostnames are rejected. |
**name** | **string** |  |
**main_country** | **string** |  |
**main_language** | **string** |  |
**brand_name** | **string** |  | [optional]
**description** | **string** |  | [optional]
**industry** | **string[]** |  | [optional]
**business_model** | **string** | Business model key (e.g. B2B_SAAS, MARKETPLACE); unknown keys are rejected | [optional]
**business_model_other** | **string** | Free-text business model, only accepted when business_model is OTHER; rejected against any other key | [optional]
**target_audience** | **string** | Who the brand sells to. Context for Recommendations and GEO Writer (Brand Book) | [optional]
**brand_voice** | **string** | Tone of voice guidance for generated content (Brand Book) | [optional]
**goals** | **string** | What the brand wants to achieve. Context for GEO Writer and prompt suggestions | [optional]
**primary_products** | **string[]** | Main products or services | [optional]
**matching_names** | **string[]** |  | [optional]
**prompts** | **string[]** |  | [optional]
**competitors** | [**\LLMPulse\Model\ProjectCreateRequestCompetitorsInner[]**](ProjectCreateRequestCompetitorsInner.md) |  | [optional]
**owned_media** | [**\LLMPulse\Model\ProjectCreateRequestOwnedMedia**](ProjectCreateRequestOwnedMedia.md) |  | [optional]
**use_subdomain** | **bool** |  | [optional] [default to false]
**weekly_email_subscribed** | **bool** |  | [optional] [default to false]
**external_identifier** | **string** | Embed-enabled (Enterprise) accounts only; other accounts receive ERR_PLAN_REQUIRED. Idempotency key and embed-session join key, unique per account | [optional]
**execute_prompts_immediately** | **bool** |  | [optional] [default to true]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
