# Datatrans PayPal Button

Render PayPal buttons for payments via Datatrans. 

## Usage example

```js
PayPalButton.init({
  merchantId: '1100025160',
  reqType: 'CAA',
  currencyCode: 'CHF',
  amount: '100',
  createAlias: false
});

PayPalButton.on('init', function() {
  console.log('init event dispatched');
  PayPalButton.create(document.getElementById('paybutton'), paypalOptions);
});

PayPalButton.on('create', function() {
  console.log('create event dispatched');
});

PayPalButton.on('authorization', function(response) {
  console.log('authorization response:', response);
});

PaymentButton.on('error', function(error) {
  console.log('Error:', JSON.stringify(error));
});
```

## Events

The following events can be subscribed to:

- `init` - emitted when the library was initialized
- `create` - emitted when all buttons were rendered
- `authorization` - emitted when the authorization process has completed
- `error` - emitted when an error happens
