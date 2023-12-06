# blueprint
SLICES blueprint

## The blueprint concept

The *blueprint* is a fundamental component in programme management that
guarantees to keep the focus on what is needed to deliver the expected changes
to the programme on time.

The key for the success of an ambitious projects such as SLICES is to take
enough time, effort, and rigour at the head of the programme to set the vision,
requirements, and culture [[^1]].

In SLICES, we leverage the concept of blueprint to ease collaboration between
engineers and non-engineers in order to define and implement this ambitious
scientific infrastructure.

As such, we define a common terminology that doesn't require in-depth, technical
knowledge to produce consistent vision on the application with a focus on the
future objective[[^2]]. But as the devil is in the details, we accompany the
blueprint with a set of reference implementations.

The blueprint is documented and discussed with the community and is built
iteratively[[^3]]. In each cycle, we pick up the right actors to review and
validate the advances made so far and check their adequacy with the baseline.
Each iteration is used to refine the definition of the SLICES infrastructure.

Each iteration being a refinement of the previous one, we progress in parallel
with with blueprint components. At the current stage, we are iterating on the
*5G* and the *Cloud+Edge* components of the blueprint.

## Objective to reach

As a reminder, SLICES is the acronym for *Scientific Large-scale Infrastructure
for Computing/Communication Experimental Studies*. The aim of the project is
to serve the  community to take their research to the next level. As such,
SLICES has identified the following 5 types of studies to support.

### Type 1 studies: Vertical service integration and testing

Researchers use the infrastructure as a blackbox to test their own ideas.

> **Example 1:** researchers assume a beyond 5G infrastructure to upload raw
Lidar data from their drones to their ground station to create 3D environment
models in real time. The scientific core of these researchers is computer
vision, not  telecom and 5G is just a commodity for them but it would be too
time-consuming and costly for them to deploy such an infrastructure.

### Type 2 studies: Software Defined Networking

Researchers work on the altering the behavior of the network itself by following
the Software Defined Networking (SDN) paradigm and need complex environments to
validate their research.

SLICES to provide access to well-defined network function interfaces (e.g.,
xAPP, P4, DPDK) and KPI collection.

> **Example 1:** researchers that propose AI-based dynamic virtual network
functions placement with performance guarantees have to validate their algorithm
on high speed wide area network. The researchers need to have access to terabits
per second backbone with programmable switches to test their implementation.


### Type 3 studies: Low level development on resources

Researchers work on the lowest level layers of the network stack (e.g., PHY/MAC)
and have to validated and measure their findings on actual hardware.

> **Example 1:** researchers propose a new low energy MAC layer for high density
IoT location with 5G gateways. They need access to real hardware to measure the
performance of the new MAC and measure the actual energy savings.

### Type 4 studies: Novel hardware

Researchers work on new hardware such as antennas, RIS, THz radio, cryptographic
functions, packet processors, TSN devices... This hardware alone is not of much
use if not integrated in a full system. Researchers can insert their hardware in
the  infrastructure and use their time slots to exercise it.

> **Example 1:** researchers produced a new Reconfigurable Intelligent Surface
and must calibrate their model for when it is used in a 5G user equipment where
the 5G scheduler causes communications to adapt based on real-time QCI feedback.

### Type 5 studies: cross-topics and resources

Researchers need the combination of resources from different topics to succeed
in their research.

> **Example 1:** researchers make a digital twin of a very large interconnection
of radio networks. Real-time 3D radio emulators run in GPU farms and the
workload generated workload is interconnected over TBps P4 SDN core. The number
of UE in the radio networks doesn't allow to be exercised with actual UEs, hence
the need of high processing capabilities directly linked with networking
equipment.

> **Example 2:** AI-aided development, optimization, and fuzz testing of
contributions in open-source projects with hardware-in-the-loop, such as
OpenAirInterface and ORAN.

## References
[^1]: https://www.axelos.com/resource-hub/blog/msp-setting-the-blueprint-for-a-better-future
[^2]: https://dev.to/jayjayjpg/what-is-a-software-blueprint-5388
[^3]:  https://www.qrpinternational.fr/blog/faq/blueprint-quest-ce-que-cest/