# OwnedMediaProfile

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**url** | **string** |  | [optional]
**handle** | **string** | The handle, page id, store app id, subreddit or username | [optional]
**kind** | **string** |  | [optional]
**main** | **bool** | True for the main profile of its platform (or store), false for an extra one | [optional]
**store** | **string** | google_play or app_store for an app; null elsewhere | [optional]
**name** | **string** |  | [optional]
**avatar_url** | **string** |  | [optional]
**scrape_status** | **string** | State of the profile scrape that reads its name and avatar: pending, running, ready, failed or skipped; null when none has started or the platform has none | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
