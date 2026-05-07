---
title: 'Climate-OnSSET'
tags:
  - containers
  - docker
  - psychology
  - reproducibility
  - Docker
authors:
 - name: Vanessa Sochat
   orcid: 0000-0002-4387-3819
   affiliation: 1
affiliations:
 - name: Stanford University Research Computing
   index: 1
date: 28 November 2017
bibliography: paper.bib
---

# Summary

Climate-OnSSET reformulates the logic of geospatial electrification planning under conditions of climate stress. The conventional OnSSET framework is fundamentally structured around techno-economic efficiency: settlements are prioritized according to least-cost principles, and electrification pathways emerge from minimizing the levelized cost of electricity (LCOE) across competing technologies. In such a formulation, the dominant planning question becomes how universal access can be achieved at minimum aggregate cost.

The Climate-OnSSET extension challenges this premise by introducing climate-sensitive prioritization into the sequencing logic of electrification. Rather than treating electrification exclusively as a cost-optimization problem, the framework interprets electricity access as a component of adaptive capacity and socio-technical resilience. The central idea is therefore not to replace least-cost planning, but to subordinate it to a broader planning rationale in which vulnerable populations exposed to climate hazards may be prioritized even when they are not the most economically attractive settlements to electrify.

Methodologically, the extension preserves the internal techno-economic architecture of OnSSET. The model continues to calculate settlement-level LCOEs for grid extension, solar mini-grids, and stand-alone systems, and technology assignment remains governed by conventional least-cost comparisons. In this sense, Climate-OnSSET does not alter the engineering logic of infrastructure selection. What it modifies is the spatial sequencing and motives of prioritization.

The framework introduces a Climate Priority Indicator constructed from two dimensions:

\[
ClimatePriority_i = Hazard_i \times Vulnerability_i
\]

where hazard reflects the spatial distribution of climate-related stressors such as droughts and heatwaves, and vulnerability captures limited adaptive capacity through indicators such as remoteness and relative deprivation.

Exposure is intentionally excluded from the indicator because population is already embedded endogenously within OnSSET through settlement demand, clustering, and population-based electrification targets. Including exposure again would therefore reproduce a structural double-counting of population and reinforce the tendency of least-cost models to privilege large urban settlements.


# Statement of Need

Universal electricity access is increasingly recognized not only as an infrastructure challenge, but also as a problem of resilience, spatial justice, and long-term adaptive capacity. Existing geospatial electrification planning frameworks, including the Open Source Spatial Electrification Tool (OnSSET), have substantially advanced the ability of planners and researchers to evaluate electrification pathways across large spatial scales. By integrating geospatial information, demographic projections, infrastructure costs, and technology-specific techno-economic assumptions, these models provide transparent and computationally tractable approaches for identifying least-cost electrification strategies.

However, the underlying logic of conventional electrification planning remains predominantly governed by techno-economic optimality. In standard OnSSET implementations, settlements are effectively prioritized according to economic attractiveness, where lower infrastructure costs, proximity to existing grid networks, and higher population densities tend to determine the sequencing of electrification. Such formulations implicitly assume that the principal objective of electrification planning is the minimization of aggregate system cost under predefined access targets.

This assumption becomes increasingly problematic under conditions of climate stress. Many of the populations that remain unelectrified are simultaneously among the most exposed to droughts, heatwaves, floods, and other climate-related hazards, while also possessing the lowest adaptive capacity. In such contexts, electricity access cannot be interpreted solely as an economic service. It also constitutes enabling infrastructure for climate adaptation through water access, cooling, healthcare provision, communication systems, food preservation, and productive resilience. A purely least-cost sequencing logic may therefore reproduce existing spatial inequalities by systematically postponing electrification in regions where electricity access may carry the highest social and adaptive value.

Climate-OnSSET addresses this gap by reframing electrification planning from a narrowly cost-minimizing exercise toward a resilience-oriented planning framework in which climate vulnerability and adaptive capacity influence who receives electricity access first, while least-cost principles continue to determine how electrification is technically implemented. The framework therefore provides a reproducible, extensible methodology for integrating climate-sensitive and equity-oriented considerations directly into geospatial electrification planning, without sacrificing the transparency and tractability of existing least-cost electrification models.

# Experiment Container Generation
The software outlined here, "expfactory," shares little with the original implementation beyond the name. Specifically, it allows for encapsulation of all dependencies and static files required for behavioral experimentation, and flexibility to the user for configuration of the deployment. For usage of a pre-existing experiment container, the user simply needs to run the Docker image. For generation of a new, custom container the generation workflow is typically the following:
 
 - **Selection** The user browses a [library](https://expfactory.github.io/experiments/) of available experiments, surveys, and games. A preview is available directly in the browser, and data saved to the local machine for inspection. The preview reflects exactly what will be installed into the container.
 - **Generation** The user selects one or more paradigms to add to the container, and clicks "Generate." The user runs the command shown in the browser on his or her local machine to produce the custom recipe for the container, called a Dockerfile.
 - **Building** The user builds the container (and optionally adds the Dockerfile to version control or automated building on Docker Hub) and uses it in production. The same container is then available for others that want to reproduce the experiment.

At runtime, the user is then able to select deployment customization such as database (MySQL, PostgreSQL, sqlite3, or default of filesystem), and a study identifier.


# Experiment Container Usage
Once a container is generated and it's unique identifier and image layers served in a registry like Docker Hub, it can be cited in a paper with confidence that others can run and reproduce the work simply by using it.

More information on experiment development and contribution to the expfactory tools, containers, or library is provided at the Experiment Factory  <a href="https://expfactory.github.io/expfactory/" target="_blank">official documentation</a>. This is an Open Source project, and so <a href="https://www.github.com/expfactory/expfactory/issues" target="_blank">feedback and contributions</a> are encouraged and welcome.

# References
