# LNBits-Quickening-Manager
Extension for LNBits to manage PoS devices.
The Idea is to have a user friendly setup to run 1..n PoS devices which can accept Lightning Payments and can provide refunds with LNurl. LNBits will be used to manage the Wallets and Devices. The Lightning Node will be abstracted, so that different lightning backend implementations can be used or the backend can be replaced easily. After configure the PoS Wallets the extension shall be able to Flash the Firmware with correct configuration to a M5StackFaces.  


*This Extension base on following Projects:*
- M5StackSats
- Quickening
- LNBits
- RaspiBlitz
- LNurl
- arduino-cli


## Hardware Setup:
**general HW Requirement:**
- Raspiblitz on a dedicated Raspberry Pi or LND Server (LND Server)
- LNBits runs on a dedicated Raspberry Pi or Server (LNBits Server)
- 1..n Quickening (Quick_1 .. Quick_n)

```
 -----------
|	    |
|LND 	    |
|	    |
 -----------
 	|
 	| TOR
 	|
 -----------
|	    |
|LNBits	    |
|	    |
 -----------
 	|
 	| WiFi 
 	|
 -----------
|	     |
|Quickening  |
|	     |
 -----------
```
**Additional HW Requirements**
- Wifi Dongel for LNBits Server to create Access Point for Quickenings
- M5StackFaces with an connected Cradle to LNBits Server

## Features
- provide an API for PoS to create Invoices 
- provide an API to check payment status for invoices
- provide an API to create LNURL (one time) to have refund option on PoS
- manage PoS Wallets
    - who can pay in only & pay out
    - automagically balance management of the PoS wallets 
- manage PoS API Access Keys
    - how long do they have access to pay out (timeout / theft protection)
### LNBits on dedicated RPi Features
- configure PoS (Flash via USB)
    - flash all or additional POS's via LNBits
    - fetch updates from github repo to update POS's when available
- create a dedicated WiFi AP for Quickenings
 
