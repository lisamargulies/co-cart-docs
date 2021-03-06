# Cross Sells #

<img src="images/github.svg" width="20" height="20" alt="GitHub Mark Logo"> [Edit on GitHub](https://github.com/co-cart/co-cart-docs/blob/master/source/includes/cocart-v1/pro/_cross-sells.md)

This API helps you get the cross sells. It returns not just the product ID's but the product name, price, regular price and sale price.

## Cross Sell Properties ##

| Property  | Type | Description |
| --------- | ---- | ----------- |
| `thumb`   | bool | Set as true to return the product thumbnail for each item. |

### HTTP request ###

<div class="api-endpoint">
  <div class="endpoint-data">
    <i class="label label-get">GET</i>
    <h6>/wp-json/cocart/v1/cross-sells</h6>
  </div>
</div>

```shell
curl -X GET https://example.com/wp-json/cocart/v1/cross-sells \
  -H "Content-Type: application/json"
```

```javascript--jquery
var settings = {
  "url": "https://example.com/wp-json/cocart/v1/cross-sells",
  "method": "GET"
};

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

```php
<?php
$curl = curl_init();

curl_setopt_array( $curl, array(
  CURLOPT_URL => "https://example.com/wp-json/cocart/v1/cross-sells",
  CURLOPT_CUSTOMREQUEST => "GET",
  CURLOPT_RETURNTRANSFER => true
) );

$response = curl_exec($curl);

curl_close($curl);

echo $response;
```

```php--wp-http-api
<?php
$response = wp_remote_get( 'https://example.com/wp-json/cocart/v1/cross-sells' );
$body = wp_remote_retrieve_body( $response );
```

> JSON response example

```json
{
    "29": {
        "id": 29,
        "product_name": "Hoodie with Logo",
        "product_title": "Hoodie with Logo",
        "price": "£45.00",
        "regular_price": "£45.00",
        "sale_price": "£0.00"
    },
    "30": {
        "id": 30,
        "product_name": "Hoodie with Pocket",
        "product_title": "Hoodie with Pocket",
        "price": "£35.00",
        "regular_price": "£45.00",
        "sale_price": "£35.00"
    },
    "31": {
        "id": 31,
        "product_name": "Hoodie with Zipper",
        "product_title": "Hoodie with Zipper",
        "price": "£45.00",
        "regular_price": "£45.00",
        "sale_price": "£0.00"
    }
}```
