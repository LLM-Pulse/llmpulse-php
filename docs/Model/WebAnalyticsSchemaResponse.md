# WebAnalyticsSchemaResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**project_id** | **int** |  | [optional]
**provider** | **string** | The connected web analytics provider. | [optional]
**property** | **string** | The property, site, report suite (rsid:...), data view (dataview:...) or project every query runs on. | [optional]
**query_language** | **string** | The native query format the provider accepts. | [optional]
**docs_url** | **string** | The provider&#39;s reference for that format. | [optional]
**allowed_fields** | **string[]** | Top-level query fields that are forwarded. | [optional]
**rules** | **string[]** | What the bridge enforces and the provider&#39;s main constraints. | [optional]
**example** | **array<string,mixed>** | A worked query to adapt. | [optional]
**fields** | **array<string,mixed>** | The provider&#39;s live field list where it offers one: GA4 dimensions and metrics with custom definitions, Adobe ids, Matomo report methods, PostHog event names, the Plausible catalog. Null when the provider did not return it. | [optional]
**fields_unavailable** | **string** | Present when the field list could not be read; the format and example still apply. | [optional]
**request_id** | **string** |  | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
