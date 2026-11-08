# Helios: 3D Crop Modeling for Environment-Aware Breeding

## Overview

Plant breeders face a hard question every season: how will a new variety perform in places where it has never been grown? Field trials can answer only part of it. They are slow and costly, and they cover only a small share of the environments farmers actually work in. This gap is especially wide in Sub-Saharan Africa, where smallholder farmers grow crops across very different soils, rainfall patterns, and temperatures, often with little margin for a poor harvest.

**Helios** is an open-source 3D biophysical modeling platform, developed at the University of California, Davis, that helps close this gap. Helios builds virtual plants, canopies, and whole fields in three dimensions and simulates the physical and physiological processes that drive crop growth: how leaves intercept sunlight, how they photosynthesize, how they exchange water and heat with the air around them, and how the plant looks to cameras and other sensors. Because these processes are represented mechanistically, grounded in physics and plant physiology rather than statistical patterns alone, Helios can link the traits of a specific genotype to the environment it grows in and predict how that genotype will respond to conditions it has not yet encountered.

Within the GEMINI project, Helios is the modeling engine that turns field measurements into forecasts breeders can act on.

## Key Features

- **Detailed 3D plant architecture.** Helios grows plants procedurally, organ by organ, through their development stages. Its built-in library covers a wide range of species, including the GEMINI crops sorghum and cowpea, so canopy structure reflects real differences in plant height, leaf angle, branching, and leaf area between genotypes.
- **Physics-based light modeling.** GPU-accelerated ray tracing computes how sunlight is absorbed, reflected, and scattered through the canopy, down to individual leaves. Leaf optical properties for cowpea and common bean were measured in GEMINI field experiments and are now part of the Helios species library.
- **Integrated physiology.** Coupled sub-models simulate photosynthesis, stomatal conductance, leaf energy balance, boundary-layer exchange, and plant hydraulics, so the model captures how carbon gain, water use, and leaf temperature respond together to weather.
- **Virtual sensing.** Helios can generate synthetic camera, LiDAR, and annotated imagery of simulated plants. This lets the model be compared directly with drone and ground-vehicle images from the field, and it supports training and calibrating image-analysis tools.
- **Parameter estimation.** Built-in optimization tools fit genotype-specific model parameters to observed data, turning raw phenotyping measurements into the physiological "fingerprint" of each variety.
- **Open and accessible.** Helios is free software with a C++ core, a Python interface (PyHelios), and a graphical interface. It runs on Linux, macOS, and Windows, and its documentation and tutorials are publicly available.

## Capacity and Scale

Helios works across scales, from a single leaf to an entire field plot, and it keeps the 3D detail that matters for light capture and canopy microclimate. Because it uses GPU computing, it can simulate thousands of plants and many weather scenarios in practical run times. That makes it possible to test a large number of genotype × environment × management (G×E×M) combinations virtually before committing land, labor, and seed to field trials.

## How Helios Is Used in GEMINI

In GEMINI, Helios connects three activities:

1. **Sensing.** Ground-based robotic platforms (Amiga/Rafiki) and low-altitude drones collect high-resolution images of breeding plots at on-station sites.
2. **Parameterizing.** These observations, together with manual measurements, are used to estimate genotype-specific parameters in Helios that describe how each variety builds its canopy and responds to its environment.
3. **Predicting.** The parameterized model is driven by local weather and soil data to forecast traits such as flowering time, grain quality, and yield in environments where the genotype has not been tested.

The result gives breeders a way to see how a candidate line is likely to perform across a region before it is planted there.

## What Makes Helios Novel

Most crop models describe the canopy as a uniform layer and rely on statistical relationships fitted to past trials. Helios takes a different approach. It represents the real 3D structure of individual plants and computes the underlying physics and physiology explicitly. This has three important consequences:

- **Better transfer to new conditions.** Mechanistic models can make reasonable predictions outside the range of the data they were calibrated on. This is essential when the goal is to predict untested genotypes in untested environments.
- **A direct link to imagery.** Because Helios can render what a camera or sensor would "see," model and field images can be compared directly. This simulation-to-reality ("Real2Syn") link allows physiological parameters to be estimated from images at high throughput.
- **Interpretable predictions.** Breeders can see why a genotype is predicted to perform well or poorly, for example because of limited light capture, water stress, or heat at flowering, rather than receiving a single unexplained number.

## Progress in GEMINI Phase I

GEMINI Phase I established the proof of concept for this approach. The team built and tested the full pipeline, from field sensing to parameter estimation to model prediction, for sorghum and cowpea. Ground and aerial phenotyping workflows were developed and deployed at partner sites, and Helios was extended with crop-specific architecture and leaf optical properties measured in GEMINI field experiments. Phase I showed that genotype parameters estimated from imagery can be used within Helios to predict performance across environments.

Phase I also identified clear priorities for the next step. Predictions remained hardest in the most demanding case, *new genotypes in new environments*. In addition, traits tied to yield formation proved difficult to estimate from imagery alone, and the model's treatment of abiotic stresses such as drought and heat needed further development.

## GEMINI Phase II: From Proof of Concept to Breeder-Ready Tools

GEMINI Phase II turns the Phase I results into an **operational, breeder-ready G×E×M prediction toolkit** for hybrid seed product development in sorghum and cowpea, serving smallholder farmers in Sub-Saharan Africa. The project addresses a central challenge in breeding: decisions about which lines to cross, advance, and release, and where to place new products, must often be made with sparse and noisy field data.

Phase II brings together three coordinated workstreams:

1. **High-throughput field phenotyping.** Ground-based and drone imagery are combined at on-station sites to estimate model parameters for many genotypes efficiently.
2. **Defining Target Populations of Environments (TPEs).** High-resolution soil and weather data are combined with crop modeling to map the environments a new variety must serve, guide where trials should be placed, and reveal which G×E×M factors limit performance.
3. **Delivering the tools.** The framework is packaged through the Helios user interface and the GEMINI App for routine use by partner breeding programs, including CIMMYT-Kenya, IITA-Kano, Makerere University, and ISRA/CERAAS-Senegal, as well as the ADCIN and West African cowpea regional networks.

Within this effort, Phase II advances Helios in two main directions:

- **Predicting in untested environments at regional scale.** Genotype parameters estimated at a small number of intensively sensed sites (Kiboko in Kenya, IITA-Kano in Nigeria, and supporting California sites) will be extended to locations across Sub-Saharan Africa. This uses gridded satellite and reanalysis data for weather and soils (such as ERA5-Land, MERRA-2, IMERG, and iSDAsoil), along with climate projections that give breeders a view of how target environments may shift over the next decade. Predictions will carry quantified uncertainty and will be tested against regional trial networks, with particular attention to new genotypes in new environments.
- **Modeling yield and stress tolerance mechanistically.** A new carbohydrate-dynamics module will track how sugars produced by photosynthesis are supplied, allocated, and remobilized between leaves, stems, and grain over the season. This links the canopy processes Helios already simulates to the outcomes breeders care about most: grain yield, seed weight, fodder yield in dual-purpose cowpea, and yield stability under drought, heat around flowering, and nutrient limitation. Genomic information and ground-truth harvest data will help constrain yield-related traits that are difficult to measure from images.

Phase II has measurable targets for predicting flowering time, grain protein, yield, and hybrid performance across diverse environment clusters. The goal is for model outputs to feed directly into the selection decisions of partner breeding programs. All results, software, and tools will be shared openly through publications and the public Helios and GEMINI App repositories, so that breeding programs across the region can use and build on them.
