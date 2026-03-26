# Release v.1.0.0

## Tiny Tapeout IHP 26a - Initial Release

**Date:** 2026-03-25
**Process:** IHP SG13G2

### Release Contents

- `gds/TT2603.oas` - Final chip layout (OAS format) with fill and seal ring
- `netlist/tt_ihp_wrapper.nl.v` - Gate-level Verilog netlist
- `netlist/tt_ihp_wrapper.v` - Powered Verilog netlist

### Verification Status

| Check                 | Status                             |
| --------------------- | ---------------------------------- |
| DRC (KLayout)         | PASS                               |
| Metal density         | PASS                               |
| LVS (Netgen)          | PASS - "Circuits match uniquely"   |
| Gate-level simulation | PASS (test_factory_test, test_rom) |

### Design Summary

- Die: 5400 x 6450 um
- Grid: 20 x 28 tiles (560 project slots)
- Top cell: TT2603
- Built from: https://github.com/TinyTapeout/tinytapeout-ihp-26a (commit 85f4c9b)
