# AnnotationRecord

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **int** |  |
**title** | **string** |  |
**description** | **string** |  |
**annotation_date** | **\DateTime** |  |
**color** | **string** |  |
**category** | **string** | user (written by a person) or system (added by the platform) |
**origin** | **string** | manual, platform (a platform-wide event) or automation (a project change recorded automatically) |
**annotation_category** | [**\LLMPulse\Model\AnnotationRecordAnnotationCategory**](AnnotationRecordAnnotationCategory.md) |  |
**editable** | **bool** | Whether the requesting user may update or delete it |
**created_at** | **\DateTime** |  |

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
