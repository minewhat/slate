# Collection


## Track Product View Event

> SDK js:

```javascript
MWSDK.trackEvent('product', product_id, associated_ids);
```

> Script js:

```javascript
window._mwapi = window._mwapi || [];
_mwapi.push(['trackEvent', 'product', product_id, associated_ids]);
```

Send us product view details. It will help us provide you with better analysis.

### Parameters

Parameter | Description
--------- | -------------
type  | The type of event to track('product' in this case)
product_id | The unique identifier of the product you want us to track.
associated_ids  | The array of associated products

### Associated IDs

Array of associated products

Example: [{id: product_id, sku: sku, price: price}, ....]

Parameter | Description
--------- | -------------
product_id | The unique identifier of the product of the product you want us to track.
sku | The sku of the item
price | The price of product



## Track Add To Cart Event

> SDK js:

```javascript
MWSDK.trackEvent('addtocart', product_id, sku, parent_product_id, quantity, bundle);
```

> Script js:

```javascript
window._mwapi = window._mwapi || [];
_mwapi.push(['trackEvent', 'addtocart', product_id, sku, parent_product_id, quantity, bundle]);
```

Send us add to cart details. It will help us provide you with better analysis.

### Parameters

Parameter | Description
--------- | -------------
type  | The type of event to track('addtocart' in this case)
product_id | The unique identifier of the product of the product you want us to track.
parent_product_id | The unique identifier of the parent product(incase of variant products) you want us to track.
sku | The sku of the item
quantity | The quantity of items remaining in the stock
bundle  | The array of items in bundle

### Bundle

Array of individual products incase of bundle product

Example: [{id: product_id, sku: sku, price: price}, ....]

Parameter | Description
--------- | -------------
product_id | The unique identifier of the product of the product you want us to track.
sku | The sku of the item
price | The price of product


## Track Cart Info

> SDK js:

```javascript
MWSDK.trackEvent('bag', 'mwdirect', items);
```

> Script js:

```javascript
window._mwapi = window._mwapi || [];
_mwapi.push(['trackEvent', 'bag', 'mwdirect', items]);
```

Send us cart details. It will help us provide you with better analysis.

### Parameters

Parameter | Description
--------- | -------------
type  | The type of event to track('bag' in this case)
items | The products inside cart which you want us to track.

### Items

Array of products in the cart

Example: [{id: product_id, sku: sku, qty: quantity, price: price, ppid: parent_product_id, bundle: bundle}, ....]

Parameter | Description
--------- | -------------
product_id | The unique identifier of the product of the product you want us to track.
sku | The sku of the item
quantity | The quantity of items
price | The price of product
parent_product_id | The unique identifier of the parent product(incase of variant products) you want us to track.
bundle  | The array of items in bundle


## Track Buy Event

> SDK js:

```javascript
MWSDK.trackEvent('buy', 'mwdirect', items);
```

> Script js:

```javascript
window._mwapi = window._mwapi || [];
_mwapi.push(['trackEvent', 'buy', 'mwdirect', items]);
```

Send us purchase details. It will help us provide you with better analysis.

### Parameters

Parameter | Description
--------- | -------------
type  | The type of event to track('buy' in this case)
items | The list of ordered products you want us to track.

### Items

Array of products bought

Example: [{id: product_id, sku: sku, qty: quantity, price: price, ppid: parent_product_id, bundle: bundle}, ....]

Parameter | Description
--------- | -------------
product_id | The unique identifier of the product of the product you want us to track.
sku | The sku of the item
quantity | The quantity of items
price | The price of product
parent_product_id | The unique identifier of the parent product(incase of variant products) you want us to track.
bundle  | The array of items in bundle

## Set Product Inventory


> SDK js:

```javascript
MWSDK.inventory(product_id, sku , quantity);
```

> Script js:

```javascript
window._mwapi = window._mwapi || [];
_mwapi.push(['inventory', product_id , sku , quantity ]);
```
> REST:

```shell
https://api.minewhat.com/v1/updateinv/?pid=product_id&sku=sku&qty=quantity
```

Send us inventory details for all the products. It will help us provide you with better analysis on what to keep on in your inventory so that you never run out of stock or pile it up.

### Parameters

Parameter | Description
--------- | -------------
product_id | The unique identifier of the product of the product you want us to track.
sku | The sku of the item
quantity | The quantity of items remaining in the stock


## Set Customer Email

> SDK js:

```javascript
MWSDK.setuser(email_id);
```
> Script js:

```javascript
window._mwapi = window._mwapi || [];
_mwapi.push(['setUser', email_id]);
```

Users can clear cache and cookies from browser. Help us associate logged in users with their multiple session online by sending user email when he signs in.

### Parameters

Parameter | Description
--------- | -------------
email_id |  Email Id of the signed in customer


## Set Order Status

> SDK js:

```javascript
MWSDK.orderStatus(email_id, order_id, order_status);
```
> Script js:

```javascript
window._mwapi = window._mwapi || [];
_mwapi.push(['orderStatus',email_id, order_id, order_status ]);
```

Users might be visiting your website to check the order status. We can guide while they are at it. Send us order status details when a user lands on your page.

### Parameters

Parameter | Description
--------- | -------------
email_id | Email Id of the signed in customer
order_id | Order Id of the signed in customer
order_status | Order Status of the Order Id, 0 - RECEIVED , 1 - SHIPPED , 2 - DELIVERED , 3 - RETURN , 4 - RETURN_ACCEPTED