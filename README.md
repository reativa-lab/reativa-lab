# Reativa

**Laboratory for Legacy Research Equipment and Data Recovery**  
*Laboratório de Recuperação de Equipamentos de Pesquisa e Dados Científicos Legados*

An academic laboratory initiative led by Prof. Elói Rotava at the Federal University of São Paulo (Unifesp), Brazil.

---

## Mission and Motivation

Scientific instruments—spectrometers, chromatographs, analytical sensors, acquisition interfaces, and specialized controllers—often remain physically functional and calibrated for decades, while the computing layers required to operate them become obsolete much sooner. When a vendor discontinues Windows 9x/XP/7 drivers, distributes control logic only as closed binary libraries (DLLs), abandons embedded firmware, or locks measurements inside undocumented file formats, laboratories face *functional obsolescence*: working equipment is sidelined or tied to failing, unmaintainable computers, and historical experimental records become inaccessible.

**Reativa** investigates and develops engineering methods to restore the operational usability of legacy research equipment and scientific data on contemporary, maintainable platforms. By combining non-invasive compatibility layers, binary wrapping, and instrumented hardware-in-the-loop benches with supervised AI coding agents, the laboratory aims to make bespoke recovery of orphaned scientific infrastructure technically rigorous and economically viable for public research institutions.

---

## Technical Lines of Work

1. **Instrument Interfaces and Driver Adaptation**  
   Restoring communication with orphaned laboratory hardware (USB, serial, and bus bridges, acquisition modules, and embedded controllers) on current Linux systems through kernel driver porting, ABI translation layers, and user-space protocol bridges.

2. **Vendor Binary and Control Software Wrapping**  
   Running unmodified 16-bit and 32-bit proprietary vendor libraries, drivers, and calibration utilities on contemporary operating systems and processor architectures (including x86-64 and ARM Linux). Rather than maintaining full legacy operating systems on the bench, thin host wrappers supply only the imported OS and driver calls (`DeviceIoControl`, USB control transfers, serial I/O) required to operate the instrument or decode its output.

3. **Scientific Data and Proprietary Format Recovery**  
   Extracting, documenting, and converting experimental records from abandoned or undocumented instrument formats into open scientific standards, as well as maintaining reproducible runtime environments for legacy acquisition and statistical software.

4. **Embedded Firmware and Fault-Tolerant Recovery Benches**  
   Modernizing embedded controllers, telemetry interfaces, and storage subsystems using low-cost, remotely observable hardware-in-the-loop benches equipped with out-of-band serial consoles, network boot, and automated power cycling so failed interventions recover safely.

5. **Verifiable Agent-Assisted Recovery Methodology**  
   Studying how coding agents can reduce the cost of low-level software archaeology and driver adaptation while guaranteeing scientific reliability. In Reativa's workflow, human researchers define operational goals, safety boundaries, and independent acceptance oracles, while routine protocol tracing, wrapper implementation, and cross-compilation are delegated and audited automatically.

---

## Completed Foundation and Methodological Testbeds

Before taking on external multi-user instrumentation, the laboratory's methods and verification protocols were developed and stress-tested across representative scientific formats, vendor hardware libraries, and embedded testbeds:

- **Scientific Data Formats and Legacy Research Software**  
  Recovery and conversion of Bruker OPUS infrared spectroscopy records and Shimadzu LCD/TLM liquid chromatography datasets into open interchange formats (`mzXML`/`mzML`), alongside reproducible execution workflows for legacy epidemiological software (Epi Info 6 under FreeDOS/QEMU).

- **Vendor Hardware Libraries and Binary Component Wrapping**  
  Execution of unmodified Windows binary components on 64-bit and 32-bit ARM Linux with independently verified fidelity. Work includes wrapping a USB bridge vendor's configuration library (`CP210xManufacturing.dll`, 2008) and running its original Windows graphical utility against real hardware via translated Linux USB control transfers; running legacy Windows serial-communication binaries against physical adapters; and wrapping 1990s 16-bit and 32-bit binary decoders (Intel Indeo 3, 4.1, and 5.0) with frame-exact verification across 5,085 frames. The wrapped binary also served as an executable oracle to bring an open-source implementation into byte-for-byte agreement. A 45-run benchmark across 15 coding-agent configurations quantified agent reliability and demonstrated why held-out test material and independent oracles are mandatory.

- **Remotely Recoverable Embedded Benches**  
  Consolidation of a fault-tolerant hardware-in-the-loop bench—combining out-of-band LAN-accessible serial consoles, remote power switching, bootloader recovery, and isolated reference networks—validated across legacy wireless, controller, and raw NAND storage targets (SSV6051, Netgear R7000, Tenda AC6, MT7628/eCos, and Amlogic NAND).

Manuscripts reporting the hardware-in-the-loop recovery bench ([legacy-firmware-study](https://github.com/reativa-lab/legacy-firmware-study)) and the binary-wrapping methodology and agent benchmark are currently in preparation.

---

## Governance, Verification, and Compliance Principles

- **Legitimate Scope and Provenance:** Interventions are performed exclusively on equipment, software, and datasets legitimately owned by the university or authorized partner laboratories, with provenance and licensing documented on record.
- **Least-Invasive Technical Path:** Existing compatibility layers, emulation, protocol translation, and external binary wrapping are prioritized so that original vendor binaries and instrument calibration remain unmodified. Disassembly is restricted to what is strictly necessary for interoperability and is documented.
- **Verification Against an Independent Oracle:** No recovered driver, wrapper, or format converter is accepted based on an agent's self-assessment. Acceptance requires validation against an independent physical or reference oracle (hardware state reported by the host OS, reference platform execution, or cryptographic output hashes) using held-out test material not exposed during development.
- **Clean-Room Publication:** Public repositories contain only original wrappers, compatibility source code, protocol documentation, benchmark measurements, and verification hashes. Proprietary vendor binaries, firmware images, and confidential partner data are never placed in public repositories.
- **Institutional Alignment:** Work on partner laboratories' equipment or data begins only after formal agreement on authorization, safety, and publication with equipment custodians, in coordination with the university's technology-transfer and legal offices.

---

## Institutional Status

Reativa is a laboratory initiative in establishment at Unifesp. Team structure, partner intake procedures, physical bench allocation, and research funding proposals are currently under development. This public overview presents the initiative's technical scope and methodology and does not imply formal institutional accreditation or funding already awarded.
