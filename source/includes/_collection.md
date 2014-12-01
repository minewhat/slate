# Collection

## Set Customer Email

> SDK js:

```javascript
MWSDK.trackUser(email_id, data);

Example MWSDK.trackUser('abc@gmail.com', {tags: ['premiumuser', 'above60']});
```
> Script js:

```javascript
window._mwapi = window._mwapi || [];
_mwapi.push(['trackUser', email_id, data]);

Example _mwapi.push(['trackUser', 'abc@gmail.com', {tags: ['premiumuser', 'above60']}]);
```

Users can clear cache and cookies from browser. Help us associate logged in users with their multiple session online by sending user email when he signs in.

### Parameters

Parameter | Description
--------- | -------------
email_id |  Email Id of the signed in customer
tags  | Array of user tags you want us to track


## Track Product View Event

> SDK js:

```javascript
MWSDK.trackEvent('product', {pid: pid, associated_ids: associated_ids});

Example MWSDK.trackEvent('product', {pid: 'YZ1546', associated_ids: ['YZ1546A']});
```

> Script js:

```javascript
window._mwapi = window._mwapi || [];
_mwapi.push(['trackEvent', 'product', {pid: pid, associated_ids: associated_ids}]);

Example _mwapi.push(['trackEvent', 'product', {pid: 'YZ1546', associated_ids: ['YZ1546A']}]);
```

Send us product view details. It will help us provide you with better analysis.

### Parameters

Parameter | Description
--------- | -------------
pid | Product ID. The unique identifier of the product you want us to track
associated_ids  | The array of associated product ids

### Associated IDs

Array of associated products

Example: [pid1, pid2, ....]


## Track Add To Cart Event

> SDK js:

```javascript
MWSDK.trackEvent('addtocart', {pid: pid, sku: sku, parent_pid: parent_pid, qty: qty, bundle: bundle});

Example MWSDK.trackEvent('addtocart', {pid: 'YZ1546A', sku: 'YZ1546ALRG', parent_pid: 'YZ1546', qty: 2, bundle: [{pid: 'AB1546A', sku: 'AB1546ASML', price: 159}, {pid: 'D1546A', sku: 'D1546AML', price: 200}]});
```

> Script js:

```javascript
window._mwapi = window._mwapi || [];
_mwapi.push(['trackEvent', 'addtocart', {pid: pid, sku: sku, parent_pid: parent_pid, qty: qty, bundle: bundle}]);

Example _mwapi.push(['trackEvent', 'addtocart', {pid: 'YZ1546A', sku: 'YZ1546ALRG', parent_pid: 'YZ1546', qty: 2, bundle: [{pid: 'AB1546A', sku: 'AB1546ASML', price: 159}, {pid: 'D1546A', sku: 'D1546AML', price: 200}]}]);
```

Send us add to cart details. It will help us provide you with better analysis.

### Parameters

Parameter | Description
--------- | -------------
pid | Product ID. The unique identifier of the product of the product you want us to track
parent_pid | Parent Product ID. The unique identifier of the parent product(incase of variant products) you want us to track
sku | The sku of the item
qty | The quantity of items remaining in the stock
bundle  | The array of items in bundle

### Bundle

Array of individual products incase of bundle product

Example: [{pid: pid, sku: sku, price: price}, .....]

Parameter | Description
--------- | -------------
pid | Product ID. The unique identifier of the product of the product you want us to track
sku | The sku of the item
price | The price of product


## Track Remove From Cart Event

> SDK js:

```javascript
MWSDK.trackEvent('removecart', {pid: pid, sku: sku, parent_pid: parent_pid, qty: qty, bundle: bundle});

Example MWSDK.trackEvent('removecart', {pid: 'YZ1546A', sku: 'YZ1546ALRG', parent_pid: 'YZ1546', qty: 2, bundle: [{pid: 'AB1546A', sku: 'AB1546ASML', price: 159}, {pid: 'D1546A', sku: 'D1546AML', price: 200}]});
```

> Script js:

```javascript
window._mwapi = window._mwapi || [];
_mwapi.push(['trackEvent', 'removecart', {pid: pid, sku: sku, parent_pid: parent_pid, qty: qty, bundle: bundle}]);

Example _mwapi.push(['trackEvent', 'removecart', {pid: 'YZ1546A', sku: 'YZ1546ALRG', parent_pid: 'YZ1546', qty: 2, bundle: [{pid: 'AB1546A', sku: 'AB1546ASML', price: 159}, {pid: 'D1546A', sku: 'D1546AML', price: 200}]}]);
```

