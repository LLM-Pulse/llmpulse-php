# QueryFanOutRow

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**query_text** | **string** | The sub-query a model issued (view&#x3D;query) | [optional]
**count** | **int** | Times it was issued (view&#x3D;query) | [optional]
**share** | **float** | Share of all sub-query occurrences, on a 0-100 scale (view&#x3D;query) | [optional]
**prompt_id** | **int** | view&#x3D;prompt | [optional]
**prompt_text** | **string** | view&#x3D;prompt | [optional]
**variations_count** | **int** | Distinct sub-queries issued for the prompt (view&#x3D;prompt) | [optional]
**total_count** | **int** | Sub-queries issued for the prompt, repeats included (view&#x3D;prompt) | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
