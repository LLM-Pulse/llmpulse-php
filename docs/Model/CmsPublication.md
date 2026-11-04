# CmsPublication

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **int** |  | [optional]
**platform** | **string** |  | [optional]
**site_url** | **string** |  | [optional]
**status** | **string** | queued and sending are on their way; unknown means a send timed out and the next attempt looks the draft up before creating one; drafted carries remote_id and edit_url; failed carries error_code | [optional]
**title** | **string** |  | [optional]
**slug** | **string** |  | [optional]
**source_url** | **string** | For an update task, the page the draft revises | [optional]
**remote_id** | **int** | WordPress post id of the draft | [optional]
**remote_status** | **string** | WordPress status of the post when the draft was created (draft) | [optional]
**remote_url** | **string** |  | [optional]
**edit_url** | **string** | The post&#39;s edit screen in the WordPress admin | [optional]
**error_code** | **string** | Why the send failed, for example reconnect_required, missing_capability, unreachable or rejected | [optional]
**created_at** | **\DateTime** |  | [optional]
**sent_at** | **\DateTime** |  | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
