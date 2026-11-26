# CitationGroupRow

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**source_id** | **int** | The group&#39;s first citation |
**view** | **string** | url, domain or host |
**key** | **string** | The URL as cited, the domain or the host |
**total_responses** | **int** | Answers citing it |
**total_citations** | **int** |  |
**citation_rate** | **float** | total_responses as a percentage (0-100) of citation_rate_denominator |
**citation_rate_denominator** | **int** | Answers matching the filters |
**avg_citation_position** | **float** | Null when no visible citation has a rank |
**first_seen_at** | **\DateTime** |  |
**last_seen_at** | **\DateTime** |  |
**models** | **array<string,int>** | Answers citing it per AI model, keyed by model |
**url** | **string** | url view only. The URL as cited | [optional]
**url_sha256** | **string** | url view only. Key of the cited page, shared by the URL&#39;s variants | [optional]
**normalized_url** | **string** | url view only | [optional]
**page_cache** | [**\LLMPulse\Model\CitationPageCache**](CitationPageCache.md) |  | [optional]
**page_mentions** | [**\LLMPulse\Model\CitationPageMentions**](CitationPageMentions.md) |  | [optional]
**domain** | **string** | domain view only | [optional]
**host** | **string** | host view only | [optional]
**aggregate_details** | [**\LLMPulse\Model\CitationGroupRowAggregateDetails**](CitationGroupRowAggregateDetails.md) |  | [optional]
**citation_series** | [**\LLMPulse\Model\CitationSeries**](CitationSeries.md) |  | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
