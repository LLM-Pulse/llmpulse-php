# CompetitorDetails

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **int** |  | [optional]
**project_id** | **int** |  | [optional]
**brand_name** | **string** |  | [optional]
**domain** | **string** |  | [optional]
**matching_names** | **string[]** |  | [optional]
**google_play_id** | **string** |  | [optional]
**app_store_id** | **string** |  | [optional]
**citation_match_mode** | [**\LLMPulse\Model\CitationMatchMode**](CitationMatchMode.md) |  | [optional]
**citation_match_path** | **string** | Set only when citation_match_mode is path_prefix | [optional]
**google_play_name** | **string** | English app name on Google Play, when the competitor has an Android app | [optional]
**app_store_name** | **string** | English app name on the App Store, when the competitor has an iOS app | [optional]
**google_play_icon_url** | **string** |  | [optional]
**app_store_icon_url** | **string** |  | [optional]
**color** | **string** |  | [optional]
**processing** | **bool** | True while the competitor&#39;s historical mentions are being recalculated | [optional]
**created_at** | **\DateTime** |  | [optional]
**request_id** | **string** |  | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
