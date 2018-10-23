# Open Source to the Stars: How Open Source Helps One of the Biggest Astronomical Observatories in the World - Federico Pellegrin, European Southern Observatory

ESO: European Southern Observatory

Provides infrastructure

## Projects

La Silla Observatory
* Since 1976
* First light of 3.6m
* Many generations of telescopes

Paranal Observatory
* Since 1999
* First light of UT1
* VLT (4 x 8 m visible)
* VLT Interferometer (4 x 8m VLT + 4 x 1.8m AT)
* VISTA
* VST
* Future:
** Cherenkov Telescope Array

ALMA - Atacama Large Millimeter Array
* Since 2011
* Joint with NRAO and NAOJ
* 54 x 12 m + 12 x 7m moveable antennas @ 5000m
* Apex nearby

Extremely Large Telescope
* 39m ground based
* Cerro Armazones
* Started construction May 2017
* First light expected 2024
* Optical / Near IR
* Exoplanets, start formations, protoplanetary systems
* 5 mirrors
* M1: 798 segments, 1.4 meters x 5cm
** 500 Hz (1 Gb/s traffic)
* M4: 4 m (6000 actuators)

## Commonalities of Projects

Long time design to first light
* 5 - 10 years

Long lifespan: > 30 years
* Hardware / software obsolescence

One-off projects with specific needs
* No big market
* Difficulties in testing and reproduction of problems

Mixed developer and user base
* Internal / external development and scientific user-base

Environmental conditions
* Dry, high altitude, etc.

High up-time

## Control Software @ ESO

Software (RT and not)
* Control structures
** Rotation of dome
** Hydraulics
** Wind shields
* Telescope pointing, guiding, tracking
* Optics
* Detectors

Data processing and pipeline

Team
* 50 people

## Code repository at La Silla

Picture of cave paintings on weathered stones (petroglyphs)

## Languagets and Technologies

Phases: HPUX, Solaris, ...
Mostly Linux now
Some RT (VxWorks), Some PLC
GNU Make
Languages: C, TCL/TK, Fortran, C++, Java, Python
X-Based UI: Control SW (TCL moving to Python + Qt), Web based on data handling side
Comms: DDS, CORBA, Custom

## Distro

Mostly RPM based (Scientific Linux moving to CentOS)
Not cutting-edge + experimental packages
* Devtoolset-7 + ASAN
* New kernels and preempt-RT

Installation and VCS with Puppet
* Puppet in master-less config driven by Jenkins
* Sub-classing per versoin, site, facility
* ...

## Build and Test Infrastructure

Jenkins (after using in-house Perl based solution)
* Verify customized using HTPL-pubs
** Low granularity (grouped series of modules)
** Make is parallelized
** Test entry point via make rule with env filters
* CI build on commit
* Test runner in-house solution
...

## Jenkins customized jobs

## Build and Test Infra

VMs and Containers for tests
Code checkers
* cppcheck
* Nagelfar
Special weekend builds
* gcov
* debug kernels
* ASAN runs
* optimized builds
Presence of a Control Model for special tests
* Additional hardware resembling final installation
* OSS booking system
Other code metrics available
RPM on demand
Machine config verification via Puppet

## ELT Dev Env

First light in 2024
Operational until after 2060
Opportunity to update technologies
Sensibility for OSS has grown
* Lessons learned from closed-source
* Major adoption globally
Newer technologies
* Linux RT
* DPKG
* OpenBLAS
* Waf
* CLANG tools
* Anaconda Python
* Docker
* Terraform
* Nomad

## Build system challenges

Single build systems
* C++, Python, Java
* Reliable partial builds
* Full parallelization
* Less specific knowledge

Automatic dependency management
Efficient and parallel
Off-tree builds
Ease of integration with new tools
Logging / debugging support

## Dev Env overview

Various technologies tied together by the build system (waf)

## waf

[https://gitlab.com/ita1024/waf/](waf)
[https://en.wikipedia.org/wiki/Waf](Wikipedia)
OSS project started 2005
Python-based
Focus
* Speed of execution
* Portability
Efficiency on condition of rebuilds
Support many languages and tools (expandable)
Users
* Samba
* RTEMS
* Ardour
* Game companies
wscript:
* Python code
* ...
Example