Send us remove from cart details. It will help us provide you with better analysis.

### Parameters

Parameter | Description
--------- | -------------
pid | Product ID. The unique identifier of the product of the product you want us to track
parent_pid | Parent Product ID. The unique identifier of the parent product(incase of variant products) you want us to track
sku | The sku of the item
qty | The quantity of items remaining in the stock
bundle  | The array of items in bundle

### Bundle

Array of individual products incase of bundle product

Example: [{pid: pid, sku: sku, price: price}, ....]

Parameter | Description
--------- | -------------
pid | Product ID. The unique identifier of the product of the product you want us to track
sku | The sku of the item
price | The price of product


## Track Cart Info

> SDK js:

```javascript
MWSDK.trackEvent('bag', {products: products});

Example MWSDK.trackEvent('bag', {products: [{pid: 'YZ1546A', sku: 'YZ1546ALRG', qty: 2, price: 359, parent_pid: 'YZ1546', bundle: [{pid: 'YZ1546A', sku: 'YZ1546ALRG', price: 359}]}]});
```

> Script js:

```javascript
window._mwapi = window._mwapi || [];
_mwapi.push(['trackEvent', 'bag', {products: products}]);

Example _mwapi.push(['trackEvent', 'bag', {products: [{pid: 'YZ1546A', sku: 'YZ1546ALRG', qty: 2, price: 359, parent_pid: 'YZ1546', bundle: [{pid: 'YZ1546A', sku: 'YZ1546ALRG', price: 359}]}]}]);
```

Send us cart details. It will help us provide you with better analysis.

### Parameters

Parameter | Description
--------- | -------------
products | The products inside cart which you want us to track

### Items

Array of products in the cart

Example: [{pid: pid, sku: sku, qty: qty, price: price, parent_pid: parent_pid, bundle: bundle}, ....]

Parameter | Description
--------- | -------------
pid | Product ID The unique identifier of the product of the product you want us to track
sku | The sku of the item
qty | The quantity of items
price | The price of product
parent_pid | Parent Product ID. The unique identifier of the parent product(incase of variant products) you want us to track
bundle  | The array of items in bundle


## Track Buy Event

> SDK js:

```javascript
MWSDK.trackEvent('buy', {products: products, order: order});

Example MWSDK.trackEvent('buy', {products: [{pid: 'YZ1546A', sku: 'YZ1546ALRG', qty: 2, price: 359, parent_pid: 'YZ1546', bundle: [{pid: 'YZ1546A', sku: 'YZ1546ALRG', price: 359}]}], order: {order_number: 'ABDFGERSA123', revenue: 700, discount: 18, payment: 'cod', email: 'abc@gmail.com', created_at: '2016-05-12 12:00:12 -0400'}});
```

> Script js:

```javascript
window._mwapi = window._mwapi || [];
_mwapi.push(['trackEvent', 'buy', {products: products, order: order}]);

Example _mwapi.push(['trackEvent', 'buy', {products: [{pid: 'YZ1546A', sku: 'YZ1546ALRG', qty: 2, price: 359, parent_pid: 'YZ1546', bundle: [{pid: 'YZ1546A', sku: 'YZ1546ALRG', price: 359}]}], order: {order_number: 'ABDFGERSA123', revenue: 700, discount: 18, payment: 'cod', email: 'abc@gmail.com', created_at: '2016-05-12 12:00:12 -0400'}}]);
```

Send us purchase details. It will help us provide you with better analysis.

### Parameters

Parameter | Description
--------- | -------------
products | The list of ordered products you want us to track
order | The order details

### Products

Array of products bought

Example: [{pid: pid, sku: sku, qty: qty, price: price, parent_pid: parent_pid, bundle: bundle}, ....]

Parameter | Description
--------- | -------------
pid | Product ID. The unique identifier of the product of the product you want us to track
sku | The sku of the item
qty | The quantity of items
price | The price of product
parent_pid | Parent Product ID. The unique identifier of the parent product(incase of variant products) you want us to track
bundle  | The array of items in bundle

### Order
Parameter | Description
--------- | -------------
order_number | The unique order number
revenue | Total order revenue
discount  | Total discount applied on order
payment | The Payment method used for purchase
email | The email id of user who made the order
created_at | The time of order in the format YYYY-MM-DD HH:mm:ss ZZ


## Track Canceled Orders

> SDK js:

