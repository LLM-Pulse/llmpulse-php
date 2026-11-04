# CmsContentItem

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **int** | WordPress post or page id | [optional]
**type** | **string** |  | [optional]
**status** | **string** | WordPress status (publish, future, draft, pending or private) | [optional]
**slug** | **string** |  | [optional]
**title** | **string** | Plain-text title as the site renders it | [optional]
**url** | **string** | The public link on the connected site; null when the site names a link on another host | [optional]
**modified_at** | **\DateTime** |  | [optional]
**excerpt** | **string** | Plain-text excerpt, up to 2,000 characters | [optional]
**content_html** | **string** | Sanitized HTML (headings, paragraphs, lists, tables, quotes, code, links with href only), up to 200,000 characters | [optional]
**content_truncated** | **bool** |  | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
