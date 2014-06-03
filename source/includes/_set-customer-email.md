# Set Customer Email


```javascript
MWSDK.setuser(email_id);
```

```plaintext
window._mwapi = window._mwapi || [];
_mwapi.push(['setUser', email_id]);
```

```shell
https://engage.minewhat.com/api/updateCustomerInfo/?c=customer_id&uid=user_id&email=email_id
```

Users can clear cache and cookies from browser. Help us associate logged in users with their multiple session online by sending user email when he signs in.

### Parameters

Parameter | Description
--------- | -------------
email_id |  Email Id of the signed in customer
