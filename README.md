# zbtprinter
A Cordova/Phonegap driver for Zebra wifi printers

This is a fork of https://github.com/michael79bxl/zbtprinter.git

## Usage
You can find Zebra printer using:

```
window.cordova.plugins.zwifiprinter.find(
    function(result) {
        if(typeof result == 'string') {
            address = result;
        } else {
            address = result.address;
        }
        alert('Zbtprinter: connect success: ' + address);
    }, function(error) {
        alert('Zbtprinter: connect fail: ' + error);
    }
);
```

You can send data in ZPL Zebra Programing Language:

```
window.cordova.plugins.zbtprinter.print(address, "^XA^FO20,20^A0N,25,25^FDThis is a ZPL test.^FS^XZ",
    function(success) {
        alert("Zbtprinter print success: " + success);
    }, function(fail) {
        alert("Zbtprinter print fail:" + fail);
        deferred.reject(fail);
    }
);
```

## Install Cordova

```
cordova plugin add ccordova-plugin-zwifi-printer
```

## ZPL - Zebra Programming Language
For more information about ZPL please see the  [PDF Official Manual](https://support.zebra.com/cpws/docs/zpl/zpl_manual.pdf)
