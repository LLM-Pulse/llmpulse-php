# SearchConsoleAiVisibilityGapsResponseDataInner

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**query** | **string** |  | [optional]
**impressions** | **int** |  | [optional]
**clicks** | **int** |  | [optional]
**ctr** | **float** | 0..1 fraction | [optional]
**position** | **float** | Impression-weighted average position | [optional]
**prompt_id** | **int** | The project&#39;s prompt with the same text as the query; null when no prompt matches | [optional]
**responses** | **int** | AI answers the matching prompt got in the window over the account&#39;s enabled models; null when no prompt matches | [optional]
**brand_visibility** | **float** | Brand Visibility of the matching prompt in the window, percent (0-100) of its AI answers that mention the brand, over the account&#39;s enabled models; null when no prompt matches or it has no answer | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
