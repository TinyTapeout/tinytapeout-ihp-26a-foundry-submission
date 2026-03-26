# Tiny Tapeout IHP 26a - Datasheet

## General Description

Tiny Tapeout IHP 26a (TTIHP26a) is a multi-project carrier chip fabricated on the
IHP SG13G2 130nm BiCMOS process. It aggregates 283 independently designed digital,
analog, and mixed-signal user projects onto a single die using a multiplexer
architecture.

## Key Specifications

| Parameter      | Value                              |
| -------------- | ---------------------------------- |
| Process        | IHP SG13G2 (130nm BiCMOS)          |
| Die size       | 5400 x 6450 um                     |
| Tile grid      | 20 x 28 (560 tiles)                |
| Top cell       | TT2603                             |ß
| Supply voltage | 1.2V (digital), 3.3V (I/O, analog) |
| Package        | QFN64                              |

## Architecture

The chip uses a hierarchical multiplexer architecture:

- **tt_ctrl** - Address controller with active-low active select chain
- **tt_mux** - Multiplexer array connecting project I/Os via address selection
- **tt_top** (tt_ihp_wrapper) - Top-level wrapper with padring

User projects are selected by writing an address to the control interface. The
selected project's I/Os are connected to the chip's external pins.

## Pin Description

The chip has the following functional pin groups:

- `clk` - User clock
- `rst_n` - User reset (active low)
- `ui[7:0]` - User input pins
- `uo[7:0]` - User output pins
- `uio[7:0]` - Bidirectional user I/O
- `ctrl_sel_rst_n` - Selection reset (active low)
- `ctrl_sel_inc` - Selection increment
- `ctrl_ena` - Control enable

## Design Flow

Built using the LibreLane open-source RTL-to-GDS flow with:

- Yosys for synthesis
- OpenROAD for place and route
- Custom Python scripts for multiplexer routing
- Magic for parasitic extraction
- Netgen for LVS verification
- KLayout for DRC and GDS generation
