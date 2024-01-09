# The blueprint concept and philosophy

The blueprint is based on the concept of "thought experiments", a type of experiment
that Schrödinger considered impossible to realize (The Photon box). 
What matters in SLICES is not the infrastructure but the thought experiments and the
support of the full research life cycle, including FAIR[[^fair]] data and reproducibility.

It is impossible for SLICES RI to be exhaustive, neither we pretend to be able to 
identify these thought experiments. We call for the research community to suggest
how an infrastructure and its data sets can be deployed in SLICES for that purpose.

The key for the success of an ambitious projects such as SLICES is to take
enough time, effort, and rigour to set the vision,
requirements, and culture [[^1]].

In SLICES, we leverage the concept of blueprint to ease collaboration between
engineers and non-engineers. As such, we define a common terminology that doesn't require in-depth, technical
knowledge to produce consistent vision on the application with a focus on the
future objective[[^2]]. But as the devil is in the details, we accompany the
blueprint with a set of reference implementations. 

The blueprint is documented and discussed with the community and built
iteratively[[^3]]. In each cycle, we pick up the appropriate actors to review and
validate the advances made so far and check their adequacy with the baseline.
Each iteration is used to refine the definition of the SLICES infrastructure.

> [!TIP]
> Finding the right actors in the cycles is essential and this is where the
> blueprint and its multi-level of readings is an essential tool. Indeed, in
> every cycle we involved both the management and engineers of the platform
> community but also researchers from communities that are supposed to be
> supported by SLICES. As a consequence, the blueprint is always aligned with
> the actual needs of researchers and can put priority on what is really
> essential to the targeted researchers.

Each iteration being a refinement of the previous one, we progress in parallel
with blueprint components. At the current stage, we are iterating on the
*5G* and the *Cloud+Edge* components of the blueprint.

## Objectives to be reached by the scientific instrument

As a reminder, SLICES is the acronym for *Scientific Large-scale Infrastructure
for Computing/Communication Experimental Studies*. 

The aim of the project is to serve the community to take their research to
the next level. This means that SLICES must support the studies lead by the
community. As such, SLICES has identified the following 5 types of studies to
support. To be considered as valid, **research must be reproducible**.

> [!IMPORTANT]
> Independent reproduction of experimental results is essential to produce sound
> scientific results **reproducible**[[^reproducibility],[^pos]]. All scientific
> instrument, SLICES included, must then provide full support to reproducible
> research cycles.

> [!NOTE]
> This blueprint uses the ACM terminology for reproducibility in experimental
> science[[^badges]].


### Type 1 studies: Vertical service integration and testing

Researchers use the infrastructure as a layered architecture that they can
safely use as a blackbox offering a full end-to-end service yet understanding
the underlay.

> **Example 1:** researchers assume a beyond 5G infrastructure to upload raw
Lidar data from their drones to their ground station to create 3D environment
models in real time. The scientific core of these researchers is computer
vision, not  telecom and 5G is just a commodity for them but it would be too
time-consuming and costly for them to deploy such an infrastructure.

### Type 2 studies: Software Defined Networking

Researchers work on altering the behavior of the network itself by following
the Software Defined Networking (SDN) paradigm. They need complex environments to
validate their research.

SLICES to provide access to well-defined network function interfaces (e.g.,
xAPP, P4, DPDK) and KPI collection.

> **Example 1:** researchers who propose AI-based dynamic virtual network
functions placement with performance guarantees have to validate their algorithm
on high speed operational-like networks. The researchers need to have access to
terabits per second backbone with programmable switches to test their
implementation.

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
and must calibrate their model when it is used in a 5G user equipment where
the 5G scheduler causes communications to adapt based on real-time QCI feedback.

### Type 5 studies: cross-topics and resources

Researchers need the combination of resources from different topics to succeed
in their research.

> **Example 1:** researchers make a digital twin of a very large interconnection
of radio networks. Real-time 3D radio emulators run in GPU farms and the
workload generated workload is interconnected over Tbps P4 SDN core. The number
of UE in the radio networks doesn't allow to be exercised with actual UEs, hence
the need of high processing capabilities directly linked with networking
equipment.

> **Example 2:** AI-aided development, optimization, and fuzz testing of
contributions in open-source projects with hardware-in-the-loop, such as
OpenAirInterface and ORAN.

## Reproducible research

Reproducibility can take multiple forms and different methodologies can be
followed. It is a component of utmost importance in SLICES RI.

Before continuing, let's remind the terminology from the ACM:

