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
* 1pcs 1K through hole 0.25W resistor (better if subminiature type)
* 2pcs 20K through hole 0.25W resistors (better if subminiature type)
* 2pcs 4.7K through hole 0.25W resistors (better if subminiature type)
* 100kohm Resistor Networks, or Resistors, two options:
    * Option 1: 2pcs 100K 5-pin resistor networks
        * (only 1pcs is really needed if the controller will only ever be used on <= 4-row keyboards, such as non-Displaywriter standard beamspring keyboards)
    * Option 2: 8pcs 100K through hole 0.25W resistors (these are the resistors marked with ALT on the PCB)  (better if subminiature type)
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
    * You can buy pin pinheaders with more pins then necessary, and cut them. You can use two 1-row pin headers to make a vertical Solenoid connector.

## Notes regarding other revisions:

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
        * Ask drakcruix about bad amazon seller
        * Don't buy Proton-C, because non-AVR cores are not supported by my firmware. [link](https://qmk.fm/proton-c/)
        * *Maybe* do not buy Pro Micro drop-in replacements, that use DFU bootloader. These can be supported, but only if you compile your firmware locally. Otherwise many bootloader entry methods will not work. You also have the option of replacing the bootloader on one of these with ISP programming. Example: [Elite-C](https://keeb.io/products/elite-c-low-profile-version-usb-c-pro-micro-replacement-atmega32u4)

* Card Edge Connector (For beamsprings/displaywriters)
    * You can use the original connector, desoldered from the original controller
    * Please read this thread: [link](https://deskthority.net/viewtopic.php?f=7&t=24511&p=473024&hilit=tightness#p473024)

* MCP4921-E/P DAC:
    * TME: TME Symbol: MCP4921-E/P [link](https://www.tme.eu/ro/en/details/mcp4921-e_p/d-a-converters-integrated-circuits/microchip-technology/)

* 74*595 Shift Register:
    * TME: TME Symbol: SN74HC595N [link](https://www.tme.eu/ro/en/details/sn74hc595n/shift-registers/texas-instruments/)

* LM339 Comparator:
    * TME: TME Symbol: LM339N/NOPB [link](https://www.tme.eu/ro/en/details/lm339n_nopb/tht-comparators/texas-instruments/)

* 100nF Through Hole Ceramic Capacitors:
    * TME: TME Symbol: CC-100N [link](https://www.tme.eu/ro/en/details/cc-100n/50v-tht-ceramic-capacitors/sr-passives/)
* 1K resistors:
    * TME: TME Symbol: 1/4WS1K [link](https://www.tme.eu/ro/en/details/1_4ws1k/1-4w-subminiature-carbon-tht-resistors/royal-ohm/cfr0s4j0102a50/)
* 20K resistors:
    * TME: TME Symbol: 1/4WS20K [link](https://www.tme.eu/ro/en/details/1_4ws20k/1-4w-subminiature-carbon-tht-resistors/royal-ohm/cfr0s4j0203a50/)
* 4.7K resistors:
    * TME: TME Symbol: 1/4WS4K7 [link](https://www.tme.eu/ro/en/details/1_4ws4k7/1-4w-subminiature-carbon-tht-resistors/royal-ohm/cfr0s4j0472a50/)
* 100kohm resistor networks:
    * TME: TME Symbol: 4605X-101-104LF [link](https://www.tme.eu/ro/en/details/4605x-101-104lf/tht-resistor-networks/bourns/)
* 100kohm individual resistors
    * TME: TME Symbol: 1/4WS100K [link](https://www.tme.eu/ro/en/details/1_4ws100k/1-4w-subminiature-carbon-tht-resistors/royal-ohm/cfr0s4j0104a50/)
* M3 standoff/screw/washer:
    * TME:
        * 10mm M3 standoff: TME Symbol: TFF-M3X10/DR113 [link](https://www.tme.eu/ro/en/details/tff-m3x10_dr113/metal-spacers/dremec/113x10/)
        * 0.5mm height 6mm external diameter M3 washers to fine adjust spacing: TME Symbol: B3/6/0.5/BN1976 [link](https://www.tme.eu/ro/en/details/b3_6_0.5_bn1976/washers/bossard/m3-6-0-5-bn1976-din988/)
            * you will need to use two 0.5mm height washers, so the total height will be 10mm + 2*0.5mm = 11mm. This matches the total height of the plastic parts of the pin headers, which is 8.5mm + 2.5mm = 11mm.
        * 5mm long M3 screws: TME Symbol: B3X5/BN2724 [link](https://www.tme.eu/ro/en/details/b3x5_bn2724/screws/bossard/m3x5-bn2724/)
* Straight Vertical 40-pin male pinheader (will need to cut these):
    * TME: TME Symbol: PH1-40-UA [link](https://www.tme.eu/ro/en/details/ph1-40-ua/pin-headers/adam-tech/)
* Straight Vertical 40-pin female pinheader (will need to cut these):
    * TME: TME Symbol: ZL262-40SG [link](https://www.tme.eu/ro/en/details/zl262-40sg/pin-headers/connfly/ds1023-1-40s21/)
* 90degree 2-row 2x40-pin male pinheader (will need to cut these):
    * TME: TME Symbol: PH2RA-80-UA [link](https://www.tme.eu/ro/en/details/ph2ra-80-ua/pin-headers/adam-tech/)


