# ComfyFPGA – Roadmap

ComfyFPGA is a node-based, vendor-agnostic FPGA workflow engine and automation UI focused on reproducible builds, verification, hardware bring-up, and research-grade experimentation.

This project grew out of practical, multi-vendor FPGA and SoC workflows (including simulation, regression, and fault-tolerant system research) and is designed to scale from quick local experiments to large automated CI and test campaigns.

---

## 0.1.0 – FPGA toolchain runners

Core orchestration and execution layer for FPGA tools.

- CLI and directory / workspace nodes
- AMD Vivado runner
- Intel Quartus runner (including MAX 10)
- Microchip Libero runner
- Lattice ECP runner (Radiant / Diamond)
- Lattice CertusPro / Avant runner
- Efinix Efinity runner
- Cologne Chip GateMate runner
- Open-source flow (Yosys / nextpnr / OpenFPGALoader)
- Gowin runner
- Demo design executed across all supported toolchains

### Additional capabilities
- Tool version detection and locking
- Per-node environment definition (PATH, LM_LICENSE_FILE, license servers, etc.)
- Structured tool log parsing (errors, warnings, messages as node outputs)
- Tool installation / health-check nodes
- Vendor IP catalog cache and synchronization nodes

---

## 0.2.0 – Source and IP generation

- Improved directory, repository and Git nodes
- AMD IP generation nodes
- Intel Quartus IP generation nodes
- Microchip IP generation nodes
- LiteX integration
- GRLIB integration
- Lattice IP generation nodes
- Other third-party IP generators

### IP search and discovery
- IP search nodes for:
  - local IP repositories and monorepos
  - vendor IP catalogs (Vivado, Quartus, Libero, etc.)
  - open-source IP indexes (FuseSoC, LiteX ecosystem, community catalogs)
- IP metadata extraction and normalization
  - name, version, vendor, license
  - language (VHDL/Verilog/SystemVerilog)
  - supported devices and toolchains
  - interfaces (AXI, AXI-Stream, Avalon, Wishbone, CSR, etc.)
  - parameters / generics
- IP compatibility and filtering
  - device family
  - toolchain support
  - interface type
  - license constraints
- IP instantiation nodes
  - wrapper and stub generation
  - tool-specific glue (Tcl, QSF, SDC, XDC fragments)
  - dependency and include-path manifests

### Additional capabilities
- IP parameter sweep nodes
- IP regeneration fingerprinting and cache control
- IP output manifest generation
- Automatic wrapper and top-level integration helpers

---

## 0.3.0 – Simulation and verification

- Cocotb integration
- Open-source simulators (Verilator, Icarus, etc.)
- Vendor simulators
- Python golden-model nodes
- Simulation regression and batch execution

### Additional capabilities
- Coverage collection and reporting hooks
- Waveform post-processing nodes
- Assertion and failure extraction
- Test-vector and stimulus generators
- Failure triage and clustering nodes

---

## 0.4.0 – Hardware bring-up and debug

- Programming and flashing nodes
- Python hardware interface nodes
  - UART, SPI, I2C, GPIO, Ethernet, PCIe, USB, etc.
- Internal JTAG and debug bridge nodes
- Hardware regression testing
- Partial reconfiguration block testing

### Additional capabilities
- Board abstraction layer
  - board, programmer, cable, target device, voltage rails and clocks
- Clock and reset validation nodes
- Power-on sequencing verification
- Serial console capture and pattern-matching nodes
- Runtime register access nodes
  - AXI-Lite, Wishbone, CSR, memory-mapped interfaces

---

## 0.5.0 – Software build and system flows

- Generic Make and CMake nodes
- Software library and linker stages
- Software loading and deployment to FPGA targets
- OpenOCD, GDB and debug flows
- Yocto integration
- Buildroot integration

### Additional capabilities
- Device-tree generation nodes
- BSP generation nodes
- Root filesystem composition and overlay nodes
- Firmware and boot-image packaging helpers

---

## 0.6.0 – Containers and reproducibility

- Docker images per vendor toolchain
- Toolchain isolation and sandboxing
- Portable and shareable project definitions

### Additional capabilities
- Build provenance reports
  - tool versions, OS, container hashes, git revisions
- Exportable rebuild recipes
- CI pipeline export (GitHub Actions, GitLab CI, etc.)

---

## 0.7.0 – Utilities and project hygiene

- CRC, hash and fingerprint nodes
- Build snapshots and artifact capture
- Artifact versioning
- Cache inspection and visualization
- Artifact and result diff tools

### Additional capabilities
- Bitstream structural diff hooks (where supported)
- Netlist diff hooks
- Constraint diff nodes
- Timing and utilization report diff nodes

---

## 0.8.0 – AI assistance

- Flow inspection and explanation
- Failure diagnosis assistance
- Node and flow suggestions
- Parameter and constraint hints

### Practical AI features
- Tool log summarization
- Flow linting and sanity checks
- “Why did this node rerun?” explanations
- Timing and constraint hinting

---

## 0.9.0 – Other Idea

- Board support (Use Board files/ LitexBoards)
- User Documenation
- Additional Smart Reports (cross Vendor/ IP)
- Fault Injection for SEU Emulation
- Integrat other tools (GRMON, OpalKelly FrontPanel, ETC)

---

## 1.0.0 – Full Release?

- Python API for custom nodes
- Tool adapter and runner templates
