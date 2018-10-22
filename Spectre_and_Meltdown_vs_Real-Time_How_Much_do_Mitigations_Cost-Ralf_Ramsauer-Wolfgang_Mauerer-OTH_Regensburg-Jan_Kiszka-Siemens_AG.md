# Spectre and Meltdown vs. Real-Time: How Much do Mitigations Cost? - Ralf Ramsauer & Wolfgang Mauerer, OTH Regensburg; Jan Kiszka, Siemens AG

## Attack Surface

* Branch predition / speculative execution exploits
* Violation of memory protection guarantees
* Local vector
* High attack complexity

## Mitigations

### Spectre

Variant 1: Bound check bypass:

* `__user` pointer sanitizatoin

Variant 2: Branch target injection:

* Retpoline
* Speculation control through ucode
* ARM64: ATF v1.6
* Fill return stack buffer on context switch

Variant 3: Meltdown

* Page Table Isolation
* Page directory separation Kernel / Userspace
* Unmap kernel from Userspace

Variant 4: Speculative store bypass

* Intel: ucode update
* ARM64

Level 1 Terminal Fault - Foreshadow

* Mitigation:
** Disable SMT
** PTE inversion
** Conditional cache flushes on VMENTER
* Low cost for native, high for VM

Affected CPUs...

### Real-time vs mitigations

Realtime:

* Determinism
* Time-sensitive cyclic execution
* Bounded latencies
* Repeatable results

Mitigations:

* Cheap
* Expensive
* Additional sources

### Measurement set-up

Basic idea

* RT payload on multi-core
* Meaure responsivity
* Repeat:
** With / without mitigations
** With / without additional load
* Reduce variation of mitigations
** No protection
** Default protection
** PTO only
** Variant 2 only
* Proper statistic analysis

Tools

* `cyclictest`
* `stress-ng`
* Repeat in vitrualised env

### Get target under control

Fix undesired high latencies

* NMI, Watchdogs, ...
* Reduce noise:
** CPU isolation
** SMP affinity of IRQ's
** Net device affinity
** Disable NCP
* Broken behavior `cyclictest` and `stress-ng`
* ...
* Obstacles in whole system stack



