# OwnedMediaSummaryResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**project_id** | **int** |  | [optional]
**provider** | **string** |  | [optional]
**from** | **\DateTime** |  | [optional]
**to** | **\DateTime** |  | [optional]
**connected** | **bool** | Whether a profile is claimed on the platform (on overview, on any platform) | [optional]
**kpis** | [**\LLMPulse\Model\OwnedMediaKpis**](OwnedMediaKpis.md) |  | [optional]
**previous** | [**\LLMPulse\Model\OwnedMediaSummaryResponsePrevious**](OwnedMediaSummaryResponsePrevious.md) |  | [optional]
**changes** | [**\LLMPulse\Model\OwnedMediaKpiChanges**](OwnedMediaKpiChanges.md) |  | [optional]
**weekly** | [**\LLMPulse\Model\OwnedMediaWeek[]**](OwnedMediaWeek.md) |  | [optional]
**by_model** | [**\LLMPulse\Model\OwnedMediaModelShare[]**](OwnedMediaModelShare.md) | Null for provider&#x3D;overview | [optional]
**by_country** | [**\LLMPulse\Model\OwnedMediaCountryShare[]**](OwnedMediaCountryShare.md) | Null for provider&#x3D;overview | [optional]
**content_types** | [**\LLMPulse\Model\OwnedMediaContentTypeShare[]**](OwnedMediaContentTypeShare.md) | Social and YouTube providers only | [optional]
**age_buckets** | [**\LLMPulse\Model\OwnedMediaAgeBucketShare[]**](OwnedMediaAgeBucketShare.md) | Social and YouTube providers only. Posts or videos without a known publication date are left out | [optional]
**stores** | [**\LLMPulse\Model\OwnedMediaStoreTotals[]**](OwnedMediaStoreTotals.md) | provider&#x3D;mobile_apps only | [optional]
**platforms** | [**\LLMPulse\Model\OwnedMediaPlatformRollup[]**](OwnedMediaPlatformRollup.md) | provider&#x3D;overview only, one row per platform the caller can read | [optional]
**request_id** | **string** |  | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
