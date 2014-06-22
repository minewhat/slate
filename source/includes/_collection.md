# Collection


## Track Product Quick View Event

> SDK js:

```javascript
MWSDK.trackEvent('quickview', {pid: pid, pLink: pLink, url: url});

Example MWSDK.trackEvent('quickview', {pid: 'YZ1546', pLink: 'www.yourstore.com/pid/12', url: 'www.yourstore.com/cat/14'});
```

> Script js:

```javascript
window._mwapi = window._mwapi || [];
_mwapi.push(['trackEvent', 'quickview', {pid: pid, pLink: pLink, url: url}]);

Example _mwapi.push(['trackEvent', 'quickview', {pid: 'YZ1546', pLink: 'www.yourstore.com/pid/12', url: 'www.yourstore.com/cat/14'}]);
```

Send us product quick view details. It will help us provide you with better analysis.

### Parameters

Parameter | Description
--------- | -------------
pid | Product ID. The unique identifier of the product you want us to track.
pLink  | The product link
url | URL of the current page


## Track Product View Event

> SDK js:

```javascript
MWSDK.trackEvent('product', {pid: pid, associated_ids: associated_ids, url: url});

Example MWSDK.trackEvent('product', {pid: 'YZ1546', associated_ids: ['YZ1546A'], url: 'www.yourstore.com/pid/14'});
```

> Script js:

```javascript
window._mwapi = window._mwapi || [];
_mwapi.push(['trackEvent', 'product', {pid: pid, associated_ids: associated_ids, url: url}]);

Example _mwapi.push(['trackEvent', 'product', {pid: 'YZ1546', associated_ids: ['YZ1546A'], url: 'www.yourstore.com/pid/14'}]);
```

Send us product view details. It will help us provide you with better analysis.

### Parameters

Parameter | Description
--------- | -------------
pid | Product ID. The unique identifier of the product you want us to track.
associated_ids  | The array of associated product ids
url | URL of the current page

### Associated IDs

Array of associated products

Example: [pid1, pid2, ....]


## Track Add To Cart Event

> SDK js:

```javascript
MWSDK.trackEvent('addtocart', {pid: pid, sku: sku, parent_pid: parent_pid, qty: qty, bundle: bundle, url: url});

Example MWSDK.trackEvent('addtocart', {pid: 'YZ1546A', sku: 'YZ1546ALRG', parent_pid: 'YZ1546', qty: 2, bundle: [{pid: 'AB1546A', sku: 'AB1546ASML', price: 159}, {pid: 'D1546A', sku: 'D1546AML', price: 200}], url: 'www.yourstore.com/pid/14'});
```

> Script js:

```javascript
window._mwapi = window._mwapi || [];
_mwapi.push(['trackEvent', 'addtocart', {pid: pid, sku: sku, parent_pid: parent_pid, qty: qty, bundle: bundle, url: url}]);

Example _mwapi.push(['trackEvent', 'addtocart', {pid: 'YZ1546A', sku: 'YZ1546ALRG', parent_pid: 'YZ1546', qty: 2, bundle: [{pid: 'AB1546A', sku: 'AB1546ASML', price: 159}, {pid: 'D1546A', sku: 'D1546AML', price: 200}], url: 'www.yourstore.com/pid/14'}]);
```

Send us add to cart details. It will help us provide you with better analysis.

### Parameters

Parameter | Description
--------- | -------------
pid | Product ID. The unique identifier of the product of the product you want us to track.
parent_pid | Parent Product ID. The unique identifier of the parent product(incase of variant products) you want us to track.
sku | The sku of the item
qty | The quantity of items remaining in the stock
bundle  | The array of items in bundle
url | URL of the current page

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
MWSDK.trackEvent('bag', {products: products, url: url});

Example MWSDK.trackEvent('bag', {products: [{pid: 'YZ1546A', sku: 'YZ1546ALRG', qty: 2, price: 359, parent_pid: 'YZ1546', bundle: [{pid: 'YZ1546A', sku: 'YZ1546ALRG', price: 359}]}], url: , url: 'www.yourstore.com/cart/dfg576'});
```

> Script js:

```javascript
window._mwapi = window._mwapi || [];
_mwapi.push(['trackEvent', 'bag', {products: products, url: url}]);

Example _mwapi.push(['trackEvent', 'bag', {products: [{pid: 'YZ1546A', sku: 'YZ1546ALRG', qty: 2, price: 359, parent_pid: 'YZ1546', bundle: [{pid: 'YZ1546A', sku: 'YZ1546ALRG', price: 359}]}], url: 'www.yourstore.com/cart/dfg576'}]);
```

Send us cart details. It will help us provide you with better analysis.

### Parameters

Parameter | Description
--------- | -------------
products | The products inside cart which you want us to track.
url | URL of the current page

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
MWSDK.trackEvent('buy', {products: products, coupons: coupons, url: url});

Example MWSDK.trackEvent('buy', {products: [{pid: 'YZ1546A', sku: 'YZ1546ALRG', qty: 2, price: 359, parent_pid: 'YZ1546', bundle: [{pid: 'YZ1546A', sku: 'YZ1546ALRG', price: 359}]}], coupons: [{code: "ABDFGERSA123", savings: 345}], url: 'www.yourstore.com/checkout/success'});
```

> Script js:

```javascript
window._mwapi = window._mwapi || [];
_mwapi.push(['trackEvent', 'buy', {products: products, coupons: coupons, url: url}]);

Example _mwapi.push(['trackEvent', 'buy', {products: [{pid: 'YZ1546A', sku: 'YZ1546ALRG', qty: 2, price: 359, parent_pid: 'YZ1546', bundle: [{pid: 'YZ1546A', sku: 'YZ1546ALRG', price: 359}]}], coupons: [{code: "ABDFGERSA123", savings: 345}], url: 'www.yourstore.com/checkout/success'}]);
```

Send us purchase details. It will help us provide you with better analysis.

### Parameters

Parameter | Description
--------- | -------------
products | The list of ordered products you want us to track.
coupons | The list of coupons applied in the order
url | URL of the current page

### Products

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

### Coupons
Parameter | Description
--------- | -------------
code | The coupon code applied in the order
savings | The savings on the coupon

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