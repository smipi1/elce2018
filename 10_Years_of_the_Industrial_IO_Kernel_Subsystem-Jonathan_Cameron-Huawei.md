# 10 Years of the Industrial I/O Kernel Subsystem - Jonathan Cameron, Huawei

## History

SESAME project
* Sensors on athletes

Linux platform
* Intel research IMote2

Sensor drivers
* Acceleromerters, ADCs
* Upstream, but as what?

Devices
* ADC: Accelerometers, Gyros, Magnetometers, IMUs, Light, Chemical, Health, Rotation, ...
* DAC

## Interface principles

User-space IF
Allows generic user-space code
All control and metadata via `/sys`
* Human readable
* Consistent and predictable
Single channel polled read via `/sys`
Character devices:
* FIFOs
* Events

## IIO Architecture

Simple polled read, or
Trigger / buffer (push) concept
* Concurrent samples from enabled channels
* Buffers for asynchronous reads

Synchronous read `sysfs`
- Read sysfs
- Call IIO core
- Meta-data linking
- Raw read on driver
- Driver-specific read
- Hardware
- Return
- Format
- Return string

Why core? consistency

Synchronous read `consumer driver`
- return raw value

Push data flow

Issue 2: Coupling is too tight between user-space and backend

Why so complex?
* Flexibility


Lets do cool things
* Generic ADC touch screen driver
* Chained IIO devices

Issue 3: The future is hard to predict

## Some of our mistakes

ABI Mistakes
* Generalized simplicity over local simplicity
* Compatibility with existing ABI is nice, but don't try too hard
** Unit choices of hwmon weren't good to copy
* Abstraction does not always map well
* Counter drivers moving out of IIO to own subsystem
** Cleaner abstraction
** Appropriate flexibility
** Historic ABI compatibility
* Missing indication of interest
** Normal sysfs flow provides no 'I will read this shortly'

Issue 4: Where do high performance devices fit?

High speed device needs
* DMA buffers
* Handling complex multi-sample triggering and state changes
* Inline meta data, alignment tags, etc.
* Often self describing flows

Issue 5: Complex devices with proprietary user-space

Generalization breaks...
* Some sensors
** Pulse oximeters need complex post processing to provide useful output
* So far:
** Mapped to generic interfaces @ boundairy

## Community

Route to success
* Posts to LKML
** Good feedback, slow progress
* Staging
** Unusual route for a subsystem
** Time to work out where to go
** Great feedback
* Making that jump
** ABI stability

Who wrote all the drivers
* Not him
* > 20 companies
* ...


