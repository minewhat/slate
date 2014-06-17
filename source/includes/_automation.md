# Automation


## Get List of Insights

> API shell:

```shell
curl -u apikey:X -H "Content-Type: application/json" -X GET http://api.minewhat.com/v1/insights/getall

[{id: "4", name: "Products under Designer Collection that were viewed via search more often", metric: "searchviews", segmentName: "All Shoppers", segmentId: "2"}, ...]
```

You can get all the insights you have created or system created with this API.

### Parameters/Filters

Parameter | Description
--------- | -------------
type  | Type of Insight ( insight )
id | The exact id of the Insight
metric  | views/purchases/revenue/avgtimespent/conversionrate


### Response

Response of an insight list call

[{id: id, name: name, metric: metric, segmentName: segmentName, segmentId: segmentId}, ...]

Parameter | Description
--------- | -------------
id | The exact id of the Insight
name  | Name of the insight,
metric  | The metric of the insight
segmentName  | The segment name associated with the insight
segmentId  | The segment id associated with the insight

## Get Items of an Insight

> API shell:

```shell
curl -u apikey:X -H "Content-Type: application/json" -X GET http://api.minewhat.com/v1/insights/getdata

[{id: "12", name: "Most Converting Products From Mobile" , metric: "conversionrate", segmentName: "Shoppers from mobile", segmentId: "25"}, ...]
```

You can get all the items of the insights so that you can connect back to any automation systems like Email, Landing Page automation etc

### Parameters

Parameter | Description
--------- | -------------
id | The unique identifier of the insight (obtained with getall call)

### Response

Response of an insight call 

[{id: product_id, name: product_name, sku: sku, price: price, views: views, purchases: purchases, revenue: revenue, duration: {from: fromDate, to: toDate}}, ...]

Parameter | Description
--------- | -------------
product_id | The unique identifier of the product.
product_name | Name of the product
sku | The sku of the item
price | The price of product
views | Views of the product for the selected duration
purchases | Purchases of the product for the selected duration
revenue | Revenue from the product for the selected duration
duration | The duration for which above metric were achieved



