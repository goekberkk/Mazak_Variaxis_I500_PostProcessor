# INCOMPLETE Mazak Variaxis I- 500 NX Postprocessor

Work-in-progress Siemens NX CAM postprocessor project for Mazak Variaxis 500 / MAZATROL Matrix EIA/ISO output.

This project is focused on developing and validating a custom 5-axis postprocessor for Siemens NX CAM. The goal is to generate safe, predictable, and Mazak-compatible NC output for 3-axis milling, indexed 3+2 machining, and simultaneous 5-axis machining.

> **Status:** This project is not finished and is not production-ready.  
> Generated NC code must be verified carefully before any real machine use.

---

## Project Purpose

The purpose of this project is to adapt a Siemens NX 5-axis milling postprocessor structure to the Mazak Variaxis I-500.

The postprocessor is intended to handle:

- Mazak MAZATROL Matrix EIA/ISO formatting
- 3-axis milling output
- Indexed 3+2 positioning
- Simultaneous 5-axis motion
- A/C rotary-axis output
- G68.2 inclined-plane machining logic
- G53.1 rotary-axis alignment
- G43 / G43.4 tool length and tool tip control behavior
- Tool changes and operation headers
- Fixed drilling cycles
- Cutter compensation formatting
- Safe retract, home, and reindex sequences

The main goal is not only to output valid G-code, but to make the output restart-safe, controller-compatible, and machine-safe.

---

## Development Method

### 1. Base Logic

The starting point is the logic and structure of a Fanuc-style Siemens NX 5-axis mill postprocessor.

This base is used for:

- NX MOM event structure
- TCL procedure organization
- Motion event handling
- Rotary-axis logic flow
- General postprocessor architecture

### 2. Mazak Adaptation

The Fanuc-style base logic is adapted for Mazak Variaxis I-500 behavior using private Mazak reference documentation.

The main private reference used during development is:

- `Mazak Programming Manual EIA/ISO`

This reference is used to understand Mazak-specific behavior such as inclined-plane machining, tool tip point control, rotary-axis positioning, G-code rules, and controller limitations.

# Disclaimer

This project is provided for development and research purposes only.

It is not an official Siemens, Mazak, or Yamazaki Mazak product.

Use it at your own risk. All NC output must be verified before use on any CNC machine.
