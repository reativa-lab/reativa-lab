# Reativa

**Laboratory for Technology Recovery and Modernization**

A laboratory initiative led by Elói Rotava, a faculty member at the Federal
University of São Paulo (Unifesp), Brazil.

Reativa investigates and applies coding agents to recover and modernize legacy
devices and systems. The approach combines low-cost benches, repurposed
hardware, and remote access so that technically capable operators without
specialist firmware knowledge can delegate implementation, compilation,
deployment, and recovery from failed experiments. Operators define the goals
and assess the resulting functionality.

## Research and development areas

- Updating legacy drivers and adapting them to current operating systems.
- Recovering and modernizing unsupported firmware.
- Restoring legacy software through emulation and reproducible runtime environments.
- Recovering scientific data from abandoned or proprietary file formats.
- Maintaining compatibility with vendor binaries and abandoned interfaces.
- Wrapping obsolete binary components (codecs, vendor libraries, driver interfaces)
  so that the original, unmodified binaries run on current systems and other
  processor architectures, with explicit, independently verified fidelity.
- Building accessible benches with remote observation, deployment, and recovery.
- Documenting practical experience, recovered functionality, and limitations.

## Initial experience

The initiative builds on work involving SSV6051 wireless devices, the Netgear
R7000, the Tenda AC6, MT7628/eCos repeaters, and Amlogic NAND storage.
Software and data-format work also includes Epi Info 6 under FreeDOS/QEMU,
Bruker OPUS spectra, and Shimadzu LCD/TLM chromatography data. A manuscript
in preparation reports these experiences and the evolution of the bench.

Binary-component work covers a 1990s Windows video codec (Intel Indeo, 32- and
16-bit versions and two later generations) wrapped to run unmodified on ARM
Linux with output verified frame by frame, and a USB device vendor's Windows library that
operates real hardware on ARM systems, alone and under its original graphical
utility. Whole Windows programs using serial ports have also been run against
real adapters. A benchmark of 15 coding-agent configurations, three runs each,
measured how far agents produce such wrappers unaided when acceptance is
checked independently. A second manuscript in preparation reports this work.

## Working principles

- Work only with legitimate copies of software and equipment that the
  laboratory or its partners own and may use, and keep the licenses on record.
- Prefer the least invasive approach that works: existing compatibility layers,
  emulation and wrapping first, black-box observation next; disassembly only
  where interoperability requires it, with the reason recorded.
- Publish only what is ours: wrappers, methods, measurements and hashes. Vendor
  binaries and partners' data are never placed in public repositories.
- Agree on authorization and publication with equipment and data owners, and
  involve the university's technology-transfer and legal offices, before work
  on a partner's case begins.
- Accept results only against an oracle independent of the agent, including
  test material the agent has not seen.

## Status

The laboratory is being established. Team development, infrastructure planning,
and funding proposals are in progress. This description does not imply formal
institutional recognition or funding already awarded.

Technical materials will be selected according to confidentiality and
redistribution rights. This initial repository remains private during preparation.

## Article companion

The curated hardware/firmware case material is organized in
[legacy-firmware-study](https://github.com/reativa-lab/legacy-firmware-study).
The scope of that article is narrower than the laboratory's hardware and software remit.
