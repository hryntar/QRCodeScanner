
## Installation

You can install library using npm

```bash
  npm i wl-barcode-scanner
```
    
## Example of usage
```html
<!DOCTYPE html>
<html lang="en">
<head>
   <meta charset="UTF-8">
   <meta name="viewport" content="width=device-width, initial-scale=1.0">
   <title>Document</title>
</head>
<body>
   <div style="text-align: center">
      <div id="reader" style="max-width: 100%; height: 100%"></div>
      <div id="show" style="display: none">
         <h4>Scanned Result:</h4>
         <p id="result"></p>
         <h3>Product:</h3>
         <p id="product-result"></p>
      </div>
      <button
         onclick="startBarcodeScanner()"
         style="
            height: 40px;
            width: 100px;
            display: flex;
            align-items: center;
            font-size: 14px;
            column-gap: 6px;
            text-transform: uppercase;
            letter-spacing: 1px;
            background-color: black;
            color: white;
            cursor: pointer;
         "
      >
         <svg width="30px" height="30px" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
            <path
               fill-rule="evenodd"
               clip-rule="evenodd"
               d="M6.75 4.5H3V8.25H4.5V6H6.75V4.5ZM6.75 8.25V15.75H8.25V8.25H6.75ZM9.75 15.75V8.25H11.25V15.75H9.75ZM12.75 8.25V15.75H14.25V8.25H12.75ZM15.75 15.75V8.25H17.25V15.75H15.75ZM17.25 19.5H21V15.75H19.5V18H17.25V19.5ZM3 19.5V15.75H4.5L4.5 18H6.75L6.75 19.5H3ZM21 8.25V4.5H17.25V6H19.5V8.25L21 8.25Z"
               fill="#fff"
            />
         </svg>
         <p>Scan</p>
      </button>
   </div>
</body>
<script src="./node_modules/wl-barcode-scanner/scanner.js"></script>
<script> 
   function startBarcodeScanner() {
      const scanner = new BarcodeScanner();
      scanner
         .scanBarcode()
         .then((productInfo) => {
            document.getElementById("show").style.display = "block";
            document.getElementById("result").textContent = productInfo;
            document.getElementById("product-result").textContent = JSON.stringify(productInfo);
         })
         .catch((error) => {
            console.error("Error scanning barcode:", error);
         });
   }
</script>
</html>
```




