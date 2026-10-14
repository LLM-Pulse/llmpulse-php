# CreateWebhook201Response

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **int** |  | [optional]
**project_id** | **int** |  | [optional]
**event_type** | **string** |  | [optional]
**target_url** | **string** |  | [optional]
**disabled** | **bool** | True when the subscription receives no more events, including when the API key or OAuth connection that created it was revoked. Creating it again with the same project, event and URL replaces it with a new subscription and secret. | [optional]
**failure_count** | **int** |  | [optional]
**last_delivered_at** | **\DateTime** |  | [optional]
**created_at** | **\DateTime** |  | [optional]
**secret** | **string** | HMAC signing secret (whsec_...). Returned when the subscription is created, and on a re-post only to the API key or OAuth connection that created it; absent for any other credential. | [optional]
**request_id** | **string** |  | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
