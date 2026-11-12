# ProjectCreateRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**website_url** | **string** | Public HTTP(S) URL with a DNS hostname or public IP address. Credentials, private and special IP addresses, localhost and internal hostnames are rejected. |
**name** | **string** | Project name, as plain text. It can be changed later with PATCH /projects/{id} |
**main_country** | **string** |  |
**main_language** | **string** |  |
**brand_name** | **string** |  | [optional]
**description** | **string** |  | [optional]
**industry** | **string[]** | Industry keys, case-insensitive; a single key string is also accepted. An unknown key returns ERR_INVALID_PARAM listing the valid keys (the same list as the in-app industry picker, e.g. TECHNOLOGY, SAAS, ECOMMERCE) | [optional]
**business_model** | **string** | Business model key (e.g. B2B_SAAS, MARKETPLACE); unknown keys are rejected | [optional]
**business_model_other** | **string** | Free-text business model, only accepted when business_model is OTHER; rejected against any other key | [optional]
**target_audience** | **string** | Who the brand sells to. Context for Recommendations and GEO Writer (Brand Book) | [optional]
**brand_voice** | **string** | Tone of voice guidance for generated content (Brand Book) | [optional]
**goals** | **string** | What the brand wants to achieve. Context for GEO Writer and prompt suggestions | [optional]
**primary_products** | **string[]** | Main products or services | [optional]
**matching_names** | **string[]** | Brand-name variants used to detect mentions. At most 50 names of up to 100 characters each; a longer list or name is refused with ERR_INVALID_PARAM (422) and nothing is created | [optional]
**prompts** | **string[]** |  | [optional]
**collections** | [**\LLMPulse\Model\ProjectCreateRequestCollectionsInner[]**](ProjectCreateRequestCollectionsInner.md) | Collections (prompt tags) created with the project, each tagging prompts of this request by their exact text, so no separate tagging calls are needed. A text that is not in prompts returns ERR_INVALID_PARAM. A team member also needs Tags: Create permission. | [optional]
**competitors** | [**\LLMPulse\Model\ProjectCreateRequestCompetitorsInner[]**](ProjectCreateRequestCompetitorsInner.md) |  | [optional]
**owned_media** | [**\LLMPulse\Model\ProjectCreateRequestOwnedMedia**](ProjectCreateRequestOwnedMedia.md) |  | [optional]
**use_subdomain** | **bool** |  | [optional] [default to false]
**weekly_email_subscribed** | **bool** |  | [optional] [default to false]
**external_identifier** | **string** | Embed-enabled (Enterprise) accounts only; other accounts receive ERR_PLAN_REQUIRED. Idempotency key and embed-session join key, unique per account | [optional]
**execute_prompts_immediately** | **bool** |  | [optional] [default to true]
**pitch** | **bool** | Create a pitch project, a one-off snapshot for a prospect. It runs its prompts once across the account&#39;s AI models right away, takes no project slot and its prompts do not count against the prompt quota, and it is deleted 90 days later unless converted by sending pitch false to PATCH /projects/{id}. It uses one of the month&#39;s pitch projects (GET /account, limits.pitch_projects), needs an agency or platform account (GET /account, limits.pitch_projects.access) and a paid subscription on the Scale tier or higher, takes 1 to 100 prompts, and cannot use a domain the account already tracks or pitched in the last 90 days. execute_prompts_immediately must not be false | [optional] [default to false]
**project_type** | **string** | Only for accounts billed per project type under a pricing agreement; any other account gets ERR_INVALID_PARAM. The key of one of the account&#39;s project types, such as core or lean, which sets the most prompts the project can hold and the price it is billed at. Omitted, the project takes the account&#39;s default type. A type other than the default needs the account owner or a co-owner (ERR_INSUFFICIENT_PERMISSION). An unknown key answers ERR_INVALID_PARAM with the valid keys; a pitch project has no type | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
