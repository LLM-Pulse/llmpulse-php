# OwnedMediaKpis

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**total** | **int** | Citations of the platform in the window, yours and everyone else&#39;s | [optional]
**yours** | **int** | Citations of your own profiles and their content | [optional]
**your_profile** | **int** | Citations of your profile or channel pages. Null for mobile_apps and overview | [optional]
**your_content** | **int** | Citations of your posts or videos. Null for mobile_apps and overview | [optional]
**share_pct** | **float** | yours as a percentage of total (0-100) | [optional]
**unique_subreddits** | **int** | Number of cited subreddits (provider&#x3D;reddit; null or omitted for other providers) | [optional]
**unique_authors** | **int** | Number of cited Reddit authors (provider&#x3D;reddit; null or omitted for other providers) | [optional]
**positive_pct** | **float** | Positive sentiment among rated Reddit citations, as a percentage (provider&#x3D;reddit; null or omitted for other providers) | [optional]
**connected_count** | **int** | provider&#x3D;overview only. The platforms with a connected profile, channel or app, out of the rows in platforms (the Connected sources card). It describes the current setup, so previous.kpis and changes leave it out | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
