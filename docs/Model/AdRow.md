# AdRow

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**domain** | **string** | Advertising domain; null on a placement that names none (view&#x3D;ads) |
**ads** | **int** | Placements of the domain (view&#x3D;advertisers) | [optional]
**executions** | **int** | Answers that carried them (view&#x3D;advertisers) | [optional]
**prompts** | **int** | Distinct prompts that triggered them (view&#x3D;advertisers) | [optional]
**avg_position** | **float** | Average position, 1 is the best slot; null when no placement has one (view&#x3D;advertisers) | [optional]
**best_position** | **int** | Best position, 1 is the best slot (view&#x3D;advertisers) | [optional]
**id** | **int** | The placement (view&#x3D;ads) | [optional]
**model** | **string** |  | [optional]
**title** | **string** |  | [optional]
**snippet** | **string** |  | [optional]
**url** | **string** |  | [optional]
**position** | **int** | Position of the placement, 1 is the best slot (view&#x3D;ads) | [optional]
**is_client** | **bool** | Whether the placement is identified as your brand&#39;s own (view&#x3D;ads) | [optional]
**prompt_id** | **int** |  | [optional]
**prompt_text** | **string** |  | [optional]
**prompt_execution_id** | **int** |  | [optional]
**executed_at** | **\DateTime** | When the answer that carried the placement was collected (view&#x3D;ads) | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
