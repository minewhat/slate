# Collection

## Track Product View Event

> SDK js:

```javascript
MWSDK.trackEvent('product', pid, associated_ids);

Example MWSDK.trackEvent('product', 'YZ1546', ['YZ1546A']);
```

> Script js:

```javascript
window._mwapi = window._mwapi || [];
_mwapi.push(['trackEvent', 'product', pid, associated_ids]);

Example _mwapi.push(['trackEvent', 'product', 'YZ1546', ['YZ1546A']]);
```

Send us product view details. It will help us provide you with better analysis.

### Parameters

Parameter | Description
--------- | -------------
type  | The type of event to track('product' in this case)
pid | Product ID. The unique identifier of the product you want us to track.
associated_ids  | The array of associated product ids

### Associated IDs

Array of associated products

Example: [pid1, pid2, ....]


## Track Add To Cart Event

> SDK js:

```javascript
MWSDK.trackEvent('addtocart', pid, sku, parent_pid, qty, bundle);

Example MWSDK.trackEvent('addtocart', 'YZ1546A', 'YZ1546ALRG', 'YZ1546', 2, [{pid: 'AB1546A', sku: 'AB1546ASML', price: 159}, {pid: 'D1546A', sku: 'D1546AML', price: 200}]);
```

> Script js:

```javascript
window._mwapi = window._mwapi || [];
_mwapi.push(['trackEvent', 'addtocart', pid, sku, parent_pid, qty, bundle]);

Example _mwapi.push(['trackEvent', 'addtocart', 'YZ1546A', 'YZ1546ALRG', 'YZ1546', 2, [{pid: 'AB1546A', sku: 'AB1546ASML', price: 159}, {pid: 'D1546A', sku: 'D1546AML', price: 200}]]);
```

Send us add to cart details. It will help us provide you with better analysis.

### Parameters

Parameter | Description
--------- | -------------
type  | The type of event to track('addtocart' in this case)
pid | Product ID. The unique identifier of the product of the product you want us to track.
parent_pid | Parent Product ID. The unique identifier of the parent product(incase of variant products) you want us to track.
sku | The sku of the item
qty | The quantity of items remaining in the stock
bundle  | The array of items in bundle

### Bundle

Array of individual products incase of bundle product

Example: [{pid: pid, sku: sku, price: price}, ....]

Parameter | Description
--------- | -------------
pid | Product ID. The unique identifier of the product of the product you want us to track.
sku | The sku of the item
price | The price of product


## Track Cart Info

> SDK js:

```javascript
MWSDK.trackEvent('bag', 'mwdirect', products);

Example MWSDK.trackEvent('bag', 'mwdirect', [{pid: 'YZ1546A', sku: 'YZ1546ALRG', qty: 2, price: 359, parent_pid: 'YZ1546', bundle: [{pid: 'YZ1546A', sku: 'YZ1546ALRG', price: 359}]}]);
```

> Script js:

```javascript
window._mwapi = window._mwapi || [];
_mwapi.push(['trackEvent', 'bag', 'mwdirect', products]);

Example _mwapi.push(['trackEvent', 'bag', 'mwdirect', [{pid: 'YZ1546A', sku: 'YZ1546ALRG', qty: 2, price: 359, parent_pid: 'YZ1546', bundle: [{pid: 'YZ1546A', sku: 'YZ1546ALRG', price: 359}]}]]);
```

Send us cart details. It will help us provide you with better analysis.

### Parameters

Parameter | Description
--------- | -------------
type  | The type of event to track('bag' in this case)
products | The products inside cart which you want us to track.

### Items

Array of products in the cart

Example: [{pid: pid, sku: sku, qty: qty, price: price, parent_pid: parent_pid, bundle: bundle}, ....]

Parameter | Description
--------- | -------------
pid | Product ID The unique identifier of the product of the product you want us to track.
sku | The sku of the item
qty | The quantity of items
price | The price of product
parent_pid | Parent Product ID. The unique identifier of the parent product(incase of variant products) you want us to track.
bundle  | The array of items in bundle


## Track Buy Event

> SDK js:

```javascript
MWSDK.trackEvent('buy', 'mwdirect', products);

Example MWSDK.trackEvent('buy', 'mwdirect', [{pid: 'YZ1546A', sku: 'YZ1546ALRG', qty: 2, price: 359, parent_pid: 'YZ1546', bundle: [{pid: 'YZ1546A', sku: 'YZ1546ALRG', price: 359}]}]);
```

> Script js:

```javascript
window._mwapi = window._mwapi || [];
_mwapi.push(['trackEvent', 'buy', 'mwdirect', products]);

Example _mwapi.push(['trackEvent', 'bag', 'mwdirect', [{pid: 'YZ1546A', sku: 'YZ1546ALRG', qty: 2, price: 359, parent_pid: 'YZ1546', bundle: [{pid: 'YZ1546A', sku: 'YZ1546ALRG', price: 359}]}]]);
```

Send us purchase details. It will help us provide you with better analysis.

### Parameters

Parameter | Description
--------- | -------------
type  | The type of event to track('buy' in this case)
products | The list of ordered products you want us to track.

### Items

Array of products bought

Example: [{pid: pid, sku: sku, qty: qty, price: price, parent_pid: parent_pid, bundle: bundle}, ....]

Parameter | Description
--------- | -------------
pid | Product ID. The unique identifier of the product of the product you want us to track.
sku | The sku of the item
qty | The quantity of items
price | The price of product
parent_pid | Parent Product ID. The unique identifier of the parent product(incase of variant products) you want us to track.
bundle  | The array of items in bundle

## Set Product Inventory


> SDK js:

```javascript
MWSDK.inventory(pid, sku , quantity);

Example MWSDK.inventory('RKG', 'RKG1' , 45);
```

> Script js:

```javascript
window._mwapi = window._mwapi || [];
_mwapi.push(['inventory', pid , sku , quantity ]);

Example _mwapi.push(['RKG', 'RKG1' , 45]);
```
> REST:

```shell
https://api.minewhat.com/v1/updateinv/?pid=pid&sku=sku&qty=qty

Example https://api.minewhat.com/v1/updateinv/?pid=RKG&sku=RKG1&qty=45
```

Send us inventory details for all the products. It will help us provide you with better analysis on what to keep on in your inventory so that you never run out of stock or pile it up.

### Parameters

Parameter | Description
--------- | -------------
pid | Product ID. The unique identifier of the product of the product you want us to track.
sku | The sku of the item
qty | The quantity of items remaining in the stock


## Set Customer Email

> SDK js:

```javascript
MWSDK.setuser(email_id);

Example MWSDK.setuser('abc@gmail.com');
```
> Script js:

```javascript
window._mwapi = window._mwapi || [];
_mwapi.push(['setUser', email_id]);

Example _mwapi.push(['setUser', 'abc@gmail.com']);
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

Example MWSDK.orderStatus('abc@gmail.com', 'fgrds354jd', 0);
```
> Script js:

```javascript
window._mwapi = window._mwapi || [];
_mwapi.push(['orderStatus', email_id, order_id, order_status ]);

Example _mwapi.push(['orderStatus', 'abc@gmail.com', 'fgrds354jd', 0]);
```

Users might be visiting your website to check the order status. We can guide while they are at it. Send us order status details when a user lands on your page.

### Parameters

Parameter | Description
--------- | -------------
email_id | Email Id of the signed in customer
order_id | Order Id of the signed in customer
order_status | Order Status of the Order Id, 0 - RECEIVED , 1 - SHIPPED , 2 - DELIVERED , 3 - RETURN , 4 - RETURN_ACCEPTED