# Collection

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
https://api.minewhat.com/v1/updateinv/?c=customer_id&pid=product_id&sku=sku&qty=quantity
```

Send us inventory details for all the products. It will help us provide you with better analysis on what to keep on in your inventory so that you never run out of stock or pile it up.

### Parameters

Parameter | Description
--------- | -------------
customer_id | The unique identifier of the customer.Only used in REST calls, JS call internally use it.
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
> REST:

```shell
https://api.minewhat.com/v1/updateCustomerInfo/?c=customer_id&uid=user_id&email=email_id
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
> REST:

```shell
https://api.minewhat.com/v1/updateOrderInfo/?c=customer_id&email=email_id&order=order_id&status=order_status
```

Users might be visiting your website to check the order status. We can guide while they are at it. Send us order status details when a user lands on your page.

### Parameters

Parameter | Description
--------- | -------------
email_id | Email Id of the signed in customer
order_id | Order Id of the signed in customer
order_status | Order Status of the Order Id, 0 - RECEIVED , 1 - SHIPPED , 2 - DELIVERED , 3 - RETURN , 4 - RETURN_ACCEPTED