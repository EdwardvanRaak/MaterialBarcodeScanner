# MaterialBarcodeScanner
Easy to use barcode reader for your Android Project (Uses Google Mobile Vision API)

[ ![Download](https://api.bintray.com/packages/edwardvraak/maven/MaterialBarcodeScanner/images/download.svg) ](https://bintray.com/edwardvraak/maven/MaterialBarcodeScanner/_latestVersion)
[![Android Arsenal](https://img.shields.io/badge/Android%20Arsenal-MaterialBarcodeScanner-brightgreen.svg?style=flat)](http://android-arsenal.com/details/1/3439)



**Only supports very basic features right now, please wait warmly for version 1.0!**

###Overview
- Integrate in a **few minutes**
- Quick and simple api
- No external apps required
- Uses Google Mobile Vision API (fast scanning, local)
- Automatically parses QR Codes, Data Matrix, PDF-417, and Aztec values
- Supports 1D barcodes: EAN-13, EAN-8, UPC-A, UPC-E, Code-39, Code-93, Code-128, ITF, Codabar
- Supports 2D barcodes: QR Code, Data Matrix, PDF-417, Aztec

#Setup
##1. Provide gradle dependency

```gradle
compile 'com.edwardvanraak:MaterialBarcodeScanner:0.0.4-ALPHA'
```

##2. Build a MaterialBarcodeScanner

```java
    private void startScan() {
        /**
         * Build a new MaterialBarcodeScanner
         */
        final MaterialBarcodeScanner materialBarcodeScanner = new MaterialBarcodeScannerBuilder()
                .withActivity(MainActivity.this)
                .withEnableAutoFocus(true)
                .withBleepEnabled(true)
                .withBackfacingCamera()
                .withText("Scanning...")
                .withResultListener(new MaterialBarcodeScanner.OnResultListener() {
                    @Override
                    public void onResult(Barcode barcode) {
                        barcodeResult = barcode;
                        result.setText(barcode.rawValue);
                    }
                })
                .build();
        materialBarcodeScanner.startScan();
    }

 ```
 
 Hook it up to a button
 
```java
  fab.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View view) {
                startScan();
            }
        });
 ```
 
##3. Start scanning!

Check out the full [example project](https://github.com/EdwardvanRaak/MaterialBarcodeScanner/blob/master/app/src/main/java/com/edwardvanraak/materialbarcodescannerexample/MainActivity.java) for code required for camera permissions on Android 6.0 Marshmallow

##Screenshots
![Image](https://raw.githubusercontent.com/EdwardvanRaak/MaterialBarcodeScanner/master/DEV/screens/screenshot1.png)

#Developed By

* Edward van Raak
 * edwardvraak@gmail.com
 * [Donate with Paypal](https://www.paypal.me/EdwardvanRaak)

