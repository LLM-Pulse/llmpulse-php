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
**activity** | [**\LLMPulse\Model\OwnedMediaSummaryActivityPeriod[]**](OwnedMediaSummaryActivityPeriod.md) | All providers. One row per actual project reporting period with runs; provider&#x3D;overview has null yours and other, and provider&#x3D;reddit also returns positive, neutral and negative sentiment counts. Citation counts use the selected date window, and periods with runs but no citation have zero | [optional]
**subreddit_activity** | [**\LLMPulse\Model\RedditSubredditActivityPeriod[]**](RedditSubredditActivityPeriod.md) | provider&#x3D;reddit only. One row per subreddit and actual reporting period; the top five subreddits are separate and Others has a null subreddit | [optional]
**positions** | [**\LLMPulse\Model\RedditPositionShare[]**](RedditPositionShare.md) | provider&#x3D;reddit only. Position distribution over the selected date window | [optional]
**brand_share** | [**\LLMPulse\Model\RedditBrandShare[]**](RedditBrandShare.md) | provider&#x3D;reddit only. Citation share among the tracked brand and competitors with cited mentions | [optional]
**replies** | [**\LLMPulse\Model\TrustpilotReplies**](TrustpilotReplies.md) |  | [optional]
**request_id** | **string** |  | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
