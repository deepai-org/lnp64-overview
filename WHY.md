<!-- SPDX-FileCopyrightText: 2026 Deep AI, Inc. -->
# LNP64: The Post-Legacy Computing Platform

Cerebras reached a multi-billion-dollar valuation by rejecting one inherited assumption —
that a chip must be diced into reticle-sized pieces — and rebuilding around a single
workload. LNP64 applies the same move to the largest silicon market of all:
general-purpose compute, and the entire stack of operating systems, clouds, and
safety-critical systems that runs on it.

## The incumbents cannot follow

x86 and ARM are bound by a promise: yesterday's software must keep running exactly the
way yesterday's hardware ran it. Fifty years of hardware and operating systems
co-optimizing around that promise has produced architectures that are superb inside their
groove and structurally unable to leave it. That is not a temporary gap — it is the
business model. And it leaves four permanent openings:

- **They must ration isolation.** Keeping workloads apart is expensive on legacy
  architectures, so the entire cloud economy runs on software impressions of walls —
  containers, sandboxes, hypervisors — each layer stacked on the last at compounding
  cost. Incumbents cannot make isolation cheap without breaking the compatibility promise
  that defines them.
- **They must patch security, forever.** Post-Spectre, "hardware security" on legacy
  platforms means an unending stream of software mitigations, each purchased with
  performance. The attack surface is the architecture itself; it cannot be patched away.
- **They must treat accelerators as guests.** GPUs and AI accelerators now carry the
  bulk of the world's compute spend, yet they attach to legacy CPUs through decades of
  per-vendor driver folklore, because the incumbent architectures predate the accelerator
  era and cannot re-found themselves around it.
- **They cannot make timing provable.** On legacy platforms, worst-case response time is
  measured and hoped for, not computed — which is why certification-gated industries
  still run on decades-old silicon and bespoke toolchains.

## What LNP64 delivers

LNP64 is a clean 64-bit architecture designed for how machines are used now: many
mutually distrusting workloads per box, large accelerator fleets, and security and timing
requirements that must be proved, not claimed. In business terms:

- **Higher density, lower cost per tenant.** Isolation is a native hardware construct,
  cheap enough that every plugin, tenant, and driver gets its own — and isolation nests
  without slowing down. The walls the cloud currently fakes in software become the
  default state of the machine, and the overhead currently spent faking them becomes
  sellable capacity.
- **Security as a product property, not an operating expense.** Programs can only touch
  what they've been handed; access is explicitly granted, narrowly scoped, and revocable —
  enforced by the architecture, not by millions of lines of operating-system code hoping
  to be bug-free. The claims are deliberately narrow enough to formally analyze, which is
  the difference between marketing and certification.
- **A vendor-neutral position in the AI buildout.** How work is submitted, completed,
  synchronized, and moved between CPUs and accelerators is a portable architectural
  contract — not a per-vendor moat. Every accelerator maker gets a first-class attach
  point; no one relearns the interface per generation.
- **Access to certification-gated markets.** Worst-case timing is an engineering
  calculation, not a stress test. That unlocks automotive, aerospace, and industrial —
  markets with regulated margins that incumbents structurally struggle to serve.
- **A clean target for the whole software stack.** No legacy modes, no undefined
  corners, no forty years of compatibility sediment. Compilers, operating systems, and
  formal tools build against one precise document.

None of this is a feature grafted onto an existing design. It is what falls out when the
architecture is designed around today's requirements instead of 1975's.

## Why now

Three shifts converge on this moment:

- **The AI buildout repriced the stack.** Accelerator spend now dominates compute
  capex, and the CPU's job is being redefined around orchestrating it — a role the
  incumbent architectures were never designed for and LNP64 is designed for natively.
- **AI raised the security bar past what legacy can clear.** 2026's machines run
  autonomous agents executing generated code against sensitive data at scale. That
  demands isolation cheap enough to wrap around every agent, every tool call, every
  tenant — exactly the property legacy architectures ration and LNP64 makes free.
- **The market has proven it will adopt new architectures.** RISC-V ended the era when
  a new ISA was commercially unthinkable, and post-Spectre mitigation fatigue has made
  buyers receptive to security that is architectural rather than remedial.

## Where things stand

The v1 architecture specification is complete and in pre-publication review, alongside an
FPGA implementation and toolchain work. We are developing LNP64 in the open, under an
open specification license, with a working group of industry and research partners.

**Interested in early access to the specification, the working group, or collaboration?**
Contact: kevin@deepai.org
