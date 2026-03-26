# Tiny Tapeout IHP 26a - IHP Open-Silicon MPW Submission

Multi-Project Carrier (MPC) chip for the IHP SG13G2 Open-Silicon MPW March 2026 run.

## Overview

Tiny Tapeout IHP 26a is an educational ASIC that aggregates 283 user-submitted
chip designs onto a single die manufactured on the **IHP SG13G2** 130nm BiCMOS process.

- **Category:** Mixed-Signal
- **Subcategory:** Multi Project Carrier (MPC)
- **Process:** IHP SG13G2
- **Die size:** 5400 x 6450 um
- **Top cell:** `TT2603`
- **Grid:** 20 x 28 tiles (560 user project slots)
- **License:** Apache-2.0

## Design Source

The chip design source is at: https://github.com/TinyTapeout/tinytapeout-ihp-26a

The design flow uses:
- **LibreLane** for RTL-to-GDS compilation
- **Yosys** for synthesis
- **OpenROAD** for place and route
- **Magic** for SPICE extraction
- **Netgen** for LVS verification
- **KLayout** for DRC and GDS streamout

## Physical Verification

LVS was verified during the chip build using Netgen (SPICE extracted via Magic
compared against the Verilog netlist). Result: `Circuits match uniquely.`

DRC is verified via GitHub Actions using the IHP SG13G2 PDK scripts.

## Links

- Source repository: https://github.com/TinyTapeout/tinytapeout-ihp-26a
- Tiny Tapeout: https://tinytapeout.com
- IHP SG13G2 PDK: https://github.com/IHP-GmbH/IHP-Open-PDK
