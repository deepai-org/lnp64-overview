<!-- SPDX-FileCopyrightText: 2026 Deep AI, Inc. -->
# LNP64: The Post-Legacy Computing Platform

Cerebras reached a multi-billion-dollar valuation by rejecting one inherited assumption:
that chips must be diced into reticle-sized pieces, then rebuilding around one workload.
LNP64 applies the same move to the largest silicon market: general-purpose compute, and
the operating systems, clouds, and safety-critical systems built on it.

## The incumbents cannot follow

x86 and ARM are bound by compatibility: yesterday's software must keep running exactly
as before. That promise produced excellent architectures inside their groove, but it
also prevents them from being rebuilt around today's requirements. Four permanent
openings follow:

- **They must ration isolation.** Legacy isolation is expensive, so clouds stack
  containers, sandboxes, and hypervisors as software walls at compounding cost.
  Incumbents cannot make isolation cheap without breaking their compatibility promise.
- **They must patch security, forever.** Post-Spectre hardware security largely means
  software mitigations bought with performance. The attack surface is architectural, so
  it cannot be patched away.
- **They must treat accelerators as guests.** GPUs and AI accelerators now carry much
  of compute spend, yet attach through per-vendor driver folklore because incumbent
  CPUs predate the accelerator era.
- **They cannot make timing provable.** Worst-case response time is measured and hoped
  for, not computed. Certification-gated industries still depend on old silicon and
  bespoke toolchains as a result.

## What LNP64 delivers

LNP64 is a clean 64-bit architecture for machines that run many mutually distrusting
workloads, coordinate accelerator fleets, and need security and timing properties that
can be proved. In business terms:

- **Higher density, lower cost per tenant.** Isolation is native, cheap, and nestable,
  so every plugin, tenant, and driver can get its own boundary. Capacity now spent
  faking walls in software becomes sellable capacity.
- **Security as a product property.** Programs can touch only what they are handed.
  Authority is explicit, narrow, revocable, and enforced by the architecture rather
  than by millions of lines of operating-system code. The claims are narrow enough for
  formal analysis, making security a certifiable property rather than an operating
  expense.
- **A vendor-neutral role in the AI buildout.** Work submission, completion,
  synchronization, and CPU-accelerator data movement become portable architectural
  contracts, not per-vendor moats. Every accelerator maker gets a first-class attach
  point without relearning the interface each generation.
- **Access to certification-gated markets.** Worst-case timing becomes an engineering
  calculation rather than a stress test, opening automotive, aerospace, and industrial
  markets with regulated margins where incumbents struggle.
- **A clean target for the software stack.** No legacy modes, undefined corners, or
  decades of compatibility sediment. Compilers, operating systems, and formal tools
  target one precise document.
- **Sovereignty as a product line.** A conforming LNP64 machine has no distrust zone
  against its owner: no vendor keys the owner cannot replace, no uninspectable
  enclaves, no remote-kill path, no undocumented interface, and firmware that is
  either permanent circuitry or free software installed with free tools. Governments,
  regulated industries, and infrastructure operators with digital-sovereignty and
  auditability mandates get, for the first time, an architecture whose ownership story
  is a conformance requirement rather than a vendor's promise — a market incumbents
  cannot enter without dismantling the platform-control businesses built on top of
  their silicon.

These are not grafted-on features. They follow from designing the architecture around
today's requirements instead of 1975's.

## Why now

Three shifts converge:

- **AI repriced the stack.** Accelerator spend now dominates compute capex, and CPUs
  are being redefined around orchestration: a role LNP64 supports natively.
- **AI raised the security bar.** 2026 systems run autonomous agents executing generated
  code against sensitive data at scale. That requires isolation around every agent,
  tool call, and tenant: exactly what legacy architectures ration and LNP64 makes cheap.
- **The market accepts new architectures.** RISC-V made new ISAs commercially credible,
  while post-Spectre mitigation fatigue created demand for architectural security.

## Where things stand

The v1 architecture specification is complete and in pre-publication review, alongside
an FPGA implementation and toolchain work. We are developing LNP64 in the open, under
an open specification license, with a working group of industry and research partners.

**Interested in early access to the specification, the working group, or collaboration?**
Contact: kevin@deepai.org
