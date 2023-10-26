# Information about the issue

The `Automatic publicPath is not supported in this browser` issue is a result of the webpack bundler used by the nShift module. When the webpack bundler loads, it attempts to identify public paths. By default, it selects the 'src' attribute of the last script tag present on the page. If the last script tag lacks an 'src' attribute, it triggers an exception.

# HOW TO REPRODUCE ISSUE

1. Open index.html
2. Click button `Click to add UnifaunCheckout script to page!` to attempt loading UnifaunCheckout javascript bundle
3. > Error
4. Uncaught Error: Automatic publicPath is not supported in this browser