```javascript
MWSDK.trackEvent('cancel', {products: products, order: order});

Example MWSDK.trackEvent('cancel', {products: [{pid: 'YZ1546A', sku: 'YZ1546ALRG', qty: 2, price: 359, parent_pid: 'YZ1546', bundle: [{pid: 'YZ1546A', sku: 'YZ1546ALRG', price: 359}]}], order: {order_number: 'ABDFGERSA123', payment: 'cod', email: 'abc@gmail.com'}});
```

> Script js:

```javascript
window._mwapi = window._mwapi || [];
_mwapi.push(['trackEvent', 'cancel', {products: products, order: order}]);

Example _mwapi.push(['trackEvent', 'cancel', {products: [{pid: 'YZ1546A', sku: 'YZ1546ALRG', qty: 2, price: 359, parent_pid: 'YZ1546', bundle: [{pid: 'YZ1546A', sku: 'YZ1546ALRG', price: 359}]}], order: {order_number: 'ABDFGERSA123', payment: 'cod', email: 'abc@gmail.com'}}]);
```

Send us order cancel details. It will help us provide you with better analysis.

### Parameters

Parameter | Description
--------- | -------------
products | The list of products in the canceled order
order | The order details

### Products

Array of products canceled

Example: [{pid: pid, sku: sku, qty: qty, price: price, parent_pid: parent_pid, bundle: bundle}, ....]

Parameter | Description
--------- | -------------
pid | Product ID. The unique identifier of the product of the product you want us to track
sku | The sku of the item
qty | The quantity of items
price | The price of product
parent_pid | Parent Product ID. The unique identifier of the parent product(incase of variant products) you want us to track
bundle  | The array of items in bundle

### Order
Parameter | Description
--------- | -------------
order_number | The unique order number
payment | The Payment method used for purchase
email | The email id of user who requested order cancel


## Track Returns

> SDK js:

```javascript
MWSDK.trackEvent('return', {products: products, order: order});

Example MWSDK.trackEvent('return', {products: [{pid: 'YZ1546A', sku: 'YZ1546ALRG', qty: 2, price: 359, parent_pid: 'YZ1546', bundle: [{pid: 'YZ1546A', sku: 'YZ1546ALRG', price: 359}]}], order: {order_number: 'ABDFGERSA123', payment: 'cod', email: 'abc@gmail.com'}});
```

> Script js:

```javascript
window._mwapi = window._mwapi || [];
_mwapi.push(['trackEvent', 'return', {products: products, order: order}]);

Example _mwapi.push(['trackEvent', 'return', {products: [{pid: 'YZ1546A', sku: 'YZ1546ALRG', qty: 2, price: 359, parent_pid: 'YZ1546', bundle: [{pid: 'YZ1546A', sku: 'YZ1546ALRG', price: 359}]}], order: {order_number: 'ABDFGERSA123', payment: 'cod', email: 'abc@gmail.com'}}]);
```

Send us product return details. It will help us provide you with better analysis.

### Parameters

Parameter | Description
--------- | -------------
products | The list of products returned
order | The order details

### Products

Array of products returned

Example: [{pid: pid, sku: sku, qty: qty, price: price, parent_pid: parent_pid, bundle: bundle}, ....]

Parameter | Description
--------- | -------------
pid | Product ID. The unique identifier of the product of the product you want us to track
sku | The sku of the item
qty | The quantity of items
price | The price of product
parent_pid | Parent Product ID. The unique identifier of the parent product(incase of variant products) you want us to track
bundle  | The array of items in bundle

### Order
Parameter | Description
--------- | -------------
order_number | The unique order number
payment | The Payment method used for purchase
email | The email id of user who made the return



## Track Product Custom Event

> SDK js:

```javascript
MWSDK.trackEvent('custom', {pid: pid, metric: metric, attribute: attribute, url: url});

Example MWSDK.trackEvent('custom', {pid: 'YZ1546', metric: 'quickview', attribute: {collection: '50%SALE_PAGE'}, url: 'www.yourstore.com/pid/12'});
```

> Script js:

```javascript
window._mwapi = window._mwapi || [];
_mwapi.push(['trackEvent', 'custom', {pid: pid, metric: metric, attribute: attribute, url: url}]);

Example _mwapi.push(['trackEvent', 'custom', {pid: 'YZ1546', metric: 'quickview', attribute: {collection: '50%SALE_PAGE'}, url: 'www.yourstore.com/pid/12'}]);
```

Send us custom events to track.

### Parameters

Parameter | Description
--------- | -------------
pid | Product ID. The unique identifier of the product you want us to track
metric  | Custom metric you want us to track
attribute | Custom attribute you want us to track
url  | The product url

### Attribute

Object containing attribute and attribute value mapping.

Example: {'collection': '50%SALE_PAGE'}