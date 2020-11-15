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


## Sources

All links in this document may become out of date. They may become unavailable, or price changes may make them not be good options anymore. Please do your own research before committing to buy.

* Pro Micro 5V/16MHz
    * Sparkfun Pro Micro: [link](https://www.sparkfun.com/products/12640)
        * More on the pricier side, but Sparkfun designed the Pro Micro, so they are probably the highest quality source.
        * They also have many distributors: [link](https://www.sparkfun.com/distributors)
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
    * Please read this thread: [link](https://deskthority.net/viewtopic.php?f=7&t=24511&p=473024&hilit=tightness#p473024)
* MCP4921-E/P DAC:
    * TME: TME Symbol: MCP4921-E/P [link](https://www.tme.eu/ro/en/details/mcp4921-e_p/d-a-converters-integrated-circuits/microchip-technology/)
    * LCSC: Last checked it wasn't available in a DIP package. 15 nov. 2020. LCSC Symbol: C640392 [link](https://lcsc.com/product-detail/Pre-ordered-Products_Microchip-Tech_MCP4921-E-P_Microchip-Tech-MCP4921-E-P_C640392.html)
* 74*595 Shift Register:
    * TME: TME Symbol: SN74HC595N [link](https://www.tme.eu/ro/en/details/sn74hc595n/shift-registers/texas-instruments/)
    * LCSC: LCSC Symbol: C112387 [link](https://lcsc.com/product-detail/74-Series_Wuxi-I-core-Elec-AIP74HC595-DIP_C112387.html)
* LM339 Comparator:
    * TME: TME Symbol: LM339N/NOPB [link](https://www.tme.eu/ro/en/details/lm339n_nopb/tht-comparators/texas-instruments/)
    * LCSC: LCSC Symbol: C127024 [link](https://lcsc.com/product-detail/Analog-Comparators_UTC-Unisonic-Tech-LM339L-D14-T_C127024.html)
* 100nF Through Hole Ceramic Capacitors:
    * TME: TME Symbol: CC-100N [link](https://www.tme.eu/ro/en/details/cc-100n/50v-tht-ceramic-capacitors/sr-passives/)
    * LCSC: LCSC Symbol: C154503 [link](https://lcsc.com/product-detail/Multilayer-Ceramic-Capacitors-MLCC-Leaded_FH-Guangdong-Fenghua-Advanced-Tech-CT4-0805Y104M500F1_C154503.html)
* 1K resistors:
    * TME variants:
      * TME Symbol: M0.4W-1K [link](https://www.tme.eu/ro/en/details/m0.4w-1k/0-4w-metal-film-tht-resistors/royal-ohm/mff04ff1001a5/)
      * TME Symbol: MF0204FTE52-1K [link](https://www.tme.eu/ro/en/details/mf0204fte52-1k/0-4w-metal-film-tht-resistors/yageo/mf0204fte52-1kl/)
      * TME Symbol: MBA02040C1001FCT00 [link](https://www.tme.eu/ro/en/details/mba02040c1001fct00/0-4w-metal-film-tht-resistors/vishay/)
      * TME Symbol: MRS16000C1001FCT00 [link](https://www.tme.eu/ro/en/details/mrs16000c1001fct00/0-4w-metal-film-tht-resistors/vishay/)
    * LCSC: LCSC Symbol: C433503 [link](https://lcsc.com/product-detail/Metal-Film-Resistor-TH_TyoHM-RN-1-8W-1K-F-T-B-A1_C433503.html)
* 20K resistors:
    * TME variants:
      * TME Symbol: MBA02040C2002FC100 [link](https://www.tme.eu/ro/en/details/mba02040c2002fc100/0-4w-metal-film-tht-resistors/vishay/)
      * TME Symbol: M0.4W-20K [link](https://www.tme.eu/ro/en/details/m0.4w-20k/0-4w-metal-film-tht-resistors/royal-ohm/mff04ff2002a5/)
    * LCSC: LCSC Symbol: C433488 [link](https://lcsc.com/product-detail/Metal-Film-Resistor-TH_TyoHM-RN-1-8W-20K-F-T-B-A1_C433488.html)
* 4.7K resistors:
    * TME variants:
      * TME Symbol: MBA02040C4701FCT00 [link](https://www.tme.eu/ro/en/details/mba02040c4701fct00/0-4w-metal-film-tht-resistors/vishay/)
      * TME Symbol: MF0204FTE52-4K7 [link](https://www.tme.eu/ro/en/details/mf0204fte52-4k7/0-4w-metal-film-tht-resistors/yageo/mf0204fte52-4k7l/)
      * TME Symbol: MRS16000C4701FC100 [link](https://www.tme.eu/ro/en/details/mrs16000c4701fc100/0-4w-metal-film-tht-resistors/vishay/)
      * TME Symbol: M0.4W-4K7 [link](https://www.tme.eu/ro/en/details/m0.4w-4k7/0-4w-metal-film-tht-resistors/royal-ohm/mff04ff4701a5/)
    * LCSC: LCSC Symbol: C433477 [link](https://lcsc.com/product-detail/Metal-Film-Resistor-TH_TyoHM-RN-1-8W-4K7-F-T-B-A1_C433477.html)
* 100kohm resistor networks (either get the resistor networks, or individual resistors, not both):
    * TME variants:
      * TME Symbol for 2% precision resistor network (was out of stock on 15 nov. 2020): 4605X-101-104LF [link](https://www.tme.eu/ro/en/details/4605x-101-104lf/tht-resistor-networks/bourns/)
      * TME Symbol for 2% precision resistor network: DR100K-4/5 [link](https://www.tme.eu/ro/en/details/dr100k-4_5/tht-resistor-networks/royal-ohm/rnla05g0104b0e/)
    * LCSC variants:
      * LCSC Symbol for 5% precision resistor network: C11398 [link](https://lcsc.com/product-detail/Resistor-Networks-Arrays_FH-Guangdong-Fenghua-Advanced-Tech-A05-104JP_C11398.html)
        * ^ This one is not really recommended, too low precision, it would probably work, but better find higher precision resistor network, or use individual resistors.
      * LCSC Symbol for 2% precision resistor network (was out of stock on 15 nov. 2020): C353644 [link](https://lcsc.com/product-detail/Resistor-Networks-Arrays-TH_ZHUHAI-MONEC-ELEC-RAA05104G_C353644.html)
* 100kohm individual resistors (either get the resistor networks, or individual resistors, not both):
    * TME variants:
      * TME Symbol for 1% precision individual resistors: MBA02040C1003FCT00 [link](https://www.tme.eu/ro/en/details/mba02040c1003fct00/0-4w-metal-film-tht-resistors/vishay/)
      * TME Symbol for 1% precision individual resistors: MF0204FTE52-100K [link](https://www.tme.eu/ro/en/details/mf0204fte52-100k/0-4w-metal-film-tht-resistors/yageo/mf0204fte52-100kl/)
      * TME Symbol for 1% precision individual resistors: M0.4W-100K [link](https://www.tme.eu/ro/en/details/m0.4w-100k/0-4w-metal-film-tht-resistors/royal-ohm/mff04ff1003a5/)
    * LCSC Symbol for 1% precision individual resistors: C433501 [link](https://lcsc.com/product-detail/Metal-Film-Resistor-TH_TyoHM-RN-1-8W-100K-F-T-B-A1_C433501.html)
* M3 standoff/screw/washer:
    * TME:
        * 10mm M3 standoff: TME Symbol: TFF-M3X10/DR113 [link](https://www.tme.eu/ro/en/details/tff-m3x10_dr113/metal-spacers/dremec/113x10/)
        * 0.5mm height 6mm external diameter M3 washers to fine adjust spacing: TME Symbol: B3/6/0.5/BN1976 [link](https://www.tme.eu/ro/en/details/b3_6_0.5_bn1976/washers/bossard/m3-6-0-5-bn1976-din988/)
            * you will need to use two 0.5mm height washers, so the total height will be 10mm + 2*0.5mm = 11mm. This matches the total height of the plastic parts of the pin headers, which is 8.5mm + 2.5mm = 11mm.
        * 5mm long M3 screws: TME Symbol: B3X5/BN2724 [link](https://www.tme.eu/ro/en/details/b3x5_bn2724/screws/bossard/m3x5-bn2724/)
    * Aliexpres:
      * 910pcs/set M3 Male Female Hex Brass Standoff Spacer with Pan Head Screw Nut and Washer Assortment Kit: [link](https://www.aliexpress.com/item/4001179100363.html)
* Straight Vertical 40-pin male pinheader (will need to cut these):
    * TME: TME Symbol: PH1-40-UA [link](https://www.tme.eu/ro/en/details/ph1-40-ua/pin-headers/adam-tech/)
    * LCSC: LCSC Symbol: C429959 [link](https://lcsc.com/product-detail/Pin-Header-Female-Header_JILN-12251140CNG0S115001_C429959.html)
* Straight Vertical 40-pin female pinheader (will need to cut these):
    * TME: TME Symbol: ZL262-40SG [link](https://www.tme.eu/ro/en/details/zl262-40sg/pin-headers/connfly/ds1023-1-40s21/)
    * LCSC: LCSC Symbol: C429953 [link](https://lcsc.com/product-detail/Pin-Header-Female-Header_JILN-22850140ANG1SYA01_C429953.html)
* 90degree/right-angle 2-row 2x40-pin male pinheader (will need to cut these):
    * TME: TME Symbol: PH2RA-80-UA [link](https://www.tme.eu/ro/en/details/ph2ra-80-ua/pin-headers/adam-tech/)
    * LCSC: LCSC Symbol: C358715 [link](https://lcsc.com/product-detail/Pin-Header-Female-Header_MINTRON-MTP125-240R1_C358715.html)
    * You can also use straight single-row pin headers from above, instead of 90-degree ones.


