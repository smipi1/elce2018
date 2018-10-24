# Kernel Analysis Using eBPF - Daniel Thompson, Linaro

## Using eBPF for debugging

## Hand-rolled

Asm

Pure C

## Compilers

### Awk-like

ply
* Easy to cross-compile

SystemTap
* eBPF backend
* More aggressive verifier
* Can print all the local variables (Access to DWARF)
* Rich library of useful tested examples and war story
* Still a little way off on practical use with eBPF

BPFtrace
* Has superpowers
* Dependencies are inconsistently packaged
* May require compiling yourself
* Awesome potential

### BCC

* Easy to use (Python)
* Much harder to cross-compile

## Examples

Aggregating power state transitions
Who is hammering a library function?
- I did a quick profile and its showing a library function dominating one of the cores
- What now?
Hunting leaks
- I'm leaking memory (or some other resource) from pool with specific workload
- System almost ready to ship
- Resource tracking already disabled
- What can I do to get a clue?
Debug kernel functions @ runtime
- BCC `tools/trace.py` can be used to debug kernel function
- Trace funnctions with infos

