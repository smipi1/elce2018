# RISC-V ISA and Foundation Overview - Rick O'Connor, RISC-V Foundation

Clean-slate ISA (Instruction Set Architecture) developed:

* Inspiration from MIPS, SPARC and x86
* 3 month project: Stretched to 4 years
* UC Berkley released frozen base user spec
* Named *RISV-V*
* August 2015: Non-profit *RISC-V* Foundation to govern ISA

## Why does an ISA matter?

* Why are 99% of laptops based on AMD x86_64 ISA?
* Why are 99% of mobile phones + tablets base on ARM v7/8 ISA?
* ISA is most important interface in a computer system
** Where software meets hardware

## Open software / standards work!

* Why are there no successful free / open ISA standards and free / open implementations?

## Most CPU chips are SoCs with many ISAs

* Applications processor
* Graphics processors
* Image processors
* Radio DSPs
* Audio DSPs
* Security processors
* Power-management processor
* ...

## Why so many ISAs?

* do we need these different ISAs?
* Do they need to be proprietary?

## What's different about RISC-V?

* Simplicity (Far smaller)
** Adds 30 years of hindsight
** 50 instructions in base ISA
* Clean-slate design
** Clear separation between user and privileged ISA
** Avoids uArch or Tech-dep features
* Modular
** Small std base ISA
** Extensions
* Designed for extensibility / specialization
** Variable-length instruction encoding
** Vast opcode space for extensions
* Stable
** Base and std ext frozen
** Additions via optional exts (not new versions)

## RISC-V Base Plus Tdandard Exts

4 x base integers ISAs

< 50 HW instructions needed

Extensions
* M: Integer mul/div
* A: Atomic mem ops
* F:
* D:
* G
* Q
* ..

## RISC-V in Education, new books

The RISC-V Reader - David Patterson, ...

## RISC-V Foundation overview & Growth

* August 2015
* Maintains standard
* Compliance suite
* Trademark
* ~ 200 members and growing
* Board of directors: 7+ members
* Technical committees: Technical, Security, Marketing

## RISC-V Use case examples

### NVIDIA

Falcon architecture:

* 15+ designs
* 50 chips
* Shipped ~ 3E9 times
* 0 stop-ship bugs

Next architecture:

* Evaluated: RISC-V is only architecture meeting all criteria

### Western Digital

RISC-V Meets the needs of both:

* Big-data, and
* Fast data

Commitment given to ship all new cores with RISC-V (1E9 cores / year)

