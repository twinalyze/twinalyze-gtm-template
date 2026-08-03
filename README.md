# Twinalyze Web Analytics GTM Template

Twinalyze Web Analytics is a Google Tag Manager custom template for installing the Twinalyze Web SDK, enabling automatic website event tracking, and sending custom events through Google Tag Manager.

## Features

* Initialize the Twinalyze Web SDK through Google Tag Manager
* Track automatic website events:

  * pageView
  * scrollDepth
  * elementClick
  * formStart
  * formSubmit
  * searchResultsView
  * fileDownload
* Send custom events using GTM triggers and variables
* Configure API base URL, SDK URL, SDK version, and debug mode

## Setup

1. Add the Twinalyze Web Analytics template to your Google Tag Manager workspace.
2. Create a new tag using the Twinalyze Web Analytics template.
3. Select **Initialize SDK**.
4. Enter your Twinalyze API Key.
5. Enter your Twinalyze Client Token / Public Write Key.
6. Keep the default API Base URL unless Twinalyze support gives you a custom endpoint.
7. Set the trigger to **Initialization - All Pages**.
8. Save and publish your GTM container.

## Automatic Events

When enabled, the template can automatically track:

* pageView
* scrollDepth
* elementClick
* formStart
* formSubmit
* searchResultsView
* fileDownload

## Custom Events

To send a custom event, push data to the GTM dataLayer:

```js
window.dataLayer = window.dataLayer || [];
window.dataLayer.push({
  event: "add_to_cart",
  product_id: "P123",
  product_name: "Pearl Hair Clip",
  price: 499,
  currency: "INR"
});
```

Then create a GTM Custom Event trigger for `add_to_cart` and create a Twinalyze tag with action **Track Custom Event**.

Example Twinalyze custom event setup:

* Action: **Track Custom Event**
* Event Name: `addToCart`
* Event Properties:

  * `product_id` = `{{DLV - product_id}}`
  * `product_name` = `{{DLV - product_name}}`
  * `price` = `{{DLV - price}}`
  * `currency` = `{{DLV - currency}}`

## Permissions Used

This template uses the following GTM permissions:

* Injects scripts
* Accesses global variables
* Uses template storage
* Logs to console

These permissions are used to load the Twinalyze Web SDK, initialize the SDK, send custom events, store temporary template state, and log messages only during debugging.


## Documentation

https://docs.twinalyze.com/integrations/gtm

## Support

https://twinalyze.com
