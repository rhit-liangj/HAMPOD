# HAMPOD: Modern Assistive Controller for Amateur Radio

## Overview

HAMPOD is an assistive technology project designed to enable blind and visually impaired amateur radio operators to independently configure and operate modern transceivers. This repository contains a **work‑in‑progress C‑based software and firmware stack** intended to run on commodity Linux hardware (e.g., Raspberry Pi–class systems) and interface with supported radios via standard control libraries.

This codebase represents an **active development and research platform**, not a finished or production‑ready system.

---

## Project Status

**Current state:**

* Functional build environment on Linux / Raspberry Pi
* Executable firmware components

---

## Repository Structure

```
HAMPOD/
├── Firmware/            # Low‑level firmware and hardware‑facing logic
├── Software/            # Core application logic (state machine, control flow)
├── Software2/           # Experimental or extended software components
├── Documentation/       # Technical notes and design references
├── *.c                  # Standalone or test C source files
├── *.h                  # Header files
├── *.sh                 # Setup and startup scripts
```

### Firmware

The `Firmware/` directory contains C code intended to interface with hardware‑level components and provide low‑level services to the higher‑level software layer. At present, this includes baseline initialization and test functionality.

### Software

The `Software/` and `Software2/` directories contain the main application logic, including state handling, radio command abstraction, and user interaction logic. These components are under active revision and are not yet fully integrated.

### Scripts

Shell scripts included in the repository assist with installation, setup, or startup on supported Linux platforms. These scripts may require modification depending on the target hardware and operating system.

---

## Build Requirements

### Operating System

* Linux (tested on Raspberry Pi OS)

### Required Tools

```bash
sudo apt update
sudo apt install build-essential git
```

### Optional / Project‑Specific Dependencies

Depending on which components are being built or tested, additional libraries may be required, such as:

* Hamlib (radio control)
* ALSA (audio output)
* Text‑to‑speech engines

Exact dependencies may evolve as the project matures.

---

## Building the Code

### Firmware

```bash
cd Firmware
make
# or, if no Makefile is present:
gcc *.c -o firmware
```

### Software

```bash
cd Software
make
# or:
gcc *.c -o hampod_app
```

The resulting executables are intended to be run from the command line during development and testing.

---

## Running

After building:

```bash
./firmware
./hampod_app
```

At this stage, output is primarily diagnostic and intended to verify correct execution rather than provide a complete user experience.

---

## Development Philosophy

This codebase prioritizes:

* **Incremental validation** (small, testable components)
* **Hardware independence where possible**
* **Accessibility‑driven design decisions**
* **Maintainability for future contributors**

Refactoring, modularization, and subsystem isolation are expected parts of ongoing work.

---

## Intended Future Work

Planned areas of development include:

* Modular radio support
* Improved audio latency and customization
* Robust error handling and diagnostics
* Clear configuration and installation workflows
* Expanded user testing with visually impaired operators

---

## Disclaimer

This repository is **not a finished assistive device** and should not be deployed for real‑world use without further development, testing, and validation.

---
