
## Installation

You can install widget using npm

```bash
  npm i wl-barcode-scanner
```
    
## Example of usage

To use the barcode scanner widget, you need to include two mandatory elements with specific IDs: 
- <div id="reader-wrapper"><div id="reader"></div></div> for initializing the scanner
- <div id="reader-result"></div> where the result will be displayed.

```html
<!DOCTYPE html>
<html lang="en">
   <head>
      <meta charset="UTF-8" />
      <meta name="viewport" content="width=device-width, initial-scale=1.0" />
      <title>Document</title>
   </head>
   <body>
      <button id="reader-init">Scan</button>
      <div id="reader-wrapper">
         <div id="reader"></div>
      </div>
      <div id="reader-result"></div>
   </body>
   <script src="./node_modules/wl-barcode-scanner/scanner.js"></script>
   <script>
      const accessToken = ""; // Put access token here
      const tenant = ""; // Put tenanntId here
      const scanner = new BarcodeScanner(accessToken, tenant);
      document.getElementById("reader-init").addEventListener("click", async () => {
         scanner.scanBarcode();
      });
   </script>
</html>
``` 

