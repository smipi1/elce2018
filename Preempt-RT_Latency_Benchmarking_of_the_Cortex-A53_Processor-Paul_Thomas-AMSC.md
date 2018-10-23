# Preempt-RT Latency Benchmarking of the Cortex-A53 Processor - Paul Thomas, AMSC

## Hardware set-up

Cortex A53
* Enclustra Mercury XU5
* Xilinx MPSoC XCZU5EV
* 8-stage pipeline
* 1.3 GHz

Cortex A9
* Zedboard
* Xilinx XC7Z020
* 10+ stage pipeline
* 666 MHz

## Kernel

* `PREEMPT_RT 4.18-rc8-rt1`
* Zynqmp firmware and clock driver patch

## Cyclictest

Cortex A53
* Max 17us
* Ave 7 us

Cortex A9
* Max 54 us
* Ave ...

## Cpuset shielding

Isolate core for dedicated RT work

System set
* CPU 0
* CPU 1
* CPU 2
* Cyclictest prio 98
* Cyclictest prio 99
* Stress 2

User set
* CPU 3
* Cyclictest prio 98
* Cyclictest prio 99

## UDP ping-pong test

UDP round-trip test

2 x Cortex A53 boards
* Dedicated Ethernet ports
* Max 168 us
* Ave 101 us

Zedboard
* Not possible (shared with ssh)
* Max > 800 us
* Ave 182 us

SPUSETs not used
* Affected performance

IRQ affinity pinned to last CPU

## Real-world test

ADC Driver
* IIO Sub-system
* DMA based
* Performance measured with HW

## Industrial IO sub-system

Types including
* ADC
* DAC
* Accelerometers

Can provide
* Text formatted measurements
* Binary

## Hardware config

In Zynq MPSoC
* Simulated ADC in Zynq MPSoC
* A/D Controller
* DMA block
** Feeds into AXI Slave, and
** Interrupts, and
** Next:
* Timer / capture block
** Feeds into AXI Master

## IIO Driver DMA IRQ Latency

Max 30 us
Ave 9 us

## Timer capture function

Common in SoCs and uC

Present value stored on trigger event

In-kernel ISR is trigger
* DMA Engine callback
* Stored load register

Latency can be calculated

## Conclusions

Coretex A53 is low latency

Programmable logic to de-couple SPI bus very effective

