# How to design a SLICES-RI blueprint?

This document aims to provide instructions on how to design a SLICES-RI
blueprint.

A blueprint is based on the concept of "thought experiments", a type of
experiment that Schrödinger considered impossible to realize (The Photon box). 
What matters in SLICES is not the infrastructure but the thought experiments and
the support of the full research life cycle, including FAIR[[^fair]] data and
reproducibility.

Every blueprint is documented and discussed with the community and built
iteratively[[^1]]. In each cycle, we pick up the appropriate actors to review
and validate the advances made so far and check their adequacy with the
baseline. Each iteration is used to refine the definition of the blueprint.

Every blueprint must support full research cycles. At the level of the
blueprint, the experimental research cycle is abstracted in 3 phases [[^pos]].

1. **Setup phase:** allocate resources and prepare the software/hardware
environment to support the experimental requirements. Each experiment must be independent of the other experiments (past, current, or future). 
2. **Measurement/experiment phase:** orchestrate experiments and measurements
according in a way that scarce resources are used efficiently. In the meanwhile,
operational parameters are collected and stored.
3. **Evaluation phase:** collected results are evaluated and processed.
Collected datasets (experimental + operational data) and related meta-data are
documented and published in format easily readable by researchers.

## Design principles

Blueprints must be designed in a modular way such that one can either deploy it
fully or only partially.

Blueprints are built in increasing complexity, described step-by-step and
seconded by an open source reference implementation, that can be used as a
baseline:

* for researchers to exercise their experimental research;
* for the SLICES community to build the SLICES infrastructure.

Blueprints are inherently reproducible and their entire experiment cycle must
be compatible with the pos framework [[^pos]].

All data and metadata must be published, and respect the FAIR principle
[[^fair]]. Published data and meta-data can be subject to policy enforcement.

## Requirements

The full experiment cycle must be automated in a reproducible way using pos 
framework [[^pos]]. Other alternatives are possible as long as at least pos is
supported.

All data and metadata must be managed by the MRS and its associated DMI.
Published data and meta-data can be subject to policy enforcement.

## References

[^fair]: COMISSION, E., 2022. Guidelines on FAIR Data Management in Horizon 2020.[Sl], 2016.

[^1]:  https://www.qrpinternational.fr/blog/faq/blueprint-quest-ce-que-cest/, accessed December 12, 2023.

[^pos]: Gallenmüller, S., Scholz, D., Stubbe, H. and Carle, G., 2021, December. The pos framework: A methodology and toolchain for reproducible network experiments. In Proceedings of the 17th International Conference on emerging Networking EXperiments and Technologies (pp. 259-266).