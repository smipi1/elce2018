# Real Time is Coming to Linux; What Does that Mean to You? - Steven Rostedt, VMware

Who is this talk for?
* Linux kernel devs

About
* `PREEMPT_RT`

What is Real-time as per `PREEMPT_RT`?
* Determinism
  - Latency
* Can calculate worst-case scenarios

Strategy
* As preemptive as possible
* Remove preemption and IRQ handling
  - Where possible
* Allow scheduling to happen (almost) everywhere

Menuconfig
* Preemption model: Fully preemptible kernel

    CONFIG_PREEMPT_RT_FULL

Interrupts as threads
Not all interrupts become threads
* Timer interrupts and Inter-processor interrupts
* ...

Interrupts
* Forced threaded interrupts

Enable `PREEMPT_RT`:
* `spin_lock*()` becomes a mutex
* Priority inheritence
  - Prevents inversion
  - Currently only futex
  - Now always
* `rw_locks` becomes more like rwsem (sleepable reader / writer locks)
* Readers do *NOT* have priority inheritence
* Writers do inherit the priority
  - Don't boost readers
* Avoid rw locks and sems
  - Horrible for cache-lines (don't scale)
  - Use RCU where you can
* Trylock issue
  - Works fine for spinning locks, not other things
  - Problematic for sleeping spin locks
  - Hack available (until you have been able to solve it properly)
* Per-CPU variables
  - Variables only accessible by associated CPU
  - Spin locks no longer disable preemption
  - Spin locks do disable migration!
  - Preempt disable not bad, but: _keep it short_
  - Keep slow operation out of the preempt disable sections
* Avoid `local_irq_save()`: Most likely a bug if using it
  - Use `spin_lock_irqsave()` (or `spin_lock_irq()`)
* Softirqs
  - Real pain-in-the-ass
  - Raised (asked to run)
  - Raised by interrupts
  - Raised by tasks
  - `local_bh_disable()` and `spin_lock_bh()`
  - `PREEMPT_RT`: Run by who raises them (mask used), `local_bh_enable()` runs the softirqs by the task, ksoftirq runs the rest
  - Mainline currently suffering: starvation, patch to help, influences by `PREEMPT_RT`...
* `raw_spin_locks()`
  - 2009: No meaning in mainline
  - Used when you _definitely cannot sleep_
  - Don't use because you cannot figure it out

