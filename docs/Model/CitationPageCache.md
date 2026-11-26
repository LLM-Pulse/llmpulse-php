# CitationPageCache

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**present** | **bool** | Whether the page has a saved copy |
**last_crawled_at** | **\DateTime** | When the saved copy was read; null without usable content |
**status_code** | **int** | A saved successful response or an observed 404/410; null otherwise |
**error_message** | **string** | Always null; crawl errors are not exposed |
**content_format** | **string** |  |
**bytes** | **int** |  |
**html_title** | **string** |  |
**meta_title** | **string** |  |
**meta_description** | **string** |  |
**h1** | **string** |  |
**canonical_url** | **string** |  |
**language** | **string** |  |
**mentions_processed** | **bool** | Whether the page&#39;s mention analysis has completed for this project |
**content_available** | **bool** |  |

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
