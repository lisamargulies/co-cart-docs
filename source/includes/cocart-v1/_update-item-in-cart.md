## Update Item in Cart ##

<img src="images/github.svg" width="20" height="20" alt="GitHub Mark Logo"> [Edit on GitHub](https://github.com/co-cart/co-cart-docs/blob/master/source/includes/cocart-v1/_update-item-in-cart.md)

This API helps you to update an item in the cart. You can also request to return the whole cart once item is updated to reduce API requests and use the [Get Cart Content](#get-cart-contents) properties.

### Properties ###

| Property         | Type   | Description       |
| ---------------- | ------ | ----------------- |
| `cart_item_key`  | string | The cart item key of the product in the cart you want to update. <i class="label label-info">mandatory</i> |
| `quantity`       | float  | Set the quantity of the product you want to update in the cart. <i class="label label-info">Default is 1</i> |
| `return_cart`    | bool   | Set as true to return the whole cart once item is updated. <i class="label label-info">optional</i> |

### HTTP request ###

<div class="api-endpoint">
  <div class="endpoint-data">
    <i class="label label-post">POST</i>
    <h6>/wp-json/cocart/v1/item</h6>
  </div>
</div>

```shell
curl -X POST https://example.com/wp-json/cocart/v1/item \
  -H "Content-Type: application/json" \
  -d '{
    "cart_item_key": "404dcc91b2aeaa7caa47487d1483e48a",
    "quantity": 2
  }'
```

```javascript--jquery
var settings = {
  "url": "https://example.com/wp-json/cocart/v1/item",
  "method": "POST",
  "data": {
    "cart_item_key" : "404dcc91b2aeaa7caa47487d1483e48a",
    "quantity" : 2
  }
};

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

```php
<?php
$curl = curl_init();

$args = array(
  'cart_item_key' => '404dcc91b2aeaa7caa47487d1483e48a',
  'quantity' => 2
);

curl_setopt_array( $curl, array(
  CURLOPT_URL => "https://example.com/wp-json/cocart/v1/item",
  CURLOPT_CUSTOMREQUEST => "POST",
  CURLOPT_POSTFIELDS => $args,
  CURLOPT_RETURNTRANSFER => true
) );

$response = curl_exec($curl);

curl_close($curl);

echo $response;
```

```php--wp-http-api
<?php
$args = array(
  'cart_item_key' => '404dcc91b2aeaa7caa47487d1483e48a',
  'quantity' => 2
);
$response = wp_remote_post( 'https://example.com/wp-json/cocart/v1/item', $args );
$body = wp_remote_retrieve_body( $response );
```

> JSON response example

```json
{
  "message":"The quantity for 'Woo T-Shirt' has increased to '2'.",
  "quantity":2
}
```
