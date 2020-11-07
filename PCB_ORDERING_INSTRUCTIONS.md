# PCB Ordering Instructions

## JLCPCB

* Issues with parsing the gerbers
    * Sometimes the gerber parsing servers are overloaded, and it will not parse immediately the gerber you uploaded. If this happens, you can still submit the order, but since board dimentions are not auto-calculated, the calculated price will be wrong, and that means that they will likely ask for an additional payment later on. If you want to avoid this, after uploading your gerbers, go to [file manager](https://cart.jlcpcb.com/fileManager), wait a little and refresh the page, until you see a thumbnail of the uploaded board, and then click the yellow "Quote" button. This time the PCB will load correctly.
* "Different Designs = 4"
    * JLCPCB policy considers each daughterboard a different design, see here: https://jlcpcb.com//quote/pcbOrderFaq/Different%20Design%20in%20Panel
    * They will "usually charge more" for this.
    * If when ordering, you select Different Designs: 4, they will always charge more, since price is autmoatically calculated. If you leave "Different Designs: 1", they might honor the order, they might put a hold on the fabrication and ask for additional payment, or they might modify the design of the breakoff mousebites, to make it easier for them to handle.
    * You can always generate new gerbers, with unneeded daughterboard removed.
* "Remove Order Number = Specify Location"
    * JLCPCB puts order numbers on the PCB silkscreen for tracking purposes. Asking them to remove this costs more, because it's harder to track the PCB. Specifying the location of this number doesn't cost more.
    * The latest revisions of the TH have the magic "JLCJLCJLCJLC" string underneath where the Pro Micro will go, so it's not an eyesore. For JLCPCB to make use of this, you have to specify "Remove Order Number = Specify Location". Otherwise they might not notice, and you will see the order number pop up somewhere else.

## Other PCB manufacturers

* You may want to remove the magic "JLCJLCJLCJLC" string from underneath the Pro Micro, if you are bothered by it, before ordering.
