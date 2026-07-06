<!-- SPDX-FileCopyrightText: 2026 Deep AI, Inc. -->
# LNP64

**A 64-bit instruction set architecture for isolated, accelerated, and analyzable systems.**

Mainstream CPU architectures still carry assumptions from systems built around a single trusted
operating system and a small number of local programs. Modern deployments run many mutually
distrusting workloads on each machine, coordinate large accelerator pools, and rely on software
mitigations for properties the hardware does not directly provide.

LNP64 is a clean 64-bit architecture designed around those requirements.

*For the opportunity and the timing, see [LNP64: The Post-Legacy Computing Platform](WHY.md).*

## The design goals

- **Low-cost isolation.** Sandboxes, containers, and virtual machines are first-class hardware
  constructs, cheap enough to assign to individual plugins, tenants, and drivers, and predictable
  enough to nest.
- **A precise compiler target.** The architecture avoids legacy modes, defines behavior at the ISA
  boundary, and maps modern language primitives directly where possible.
- **Architectural security boundaries.** Authority is explicitly granted, tightly scoped, and
  revocable, with security claims narrow enough to support formal analysis.
- **Accelerator-oriented system interfaces.** Work submission, completion, synchronization, and data
  movement between CPUs and devices are specified as portable architectural contracts.
- **Analyzable real-time behavior.** System-facing operations are designed for bounded behavior so
  worst-case guarantees can be reasoned about during engineering.

## Status

The v1 architecture specification is complete and in pre-publication review, alongside an FPGA
implementation and toolchain work. We intend to develop LNP64 in the open, under an open
specification license, with a working group of industry and research partners.

**Interested in early access to the specification, the working group, or collaboration?**
Contact: kevin@deepai.org
