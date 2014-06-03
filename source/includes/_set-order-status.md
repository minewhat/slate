# Set Order Status


```javascript
MWSDK.orderStatus(email_id, order_id, order_status);
```

```plaintext
window._mwapi = window._mwapi || [];
_mwapi.push(['orderStatus',email_id, order_id, order_status ]);
```

```shell
https://engage.minewhat.com/api/updateOrderInfo/?c=customer_id&email=email_id&order=order_id&status=order_status
```

Users might be visiting your website to check the order status. We can guide while they are at it. Send us order status details when a user lands on your page.

### Parameters

Parameter | Description
--------- | -------------
email_id | Email Id of the signed in customer
order_id | Order Id of the signed in customer
order_status | Order Status of the Order Id, 0 - RECEIVED , 1 - SHIPPED , 2 - DELIVERED , 3 - RETURN , 4 - RETURN_ACCEPTED