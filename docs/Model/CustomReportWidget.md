# CustomReportWidget

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**key** | **string** |  |
**label** | **string** |  |
**kind** | **string** |  |
**width** | **string** |  |
**available** | **bool** | false when the widget&#39;s data source (web analytics, agent analytics, owned media) is not connected |
**data** | **array<string,mixed>** | Shaped by kind. timeseries: series [{ name, color, points [{ date, value }] }]. donut: slices [{ name, value, color }]. bar: bars [{ label, value, color }]. kpi_grid: values and changes (null unless the report compares with the previous period). table: rows, one object per row. Null when the widget is not available. | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
