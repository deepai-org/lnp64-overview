<!-- SPDX-FileCopyrightText: 2026 Deep AI, Inc. -->
# Why LNP64 — the plain-language version

*If the [README](README.md) reads like it was written for chip architects, that's because it
was. This page is for everyone else.*

## The fifty-year groove

The processor in every server, laptop, and phone you own is a descendant of designs from an
era when a computer was one trusted machine running a handful of programs, all of which
basically trusted each other. The hardware made assumptions that fit that world, and
operating systems were built to fit the hardware. Then the hardware evolved to run those
operating systems faster. Then the operating systems adapted to the new hardware. Fifty
years of that, and the two have co-optimized themselves into a deep, comfortable groove.

The groove is a local minimum. Everything inside it is astonishingly fast and refined.
Everything *outside* it — the things modern computing actually needs — has to be faked in
software, bolted on, or worked around:

- **Isolation is rationed.** Keeping programs safely apart from each other is expensive on
  today's hardware, so we treat walls as a scarce resource. Containers, sandboxes, and
  virtual machines are elaborate software impressions of walls the silicon never provided —
  and stacking them (a container inside a VM inside a VM) compounds the cost.
- **Security is a patch, not a property.** Most of what we call "hardware security" today
  is software mitigation for behavior the hardware never promised in the first place. Each
  new attack gets a new patch, and each patch costs performance.
- **Accelerators are guests, not residents.** GPUs and AI accelerators now do most of the
  interesting work, but they talk to the CPU through decades of accumulated driver folklore
  rather than anything the architecture actually guarantees.
- **Timing is a hope, not a number.** For systems that must respond within a deadline —
  robotics, vehicles, industrial control — today's architectures make worst-case timing
  something you measure and pray about, not something you can compute and prove.

You can't fix this by digging the groove deeper. Every mainstream architecture is
constrained by the promise to keep running yesterday's software exactly the way yesterday's
hardware did.

## Starting from where the puck is

Companies like Cerebras showed what happens when you drop the inherited assumptions and
design silicon for the workload that actually exists: you don't get an incrementally better
chip, you get a different shape of machine. LNP64 applies that move to the general-purpose
CPU and the layer of software that sits on it. It is a clean 64-bit architecture designed
for how machines are used *now*: many mutually distrusting workloads per box, large
accelerator fleets, and security and timing requirements you have to be able to prove, not
just claim.

What that buys, in plain terms:

- **Walls become free enough to put everywhere.** Isolation is a native hardware construct,
  cheap enough that every plugin, every tenant, every driver gets its own — and walls nest
  without slowing down. The security model people fake with containers becomes the
  default state of the machine.
- **Programs can only touch what they've been handed.** Access is explicitly granted,
  narrowly scoped, and instantly revocable — enforced by the architecture itself, not by a
  million lines of operating-system code hoping to be bug-free. And the security claims are
  deliberately narrow enough that they can be formally analyzed, not just marketed.
- **Accelerators get a contract.** How work is submitted, completed, synchronized, and how
  data moves between CPUs and devices is specified by the architecture, portably — instead
  of being rediscovered per-vendor, per-driver, per-generation.
- **Worst-case timing is a number you can compute.** System operations are designed for
  bounded behavior, so "will this respond in time?" is an engineering calculation instead
  of a stress test.
- **Software gets a clean target.** No legacy modes, no undefined corners, no forty years
  of compatibility sediment for compilers and operating systems to tiptoe around.

None of these is a feature grafted onto an existing design. They're what falls out when you
design the whole architecture around today's requirements instead of 1975's.

## Where things stand

The v1 architecture specification is complete and in pre-publication review, alongside an
FPGA implementation and toolchain work. We intend to develop LNP64 in the open, under an
open specification license, with a working group of industry and research partners.

**Interested in early access to the specification, the working group, or collaboration?**
Contact: kevin@deepai.org
