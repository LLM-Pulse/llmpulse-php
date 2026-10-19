# UpdateProjectDraftRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**step** | **string** |  |
**name** | **string** |  | [optional]
**brand_name** | **string** |  | [optional]
**description** | **string** |  | [optional]
**industry** | **string[]** |  | [optional]
**matching_names** | **string[]** | Brand-name variants used to detect mentions (details step). At most 50 names of up to 100 characters each; the step stores the list as sent, and finalize refuses a longer list or name with ERR_INVALID_PARAM (422) | [optional]
**external_identifier** | **string** |  | [optional]
**prompts** | **string[]** |  | [optional]
**competitors** | **object[]** | Competitors step: objects {domain, brand_name, matching_names}, capped by plan. Each competitor&#39;s matching_names takes at most 50 names of up to 100 characters, checked at finalize like POST /projects | [optional]
**youtube_channel_url** | **string** |  | [optional]
**instagram_profile_url** | **string** |  | [optional]
**facebook_page_url** | **string** |  | [optional]
**tiktok_profile_url** | **string** |  | [optional]
**app_store_url** | **string** |  | [optional]
**google_play_url** | **string** |  | [optional]
**suggest** | **bool** |  | [optional] [default to true]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
