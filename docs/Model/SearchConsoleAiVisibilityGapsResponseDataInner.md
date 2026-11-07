# SearchConsoleAiVisibilityGapsResponseDataInner

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**query** | **string** |  | [optional]
**impressions** | **int** |  | [optional]
**clicks** | **int** |  | [optional]
**ctr** | **float** | 0..1 fraction | [optional]
**position** | **float** | Impression-weighted average position | [optional]
**prompt_id** | **int** | The project&#39;s prompt the query matches (see match_type); null when no prompt matches | [optional]
**responses** | **int** | AI answers the matching prompt got in the window over the account&#39;s enabled models; null when no prompt matches | [optional]
**brand_visibility** | **float** | Brand Visibility of the matching prompt in the window, percent (0-100) of its AI answers that mention the brand, over the account&#39;s enabled models; null when no prompt matches or it has no answer | [optional]
**match_type** | **string** | How the query matched: prompt (the same text as the prompt) or fan_out (the same text as a search the prompt&#39;s AI answers ran in the window); null when no prompt matches | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
