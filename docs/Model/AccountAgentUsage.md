# AccountAgentUsage

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**percent_used** | **int** | Whole percent used, rounded down, from 0 to 100; 100 means the allowance is spent and new questions wait until resets_on. null when unlimited is true | [optional]
**unlimited** | **bool** |  | [optional]
**included** | **bool** | Whether the plan includes the in-app AI assistant. false on a plan without it, where percent_used is 100 | [optional]
**period** | **string** | Always month | [optional]
**resets_on** | **\DateTime** | The first day of next month, when the allowance starts again | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
