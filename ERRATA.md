# Errata

This document only describes what changes must be made to each revision for it to function correctly.
For a full list of changes, please see CHANGES.txt


## Revision 0.1.1 (Rev. 0.1.1 on silkscreen) (released 2020/nov/01)
Git hash: 9028ddaa2e20d55d37fc6f7d3809adf717919eb1  
Schematic rev. was bumped to 0.1.1, PCB file revision was forgotten at 0.0.3  
please consider only git hash or revision that is mentioned on silkscreen for accurate revision identification.  
Generated gerbers are available on github, and deskthority.

* No known electrical issues

## Third Revision (Rev. 0.0.3 on silkscreen)
Git hash: 43d1e00e14cc144690cdfa7ccc7437dce1b8cad1  
Schematic rev. was bumped to 0.0.3, PCB file revision is 0.0.3, please consider only git hash or revision that is mentioned on silkscreen for accurate revision identification.  
Generated gerbers were never publicly available for this revision, only the Kicad project.

* No known electrical issues

## Second Revision (Revision not mentioned on silkscreen)
Git hash: dcde7c1d5b266a0c9a05951c770276cc73248615  
Schematic rev. is 0.0.2, PCB file revision is 0.0.3, please consider only git hash for accurate revision identification.  
Generated gerbers were never publicly available for this revision, only the Kicad project.

* This revision has separate BIAS voltages for each group of 4 rows. If the connected keyboard uses more than 4 rows, or if if uses some rows from the left 4 and some from the right 4, then the two BIAS points must be shorted together. One pair of biasing 1K/4.7K resistors are optional.
* 10K resistor networks are optional. (But only with recent enough firmware, that enables internal pull-up resistors in the microcontroller)
* The ground strap mounting hole on the controller is not grounded.


## First Revision (Revision not mentioned on silkscreen)
Git hash: 91dc5f78a520dae1363f0ed9b2873a4988be1632  
Schematic rev. is 0.0.2, PCB file revision is 0.0.3, please consider only git hash for accurate revision identification.  
This is the first revision that was known to be built by anyone,  
Gerbers were available from Deskthority.

* MUST NOT mount 10uF capacitor
* This revision has separate BIAS voltages for each group of 4 rows. If the connected keyboard uses more than 4 rows, or if if uses some rows from the left 4 and some from the right 4, then the two BIAS points must be shorted together. One pair of biasing 1K/4.7K resistors are optional.
* 10K resistor networks are optional. (But only with recent enough firmware, that enables internal pull-up resistors in the microcontroller)