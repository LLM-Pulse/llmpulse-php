# OwnedMediaRow

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**title** | **string** |  | [optional]
**url** | **string** |  | [optional]
**channel_name** | **string** |  | [optional]
**channel_handle** | **string** | The video&#39;s channel handle, without the @ | [optional]
**channel_url** | **string** |  | [optional]
**video_id** | **string** |  | [optional]
**key** | **string** | The channel key (handle:..., channel:... or name:...), accepted as profile by /dimensions/owned_media/citing_prompts | [optional]
**name** | **string** |  | [optional]
**handle** | **string** |  | [optional]
**caption** | **string** |  | [optional]
**owner_handle** | **string** |  | [optional]
**thumbnail_url** | **string** | The post or video image. Our cached copy where one exists, so the link does not expire | [optional]
**avatar_url** | **string** | The profile or channel image. Our cached copy where one exists | [optional]
**content_type** | **string** | The post format on its platform: reel, post or tv on Instagram, post or pulse on LinkedIn, post elsewhere | [optional]
**citations** | **int** |  | [optional]
**unique_videos** | **int** |  | [optional]
**unique_posts** | **int** |  | [optional]
**followers** | **int** |  | [optional]
**likes** | **int** |  | [optional]
**comments** | **int** |  | [optional]
**views** | **mixed** | View count as the platform reports it, a number or a numeric string, or null when unknown | [optional]
**published_at** | **string** | Publication date as the platform reports it | [optional]
**posted_at** | **string** | Publication date as the platform reports it (ISO 8601, or Unix seconds on TikTok) | [optional]
**avg_position** | **float** | Average position of the citation in the answers (1 &#x3D; first); null when unknown | [optional]
**yours** | **bool** |  | [optional]
**citation_date** | **\DateTime** |  | [optional]
**position** | **int** |  | [optional]
**model** | **string** |  | [optional]
**domain** | **string** | The app&#39;s store listing URL (provider&#x3D;mobile_apps) | [optional]
**total_responses** | **int** |  | [optional]
**rank** | **int** |  | [optional]
**global_rank** | **int** |  | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
