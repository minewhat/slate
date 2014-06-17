# Automation


## Get List of Insights

> API shell:

```shell
curl -u apikey:X -H "Content-Type: application/json" -X GET http://api.minewhat.com/v1/insights/getall
```

You can get all the insights you have created or sytem created with this API.

### Parameters/Filters

Parameter | Description
--------- | -------------
type  | Type of Insight ( insight )
id | The exact id of the Insight

### type

String type of Insight

Example: ""

## Get Items of an Insight

> API shell:

```shell
curl -u apikey:X -H "Content-Type: application/json" -X GET http://api.minewhat.com/v1/insights/getdata
```

You can get all the items of the insights so that you can connect back to any automation systems like Email, Landing Page automation etc

### Parameters

Parameter | Description
--------- | -------------
id | The unique identifier of the insight ( obtained with getall call )

### Response

Response of an insight call 

Example: [{id: product_id, sku: sku, price: price}, ....]

Parameter | Description
--------- | -------------
product_id | The unique identifier of the product of the product you want us to track.
sku | The sku of the item
price | The price of product



