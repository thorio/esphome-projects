# ESPHome Velux Controller

![finished product](media/result.jpg)

This project modifies a Velux KLI 310 or similar remote control to integrate with home assistant.
It replaces the back panel of the original remote, powers it from the wall, and can report state back to home assistant even if you press the physical buttons.

Installing it on the remote only requires removing the back and batteries, soldering 5 wires and plugging it into the control board. This process is nondestructive and reversible.

It runs on anywhere between 5V and 12V, though 5V is preferred.

![interior view](media/interior.jpg)

## Bill of Materials

- 1x ESP-12F module
	([Mouser](https://eu.mouser.com/ProductDetail/Adafruit/2491?qs=N%2F3wi2MvZWDVFv7HwruvGQ%3D%3D),
	[AliExpress](https://www.aliexpress.com/item/1005004495916418.html))
- 1x SOT223 AMS1117-3.3 linear voltage regulator
	([DigiKey](https://www.digikey.com/en/products/detail/texas-instruments/TLV1117LV33DCYR/2666508),
	[AliExpress](https://www.aliexpress.com/item/1005004529378722.html))
- 3x SOT23 MMBT3904 transistor
	([DigiKey](https://www.digikey.com/en/products/detail/diotec-semiconductor/MMBT3904/20391048),
	[AliExpress](https://www.aliexpress.com/item/1005002334131697.html))
- 8x 0603 10kΩ resistor
	([DigiKey](https://www.digikey.com/en/products/detail/stackpole-electronics-inc/RMCF0603FT10K0/1761235),
	[AliExpress](https://www.aliexpress.com/item/32867298442.html))
- 6x 0603 1kΩ resistor
	([DigiKey](https://www.digikey.com/en/products/detail/stackpole-electronics-inc/RMCF0603FT1K00/1761077),
	[AliExpress](https://www.aliexpress.com/item/32867298442.html))
- 2x 0805 100nF ceramic capacitor
	([DigiKey](https://www.digikey.com/en/products/detail/samsung-electro-mechanics/CL21B104KACNNNC/3886757),
	[AliExpress](https://www.aliexpress.com/item/32964553793.html))
- 1x SMA 22μF tantalum capacitor
	([DigiKey](https://www.digikey.com/en/products/detail/kemet/T491A226M010AT/818553),
	[AliExpress](https://www.aliexpress.com/item/1005006136419609.html))
- 2x PTS820 tactile switch
	([DigiKey](https://www.digikey.com/en/products/detail/cit-relay-and-switch/CS1213AGF160/16607723),
	[AliExpress](https://www.aliexpress.com/item/1005004307665595.html))
- 1x DC-005 jack
	([DigiKey](https://www.digikey.com/en/products/detail/tensility-international-corp/54-00166/10459294),
	[AliExpress](https://www.aliexpress.com/item/4001206395694.html))
- 1x male pin header 1x4 2.54mm pitch
	([AliExpress](https://www.aliexpress.com/item/4000857385112.html))
- 1x 2Pin JST-XH connector pair, right angle
	([DigiKey](https://www.digikey.com/en/products/detail/jst-sales-america-inc/S2B-XH-A-1/9961922),
	AliExpress [assortment](https://www.aliexpress.com/item/1005006498660940.html) + [right angle](https://www.aliexpress.com/item/1005004067623293.html))
- 1x 3Pin JST-XH connector pair, right angle
	([DigiKey](https://www.digikey.com/en/products/detail/jst-sales-america-inc/S3B-XH-A-1/1556255),
	AliExpress [assortment](https://www.aliexpress.com/item/1005006498660940.html) + [right angle](https://www.aliexpress.com/item/1005004067623293.html))
- spare wire + JST-XH crimps
	([AliExpress assortment](https://www.aliexpress.com/item/1005006498660940.html))
- 4x M2x6mm coarse thread screws, pan head
	([AliExpress](https://www.aliexpress.com/item/33043885403.html))
- 4x M2 paper washers
	([AliExpress](https://www.aliexpress.com/item/1005003052657995.html))

I didn't need these, but you can add them if your ESP is unhappy with the supply voltage:

> Note: It isn't super obvious from the footprints, but these additional capacitors are supposed to mount horizontally against the board facing toward the bottom. If mounted vertically they may prevent the case from being closed.

- 1x 470μF >=5V electrolytic capacitor, 2mm pitch
	([DigiKey](https://www.digikey.com/en/products/detail/wurth-elektronik/860010273011/5726952),
	[AliExpress assortment](https://www.aliexpress.com/item/1940215752.html))
- 1x 10μF >=16V electrolytic capacitor, 1.5mm pitch
	([DigiKey](https://www.digikey.com/en/products/detail/nichicon/UVR1C100MDD6TP/4328964),
	[AliExpress assortment](https://www.aliexpress.com/item/1940215752.html))


## Attribution
Thanks to these fine people for their research on how to interface with the remote control:
- https://ottelo.jimdofree.com/velux-integra-esp8266/
- https://www.reddit.com/r/homeassistant/comments/pzhkia/hack_velux_kli3xx_to_use_blinds_without_gateway/
