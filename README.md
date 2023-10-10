# a-un-require-js-issue

# Information about the issue

In our flow we attempt to insert `"https://api.unifaun.com/rs-extapi/v1/delivery-checkouts-widget/unifaun-checkout-all.min.js"` to the partner page when the shipping module should be displayed in Checkout3 application. We found out that in some cases the script is added and downloaded but the `UnifaunCheckout` object is not available on the window. After some research we found out that if the page contains [require.js](https://requirejs.org/) loading the bundle fails silently - there is no error or console log present in the page. When accessing `require.config();` error is displayed `"Uncaught Error: Mismatched anonymous define()` pointing to the issue on require.js page [Mismatched anonymous define() modules ...](<https://requirejs.org/docs/errors.html#mismatch:~:text=steps%20to%20reproduce.-,MISMATCHED%20ANONYMOUS%20DEFINE()%20MODULES%20...,-%C2%A7%201>)

# HOW TO REPRODUCE ISSUE

1. Open index.html
2. Click button `Click to add UnifaunCheckout script to page!` to attempt loading UnifaunCheckout javascript bundle
3. > Error
4. UnifaunCheckout is not attached to the window object

# CONFIRMING REQUIRE.JS CAUSES THE ISSUES

1. Edit index.html
2. Comment out line nr.8 `<script src="https://requirejs.org/docs/release/2.3.6/minified/require.js"></script>`
3. Save file and open it again
4. Click button `Click to add UnifaunCheckout script to page!` to attempt loading UnifaunCheckout javascript bundle
5. > Everything OK
6. UnifaunCheckout is attached to the window object - and it's ready for use.