> **Reproducibility (Different team, same experimental setup)**
>
> The measurement can be obtained with stated precision by a different team
> using the same measurement procedure, the same measuring system, under the
> same operating conditions, in the same or a different location on multiple
> trials. For computational experiments, this means that an independent group
> can obtain the same result using the author’s own artifacts[[^badges]].


SLICES as a scientific instrument must support full research cycles. At the
level of the blueprint, we can abstract experimental research cycles in 3
phases [[^pos]].

1. **Setup phase:** allocate resources and prepare the software environment
to support the experimental requirements. Each experiment must be independent of
the other experiments (past, current, or future). 
2. **Measurement/experiment phase:** orchestrate experiments and measurements
according in a way that scarce resources are used efficiently. In the meanwhile,
operational parameters are collected and stored.
3. **Evaluation phase:** collected results are evaluated and process.
Collected datasets (experimental + operational data) and related meta-data are
documented and published in format easily readable by researchers. Published
data and meta-data can be subject to policy enforcement.

To support reproducibility, SLICES must support *(i)* **Heterogeneity** of
hardware and software to support the types of studies defined above. Its
objective is not be be unique and offer a one-and-only solution.

As experiments in these studies are inherently distributed and may involve
devices which behavior might influence experiments (e.g., a radio transmission
may impact other radio reception), it is also required to provide *(ii)*
**Isolation** such that an experiment cannot impact the other experiments.

In addition, experimental research often starts with trial-and-error and
potential heavy modifications of system under study. SLICES must then guarantee
*(iii)* **Recoverability** at any moment such that experiments are always
started from a well-defined initial state.

Modern research implies large and complex interactions and preparation, that
could be error-prone if done manually, and hard to repeat more than a few times.
This is why SLICES must support *(i)* **Automation**.

To be reproducible all steps and results must be provided, well-documented, and
available to researchers involved in the study (not necessarily public). To
achieve this goal SLICES must ensure *(i)* **Non-ambiguous Archivability** of
experiments, not only results, but also artifacts that lead to these results,
including the actual state of the system when results have been obtained
[[^pos],[^nepi],[^badges]]. 

> [!IMPORTANT]
> Publication of data and meta-data is defined in conformance with the FAIR Data
> principle[[^fair]] and aligned with EOSC governance [[^eosc]].

> [!IMPORTANT]
> Experimenters must be able to chose the license, access, and pricing policy
> for all data and meta-data resulting from use SLICES.

## References
[^refESFRI]: https://www.esfri.eu/forum
[^slices]: https://www.slices-ri.eu/, accessed December 12, 2023.
[^slices2]:Serge Fdida, Nikos Makris, Thanasis Korakis, Raffaele Bruno, Andrea Passarella, Panayiotis Andreou, Bartosz Belter, Cédric Crettaz, Walid Dabbous, Yuri Demchenko, Raymond Knopp,SLICES, a scientific instrument for the networking community, Computer Communications, Volume 193, 2022, Pages 189-203,
[^1]: https://www.axelos.com/resource-hub/blog/msp-setting-the-blueprint-for-a-better-future, accessed December 12, 2023.
[^2]: https://dev.to/jayjayjpg/what-is-a-software-blueprint-5388, accessed December 12, 2023.
[^3]:  https://www.qrpinternational.fr/blog/faq/blueprint-quest-ce-que-cest/, accessed December 12, 2023.
[^reproducibility]: Munafò, M.R., Nosek, B.A., Bishop, D.V., Button, K.S., Chambers, C.D., Percie du Sert, N., Simonsohn, U., Wagenmakers, E.J., Ware, J.J. and Ioannidis, J., 2017. A manifesto for reproducible science. Nature human behaviour, 1(1), pp.1-9.
[^pos]: Gallenmüller, S., Scholz, D., Stubbe, H. and Carle, G., 2021, December. The pos framework: A methodology and toolchain for reproducible network experiments. In Proceedings of the 17th International Conference on emerging Networking EXperiments and Technologies (pp. 259-266).
[^nepi]: Quereilhac, A., Lacage, M., Freire, C., Turletti, T. and Dabbous, W., 2011, September. NEPI: An integration framework for network experimentation. In SoftCOM 2011, 19th International Conference on Software, Telecommunications and Computer Networks (pp. 1-5). IEEE.
[^badges]: Artifact Review and Badging Version 1.1, https://www.acm.org/publications/policies/artifact-review-and-badging-current, accessed December 12, 2023.
[^eosc]: https://eosc-hub.eu/, accessed December 12, 2023.
[^fair]: COMISSION, E., 2022. Guidelines on FAIR Data Management in Horizon 2020.[Sl], 2016.
