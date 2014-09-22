# Automation


## Get List of Insights

> API shell:

```shell
curl -H "MW-Token: <apikey>" -H "Content-Type: application/json" -X GET https://api.minewhat.com/v1/insights?domain=<domain_key>

Example:
curl -H "MW-Token: 123456ab78cd9e01" -H "Content-Type: application/json" -X GET https://api.minewhat.com/v1/insights?domain=sandbox_sandbox

Response:
{status: "ok", data: {insights: [{id: "52eb4b1b8b7a5800000002cd", name: "Products under Designer Collection that were viewed via search more often", metric: "searchviews", order: "topk"}, ...]}}
```

You can get all the insights you have created or system created with this API.

### Filters

Parameter | Description
--------- | -------------
domain    | domain key
metric    | views/purchases/revenue/avgtimespent/conversionrate(optional)
order     | topk/leastk(optional)


### Response

Response of an insight list call

{status: "ok", data: {insights: [{id: id, name: name, metric: metric, order: order}, ...]}}

Parameter   | Description
----------- | -------------
id          | The exact id of the Insight
name        | Name of the insight,
metric      | The metric of the insight
order       | topk/leastk

## Get Items of an Insight

> API shell:

```shell
curl -H "MW-Token: <apikey>" -H "Content-Type: application/json" -X GET http://api.minewhat.com/v1/insights/<insightid>?domain=<domain_key>

Example:
curl -H "MW-Token: 123456ab78cd9e01" -H "Content-Type: application/json" -X GET http://api.minewhat.com/v1/insights/52eb4b1b8b7a5800000002cd?domain=sandbox_sandbox

Response:
{status: "ok", data: {id: "52eb4b1b8b7a5800000002cd" , name: "Most Converting Products From Mobile" , metric: "conversionrate", order: "topk", itemtype: "products", date: {fromDate: "2014-08-14", toDate: "2014-08-20", dataValidFrom: "2014-08-01", dataValidTo: "2014-08-25", format: "YYYY-MM-DD"}, insight: {"all-items": [{id: "AX12", name: "Blue Jeans", price: "$99", brand: "dkny", brandid: 56, categories: ["men", "jeans"], categoryids: [2, 34], m1: 2045, m2: 26, m3: 2574, m4: "1.27%", m5: 25}, ...]}, metricnames: {m1name: "Views", m2name: "Purchases", m3name: "Revenue", m4name: "Conversion rate", m5name: "Avg. Time Spent"}}}
```

You can get all the items of the insights so that you can connect back to any automation systems like Email, Landing Page automation etc

### Parameters

Parameter | Description
--------- | -------------
id        | Unique identifier of the insight (obtained with insight list api)
domain    | domain key

### Response

Response of an insight call 

{status: "ok", data: {id: ins_id , name: ins_name , metric: metric, order: order, itemtype: itemtype, date: {fromDate: fromDate, toDate: toDate, dataValidFrom: dataValidFrom, dataValidTo: dataValidTo, format: "YYYY-MM-DD"}, insight: {"ins_group": [{id: product_id, name: product_name, price: price, brand: brand, brandid: brandid, categories: categories, categoryids: categoryids, m1: m1, m2: m2, m3: m3, m4: m4, m5: m5}, ...]}, metricnames: {m1name: m1name, m2name: m2name, m3name: m3name, m4name: m4name, m5name: m5name}}}

Parameter       | Description
--------------- | -------------
ins_id          | Unique identifier of the insight
ins_name        | Name of Insight
metric          | views/purchases/revenue/avgtimespent/conversionrate
order           | topk/leastk
itemtype        | products/brands/category
product_id      | Unique identifier of the insight.
product_name    | Name of the product
brand           | Brand name
brandid         | Brand ID
categories      | Category list
categoryids     | Category ID list
m1name...m5name | Metric names
m1...m5         | Metric values
date            | The date object for which above metric were achieved



