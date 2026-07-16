<!-- SPDX-FileCopyrightText: 2026 Deep AI, Inc. -->
# LNP64

**A 64-bit instruction set architecture for isolated, accelerated, and analyzable systems.**

Mainstream CPU architectures still reflect systems built around one trusted operating system and a
small number of local programs. Modern deployments run many mutually distrusting workloads per
machine, coordinate accelerator pools, and rely on software mitigations for properties hardware does
not directly provide.

LNP64 is a clean 64-bit architecture for those requirements.

*For the opportunity and the timing, see [LNP64: The Post-Legacy Computing Platform](WHY.md).*

## The design goals

- **Low-cost isolation.** Sandboxes, containers, and virtual machines are first-class hardware
  constructs, cheap enough for individual plugins, tenants, and drivers, and predictable enough to
  nest.
- **A precise compiler target.** No legacy modes; behavior is defined at the ISA boundary, with
  direct mappings for modern language primitives where possible.
- **Architectural security boundaries.** Authority is explicitly granted, tightly scoped, and
  revocable, with security claims narrow enough for formal analysis.
- **Accelerator-oriented interfaces.** Work submission, completion, synchronization, and CPU-device
  data movement are portable architectural contracts.
- **Analyzable real-time behavior.** System-facing operations are bounded so worst-case guarantees
  can be reasoned about during engineering.
- **Owner sovereignty.** The machine answers to its owner. There is no state the owner cannot
  inspect, no key the owner cannot read and replace, and no vendor-privileged channel. Attestation
  proves to the owner's own verifier what a machine runs — it can never prove to a third party that
  the owner is locked out. The conformance mark extends this through the stack: the specification
  and its machine-readable catalog are the complete programming interface, bundled hardware comes
  with free drivers or complete freely licensed documentation, and firmware is either permanent
  factory circuitry or free software installed with free tools.

## Status

The v1 architecture specification is complete and in pre-publication review, alongside an FPGA
implementation and toolchain work. We intend to develop LNP64 in the open, under an open
specification license, with a working group of industry and research partners.

**Interested in early access to the specification, the working group, or collaboration?**
Contact: kevin@deepai.org
