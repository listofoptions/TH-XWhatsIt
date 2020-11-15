# Bill Of Materials

## To build 1 pcs of the TH Xwhatsit controller Rev. 0.1.1, you need:

* 1pcs "Pro Micro 5V/16MHz" development board
    * 2pcs male 12-pin header (usually comes included with the Pro Micro)
* 1pcs MCP4921-EP DAC
* 2pcs LM339 comparator
    * (only 1pcs is really needed if the controller will only ever be used on <= 4-row keyboards, such as non-Displaywriter standard beamspring keyboards)
* 3pcs 74AHC595 or 74HCT595 or 74HC595 shift registers
    * (only 2pcs is really needed if the controller will only ever be used on <= 16-column keyboards, such as Model F of Displaywriter keyboards)
* 7pcs 100nF Through Hole Ceramic Capacitors (pin pitch is 2.54mm)
* 1pcs 1K through hole 0.25W resistor (better if subminiature type, metal film)
* 2pcs 20K through hole 0.25W resistors (better if subminiature type, metal film)
* 2pcs 4.7K through hole 0.25W resistors (better if subminiature type, metal film)
* 100kohm Resistor Networks, or Resistors, two options:
    * These are recommended to be high precision (1% or 2%), but the design will likely work with 5% resistors too.
    * Option 1: 2pcs 100K 5-pin resistor networks
        * Make sure it's the kind that has a single common pin on one of the sides.
        * (only 1pcs is really needed if the controller will only ever be used on <= 4-row keyboards, such as non-Displaywriter standard beamspring keyboards)
    * Option 2: 8pcs 100K through hole 0.25W resistors (these are the resistors marked with ALT on the PCB)  (better if subminiature type, metal film)
        * (only 4pcs is really needed if the controller will only ever be used on <= 4-row keyboards, such as non-Displaywriter
* 3.96mm 30-pin card edge connectors (if using the controller for Beamspring/Displaywriter keyboards, and if you don't wish to desolder, and reuse the original connector from the original controller PCB)
* M3 standoff, screw, nut, and washers (optional, useful for better mechanical stability with daughterboards)
* 2.54 mm pitch through hole pin headers:
    * Optional if not using Solenoid/Expansion header:
        * 2x3-pin male pinheader (through-hole, can be vertical or 90-degree)
    * Optional if soldering wires directly to the motherboard, and not using the daughtercards:
        * male 27-pin pinheader (straight, through hole)
        * female 27-pin pinheader (straight, through hole)
        * male 12-pin pinheader (straight, through hole)
        * female 12-pin pinheader (straight, through hole)
    * You can buy pinheaders with more pins then necessary, and cut them. You can use two 1-row pin headers to make a vertical Solenoid connector.

## Notes regarding older revisions:

* Previous revisions can't fit an M3 standoff, so you have to get an M2 standoff
* Combining daughtercard/motherboard from different revisions is possible, (the pin headers are in the same relative positions), but the hole that can be used for a standoff is in a slightly different position, so if combining you can't use standoffs
* 10Kohm resistor networks, present in previous revisions are optional, they don't need to be mounted even if using a previous-revision board.
* the 10uF capacitor which was present in the first version of the TH MUST NOT be mounted.
* Only one pair of 1K, 4.7k resistors is necessary to set the BIAS voltage. Some previous TH versions had two pairs. It is okay to only mount one pair, or to mount both pairs, but the two bias points must be connected for >4-row keyboards.
* Previous versions supported fewer card edge connector types when using them for Beamspring/Displaywriter keyboards.

## Octopart BOM:

An octopart BOM has been assembled here: [link](https://octopart.com/bom-tool/UL7oTH6f)

## TME quick buy - uploading products from a file:

* [Go to this URL](https://www.tme.eu/ro/en/Profile/QuickBuy/load.html)
* Click "Uploading products from a file"
* Select "csv"
* Select [tme_bom.csv](tme_bom.csv) from this folder.
* Click Upload
* Click Add to Order
* Note: quantities have been adjusted for minimum order amounts.

## Individual links to various sources

All links in this document may become out of date. They may become unavailable, or price changes may make them not be good options anymore. Please do your own research before committing to buy.

* Pro Micro 5V/16MHz
    * Sparkfun Pro Micro: [link](https://www.sparkfun.com/products/12640)
        * More on the pricier side, but Sparkfun designed the Pro Micro, so they are probably the highest quality source.
        * They also have many distributors: [link](https://www.sparkfun.com/distributors)
          * The original Sparkfun Pro Micro is also available from these distributors:
            * Digikey: Digi-Key Part Number: [1568-1060-ND](https://www.digikey.com/en/products/detail/DEV-12640/1568-1060-ND/5140825)
            * Mouser: Mouser No: [474-DEV-12640](https://eu.mouser.com/ProductDetail/SparkFun/DEV-12640?qs=%2Fha2pyFaduhrMhBRm%252B%2FHWtJdSvRGjEaL1xOzwYvsZoVc9s6MYCFNnA%3D%3D)
    * Aliexpress:
        * There are many sellers on [aliexpress.com](https://www.aliexpress.com), the best deals are often for bulk quantities, but not always
        * Examples:
            * [link](https://www.aliexpress.com/item/4000087265549.html) (EDIT they recently raised their prices, cheaper may be available)
    * Ebay:
        * Also many sellers, examples:
            * [link](https://www.ebay.co.uk/itm/Pro-Micro-ATmega32U4-5V-16MHz-Replace-ATmega328-Pro-Mini-for-Arduino/283659748382?hash=item420b70441e:g:~zcAAOSwdbRdupUr)
            * [link](https://www.ebay.co.uk/itm/Arduino-Pro-Micro-ATmega32U4-MU-5V-16MHz-Leonardo-Compatible-Board/183467795511?ssPageName=STRK%3AMEBIDX%3AIT&_trksid=p2057872.m2749.l2649)
            * [link](https://www.ebay.co.uk/itm/Arduino-Pro-Micro-ATmega32U4-AU-5V-16MHz-Leonardo-Compatible-Board/183467793639?ssPageName=STRK%3AMEBIDX%3AIT&_trksid=p2057872.m2749.l2649) - this is a less-then usual 'square' version where the microcontroller is in a TQFP package.
    * Alternatives, that are not exactly pro micro:
        * Sparkfun qwiic pro USB-C (not tested): [link](https://www.sparkfun.com/products/15795)
    * DO NOT BUY:
        * Don't buy 3V/8MHz Pro Micros, they are not supported.
        * Don't buy "DM DIY MORE" Pro Micros -- these are wider then most other pro micros, and won't physically fit [link](https://www.ebay.co.uk/itm/ATMEGA32U4-Pro-Micro-3-3V-5V-8-16MHz-USB-Controller-Board-Bootloader-for-Arduino/153425765054?ssPageName=STRK%3AMEBIDX%3AIT&_trksid=p2057872.m2749.l2649)
        * Don't buy Proton-C, because non-AVR cores are not supported by my firmware. [link](https://qmk.fm/proton-c/)
        * *Maybe* do not buy Pro Micro drop-in replacements, that use DFU bootloader. These can be supported, but only if you compile your firmware locally. Otherwise many bootloader entry methods will not work. You also have the option of replacing the bootloader on one of these with ISP programming. Example: [Elite-C](https://keeb.io/products/elite-c-low-profile-version-usb-c-pro-micro-replacement-atmega32u4)
* Card Edge Connector (For beamsprings/displaywriters)
    * You can use the original connector, desoldered from the original controller
    * Please read this [thread](https://deskthority.net/viewtopic.php?f=7&t=24511&p=473024&hilit=tightness#p473024)
    * EDAC connector sources: (I recommend pin-modding these)
      * Higher pin-count, must be cut, but the extra pins are useful if pin-modding: 
        * Digikey: Digi-Key Part Number: [151-1359-ND](https://www.digikey.com/en/products/detail/307-086-520-202/151-1359-ND/1292373)
        * Mouser: Mouser No: [587-307-086-520-202](https://eu.mouser.com/ProductDetail/EDAC/307-086-520-202?qs=%2Fha2pyFadujtxmsdbs3PHxpkXnbJgP4ckMerl2TaY6ijMRB8PMNaQzySHxFo%2F4Xv)
      * TME: Not a great option, you can buy two of these lower-pin-count connectors, and cut both, and put them next to each other: TME Symbol: [307-030-520-202](https://www.tme.eu/ro/en/details/307-030-520-202/idc-connectors/edac/)
* MCP4921-E/P DAC:
    * TME: TME Symbol: [MCP4921-E/P](https://www.tme.eu/ro/en/details/mcp4921-e_p/d-a-converters-integrated-circuits/microchip-technology/)
    * LCSC: Last checked it wasn't available in a DIP package. 15 nov. 2020. LCSC Part # [C640392](https://lcsc.com/product-detail/Pre-ordered-Products_Microchip-Tech_MCP4921-E-P_Microchip-Tech-MCP4921-E-P_C640392.html)
    * Digikey: Digi-Key Part Number: [MCP4921-E/P-ND](https://www.digikey.com/en/products/detail/MCP4921-E-P/MCP4921-E-P-ND/716280)
    * Mouser: Mouser No: [579-MCP4921-E/P](https://eu.mouser.com/ProductDetail/Microchip-Technology/MCP4921-E-P?qs=%2Fha2pyFaduhJohQi%252B%252B22xS27zm5f%252BDmP7mWhwLawPEk%3D)
* 74*595 Shift Register:
    * TME: TME Symbol: [SN74HC595N](https://www.tme.eu/ro/en/details/sn74hc595n/shift-registers/texas-instruments/)
    * LCSC: LCSC Part # [C112387](https://lcsc.com/product-detail/74-Series_Wuxi-I-core-Elec-AIP74HC595-DIP_C112387.html)
    * Digikey: Digi-Key Part Number: [296-1600-5-ND](https://www.digikey.com/en/products/detail/texas-instruments/SN74HC595N/277246)
    * Mouser: Mouser No: [595-SN74HC595N](https://eu.mouser.com/ProductDetail/Texas-Instruments/SN74HC595N?qs=IEl3ej0IqwBTHkYa8XPoMQ%3D%3D)
* LM339 Comparator:
    * TME: TME Symbol: [LM339N/NOPB](https://www.tme.eu/ro/en/details/lm339n_nopb/tht-comparators/texas-instruments/)
    * LCSC: LCSC Part # [C127024](https://lcsc.com/product-detail/Analog-Comparators_UTC-Unisonic-Tech-LM339L-D14-T_C127024.html)
    * Digikey: Digi-Key Part Number: [296-39010-5-ND](https://www.digikey.com/en/products/detail/LM339N-NOPB/296-39010-5-ND/4733938)
    * Mouser: Mouser No: [926-LM339N/NOPB](https://eu.mouser.com/ProductDetail/Texas-Instruments/LM339N-NOPB?qs=%2Fha2pyFaduhbDH62uPo1TIiqGIlbAYk%252BYJOqg0GxGHZFjv5Rhi6ogA%3D%3D)
* 100nF Through Hole Ceramic Capacitors:
    * TME: TME Symbol: [CC-100N](https://www.tme.eu/ro/en/details/cc-100n/50v-tht-ceramic-capacitors/sr-passives/)
    * LCSC: LCSC Part # [C154503](https://lcsc.com/product-detail/Multilayer-Ceramic-Capacitors-MLCC-Leaded_FH-Guangdong-Fenghua-Advanced-Tech-CT4-0805Y104M500F1_C154503.html)
    * Digikey: Digi-Key Part Number: [399-4329-ND](https://www.digikey.com/en/products/detail/C322C104K5R5TA/399-4329-ND/818105)
    * Mouser: Mouser No: [80-C322C104K5R](https://eu.mouser.com/ProductDetail/KEMET/C322C104K5R5TA?qs=XvIqZs20p47gvrtGJkxvnw%3D%3D)
* 1K resistors:
    * TME variants:
      * TME Symbol: [M0.4W-1K](https://www.tme.eu/ro/en/details/m0.4w-1k/0-4w-metal-film-tht-resistors/royal-ohm/mff04ff1001a5/)
      * TME Symbol: [MF0204FTE52-1K](https://www.tme.eu/ro/en/details/mf0204fte52-1k/0-4w-metal-film-tht-resistors/yageo/mf0204fte52-1kl/)
      * TME Symbol: [MBA02040C1001FCT00](https://www.tme.eu/ro/en/details/mba02040c1001fct00/0-4w-metal-film-tht-resistors/vishay/)
      * TME Symbol: [MRS16000C1001FCT00](https://www.tme.eu/ro/en/details/mrs16000c1001fct00/0-4w-metal-film-tht-resistors/vishay/)
    * LCSC: LCSC Part # [C433503](https://lcsc.com/product-detail/Metal-Film-Resistor-TH_TyoHM-RN-1-8W-1K-F-T-B-A1_C433503.html)
    * Digikey: Digi-Key Part Number: [PPC1.00KXCT-ND](https://www.digikey.com/en/products/detail/SFR16S0001001FR500/PPC1.00KXCT-ND/594732)
    * Mouser: Mouser No: [594-SFR16S0001001FR5](https://eu.mouser.com/ProductDetail/Vishay-BC-Components/SFR16S0001001FR500?qs=%2Fha2pyFadujsUqvUkorj9sqoYQuDLwNqZF1AZuultzJ3WeA4IHI4Zh1zn%252B3DVKi1)
* 20K resistors:
    * TME variants:
      * TME Symbol: [MBA02040C2002FC100](https://www.tme.eu/ro/en/details/mba02040c2002fc100/0-4w-metal-film-tht-resistors/vishay/)
      * TME Symbol: [M0.4W-20K](https://www.tme.eu/ro/en/details/m0.4w-20k/0-4w-metal-film-tht-resistors/royal-ohm/mff04ff2002a5/)
    * LCSC: LCSC Part # [C433488](https://lcsc.com/product-detail/Metal-Film-Resistor-TH_TyoHM-RN-1-8W-20K-F-T-B-A1_C433488.html)
    * Digikey: Digi-Key Part Number: [PPC20.0KXCT-ND](https://www.digikey.com/en/products/detail/SFR16S0002002FR500/PPC20.0KXCT-ND/594752)
    * Mouser: Mouser No: [594-SFR16S0002002FR5](https://eu.mouser.com/ProductDetail/Vishay-BC-Components/SFR16S0002002FR500?qs=%2Fha2pyFadujsUqvUkorj9umgYhpPlR5mCJn3%252Blcb4g6DIeW0WKj3%252Bl6vHG2opx20)
* 4.7K resistors:
    * TME variants:
      * TME Symbol: [MBA02040C4701FCT00](https://www.tme.eu/ro/en/details/mba02040c4701fct00/0-4w-metal-film-tht-resistors/vishay/)
      * TME Symbol: [MF0204FTE52-4K7](https://www.tme.eu/ro/en/details/mf0204fte52-4k7/0-4w-metal-film-tht-resistors/yageo/mf0204fte52-4k7l/)
      * TME Symbol: [MRS16000C4701FC100](https://www.tme.eu/ro/en/details/mrs16000c4701fc100/0-4w-metal-film-tht-resistors/vishay/)
      * TME Symbol: [M0.4W-4K7](https://www.tme.eu/ro/en/details/m0.4w-4k7/0-4w-metal-film-tht-resistors/royal-ohm/mff04ff4701a5/)
    * LCSC: LCSC Part # [C433477](https://lcsc.com/product-detail/Metal-Film-Resistor-TH_TyoHM-RN-1-8W-4K7-F-T-B-A1_C433477.html)
    * Digikey: Digi-Key Part Number: [BC3275CT-ND](https://www.digikey.com/en/products/detail/MBA02040C4701FCT00/BC3275CT-ND/6138778)
    * Mouser: Mouser No: [594-5063JD4K700F5](https://eu.mouser.com/ProductDetail/Vishay-Beyschlag/MBA02040C4701FCT00?qs=%2Fha2pyFaduhdxPPbXRtwp14%252BOd3NrR4qjYAqlfO7AOn4IAkYilba3w%3D%3D)
* 100kohm resistor networks (either get the resistor networks, or individual resistors, not both):
    * TME variants:
      * TME Symbol for 2% precision resistor network (was out of stock on 15 nov. 2020): [4605X-101-104LF](https://www.tme.eu/ro/en/details/4605x-101-104lf/tht-resistor-networks/bourns/)
      * TME Symbol for 2% precision resistor network: [DR100K-4/5](https://www.tme.eu/ro/en/details/dr100k-4_5/tht-resistor-networks/royal-ohm/rnla05g0104b0e/)
    * LCSC variants:
      * LCSC Symbol for 5% precision resistor network: [C11398](https://lcsc.com/product-detail/Resistor-Networks-Arrays_FH-Guangdong-Fenghua-Advanced-Tech-A05-104JP_C11398.html)
        * ^ This one is not really recommended, too low precision, it would probably work, but better find higher precision resistor network, or use individual resistors.
      * LCSC Symbol for 2% precision resistor network (was out of stock on 15 nov. 2020): [C353644](https://lcsc.com/product-detail/Resistor-Networks-Arrays-TH_ZHUHAI-MONEC-ELEC-RAA05104G_C353644.html)
* 100kohm individual resistors (either get the resistor networks, or individual resistors, not both):
    * TME variants:
      * TME Symbol for 1% precision individual resistors: [MBA02040C1003FCT00](https://www.tme.eu/ro/en/details/mba02040c1003fct00/0-4w-metal-film-tht-resistors/vishay/)
      * TME Symbol for 1% precision individual resistors: [MF0204FTE52-100K](https://www.tme.eu/ro/en/details/mf0204fte52-100k/0-4w-metal-film-tht-resistors/yageo/mf0204fte52-100kl/)
      * TME Symbol for 1% precision individual resistors: [M0.4W-100K](https://www.tme.eu/ro/en/details/m0.4w-100k/0-4w-metal-film-tht-resistors/royal-ohm/mff04ff1003a5/)
    * LCSC Symbol for 1% precision individual resistors: [C433501](https://lcsc.com/product-detail/Metal-Film-Resistor-TH_TyoHM-RN-1-8W-100K-F-T-B-A1_C433501.html)
    * Digikey: Digi-Key Part Number: [PPC100KXCT-ND](https://www.digikey.com/en/products/detail/SFR16S0001003FR500/PPC100KXCT-ND/594692)
    * Mouser: Mouser No: [594-SFR16S0001003FR5](https://eu.mouser.com/ProductDetail/Vishay-BC-Components/SFR16S0001003FR500?qs=%2Fha2pyFadujsUqvUkorj9sqoYQuDLwNqbRrKTwOWfEmMQ5v4xEYvMk%252Bu4ls69HLw)
* M3 standoff/screw/washer:
    * TME:
        * 10mm M3 standoff: TME Symbol: [TFF-M3X10/DR113](https://www.tme.eu/ro/en/details/tff-m3x10_dr113/metal-spacers/dremec/113x10/)
        * 0.5mm height 6mm external diameter M3 washers to fine adjust spacing: TME Symbol: [B3/6/0.5/BN1976](https://www.tme.eu/ro/en/details/b3_6_0.5_bn1976/washers/bossard/m3-6-0-5-bn1976-din988/)
            * you will need to use two 0.5mm height washers, so the total height will be 10mm + 2*0.5mm = 11mm. This matches the total height of the plastic parts of the pin headers, which is 8.5mm + 2.5mm = 11mm.
        * 5mm long M3 screws: TME Symbol: [B3X5/BN2724](https://www.tme.eu/ro/en/details/b3x5_bn2724/screws/bossard/m3x5-bn2724/)
    * Digikey:
        * 11mm M3 standoff: Digi-Key Part Number: [732-10550-ND](https://www.digikey.com/en/products/detail/970110321/732-10550-ND/6174770)
        * Digi-Key Part Number: [36-9191-4-ND](https://www.digikey.com/en/products/detail/9191-4/36-9191-4-ND/4499485)
    * Mouser:
        * 11mm M3 standoff: Mouser No: [710-970110321](https://eu.mouser.com/ProductDetail/Wurth-Elektronik/970110321?qs=%2Fha2pyFadugi%252BmZ0LeMTQJUDyfnJIx0ZgF6mc8LRaC83gwEK%2F99RYw%3D%3D)
        * Mouser No: [534-9191-4](https://eu.mouser.com/ProductDetail/Keystone-Electronics/9191-4?qs=%2Fha2pyFaduhwD8HQuFOgghyidIhMmEW%252BlRhKXnRQ8hUh1auiqm602w%3D%3D)
    * Aliexpres:
      * 910pcs/set M3 Male Female Hex Brass Standoff Spacer with Pan Head Screw Nut and Washer Assortment Kit: [link](https://www.aliexpress.com/item/4001179100363.html)
* Straight Vertical 40-pin male pinheader (will need to cut these, buy at least 2 40-pin ones):
    * TME: TME Symbol: [PH1-40-UA](https://www.tme.eu/ro/en/details/ph1-40-ua/pin-headers/adam-tech/)
    * LCSC: LCSC Part # [C429959](https://lcsc.com/product-detail/Pin-Header-Female-Header_JILN-12251140CNG0S115001_C429959.html)
    * Digikey: Digi-Key Part Number: [732-5334-ND](https://www.digikey.com/en/products/detail/61304011121/732-5334-ND/4846884)
    * Mouser: Mouser No: [710-61304011121](https://eu.mouser.com/ProductDetail/Wurth-Elektronik/61304011121?qs=%2Fha2pyFaduhbwb%2FVaKS9HzW1ZRPFHPCn%2FQ4cabrOWJCnR%2FCDOZkTxA%3D%3D)
* Straight Vertical 40-pin female pinheader (will need to cut these, buy at least 2 40-pin ones):
    * TME: TME Symbol: [ZL262-40SG](https://www.tme.eu/ro/en/details/zl262-40sg/pin-headers/connfly/ds1023-1-40s21/)
    * LCSC: LCSC Part # [C429953](https://lcsc.com/product-detail/Pin-Header-Female-Header_JILN-22850140ANG1SYA01_C429953.html)
    * Digikey: Digi-Key Part Number: [HDR100IMP40F-G-V-TH-ND](https://www.digikey.com/en/products/detail/HDR100IMP40F-G-V-TH/HDR100IMP40F-G-V-TH-ND/5978200)
    * Mouser: Mouser No: [474-PRT-00115](https://eu.mouser.com/ProductDetail/SparkFun/PRT-00115?qs=%2Fha2pyFaduhW%2Fk%2FYYulWfh3Vj%2FzW2cZGQaWSLmdxaKBAnHxDvNmwlg%3D%3D)
* 90degree/right-angle 2-row 2x40-pin male pinheader (will need to cut these):
    * TME: TME Symbol: [PH2RA-80-UA](https://www.tme.eu/ro/en/details/ph2ra-80-ua/pin-headers/adam-tech/)
    * LCSC: LCSC Part # [C358715](https://lcsc.com/product-detail/Pin-Header-Female-Header_MINTRON-MTP125-240R1_C358715.html)
    * Digikey: Digi-Key Part Number: [A106438-ND](https://www.digikey.com/en/products/detail/2-826634-0/A106438-ND/2276155)
    * Mouser: Mouser No: [571-2-826634-0](https://eu.mouser.com/ProductDetail/TE-Connectivity/2-826634-0?qs=%2Fha2pyFadujVwif95ePX5VoXjOYczoe%252BxztXLQuR7DF0J24iKC70sg%3D%3D)
    * You can also use straight single-row pin headers from above, instead of 90-degree ones.
