# CitationPageMentions

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**brand_mentioned** | **bool** |  |
**competitor_mentioned** | **bool** |  |
**brand_position** | **int** | Rank of the brand&#39;s first mention on the page; null when it has none |
**content_gap_status** | **string** | missing_page_cache, content_unavailable, mentions_not_processed, mentioned, gap (a competitor but not the brand) or not_mentioned |
**brands** | [**\LLMPulse\Model\CitationPageMentionsBrandsInner[]**](CitationPageMentionsBrandsInner.md) | Each brand the page mentions once, in order of first mention |
**mentions** | [**\LLMPulse\Model\CitationPageMentionsMentionsInner[]**](CitationPageMentionsMentionsInner.md) | Every mention on the page with its snippet; not sent on GET /citation_intelligence/groups | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
