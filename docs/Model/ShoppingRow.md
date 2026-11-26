# ShoppingRow

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**product_key** | **string** | Stable grouping key of the product: its external id, else title: and the lowercased title (view&#x3D;products) | [optional]
**title** | **string** |  | [optional]
**domain** | **string** |  | [optional]
**url** | **string** |  | [optional]
**merchants** | **string** | The merchants the product card names (view&#x3D;products) | [optional]
**merchant** | **string** | The merchant (view&#x3D;merchants) | [optional]
**products** | **int** | Distinct products the merchant sold (view&#x3D;merchants) | [optional]
**currency** | **string** | Currency code the prices are in; null when no price names one |
**currency_count** | **int** | Currencies the product was priced in; above 1 the row reports its highest-priced listing (view&#x3D;products) | [optional]
**min_price** | **float** |  |
**max_price** | **float** |  |
**avg_price** | **float** | Average price in currency (view&#x3D;merchants) | [optional]
**avg_rating** | **float** |  |
**rating_votes** | **int** | Most rating votes any listing of the product showed (view&#x3D;products) | [optional]
**appearances** | **int** |  |
**is_client** | **bool** | Whether the product is identified as your brand&#39;s own (view&#x3D;products) | [optional]
**best_rank** | **int** | Best rank the product got in a card list (view&#x3D;products) | [optional]
**models** | **string[]** | Models that showed the product (view&#x3D;products) | [optional]
**last_seen_at** | **\DateTime** | The latest answer that showed the product (view&#x3D;products) | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
