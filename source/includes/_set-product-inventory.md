# Set Product Inventory


```javascript
MWSDK.inventory(product_id, sku , quantity);
```

```plaintext
window._mwapi = window._mwapi || [];
_mwapi.push(['inventory', product_id , sku , quantity ]);
```

```shell
https://engage.minewhat.com/api/updateinv/?c=customer_id&pid=product_id&sku=sku&qty=quantity
```

Send us inventory details for all the products. It will help us provide you with better analysis on what to keep on in your inventory so that you never run out of stock or pile it up.

### Parameters

Parameter | Description
--------- | -------------
customer_id | The unique identifier of the customer.Only used in REST calls, JS call internally use it.
product_id | The unique identifier of the product of the product you want us to track.
sku | The sku of the item
quantity | The quantity of items remaining in the stock