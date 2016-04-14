# MaterialBarcodeScanner
Easy to use barcode reader for your Android Project (Uses Google Mobile Vision API)

[ ![Download](https://api.bintray.com/packages/edwardvraak/maven/MaterialBarcodeScanner/images/download.svg) ](https://bintray.com/edwardvraak/maven/MaterialBarcodeScanner/_latestVersion)

**Still in alpha so expect bugs, pain and suffering!**

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
compile 'com.edwardvanraak:MaterialBarcodeScanner:0.0.3-ALPHA'
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

Check out the example project for code required for camera permissions on Android 6.0 Marshmallow

##Screenshots
![Image](https://raw.githubusercontent.com/EdwardvanRaak/MaterialBarcodeScanner/master/DEV/screens/screenshot1.png)


