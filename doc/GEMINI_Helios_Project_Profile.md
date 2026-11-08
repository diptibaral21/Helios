# Helios: 3D Crop Modeling for Environment-Aware Breeding

## What Is Helios?

Helios is an open-source, three-dimensional plant and canopy model developed at the University of California, Davis. It builds a virtual plant organ by organ, leaf by leaf, and simulates the biological and physical processes that take place inside and around each organ: how leaves expand and age, how sunlight is captured and turned into sugars through photosynthesis, how water moves through the plant and is lost through the stomata, and how carbon is partitioned among leaves, stems, roots, and grain. Because every process is grounded in physics and plant physiology, Helios is a mechanistic, whole-plant model. It contains the components a plant needs to grow and a canopy needs to develop. The result is a "digital twin" of a crop that grows in a realistic environment the way a real plant would. Researchers can change one factor at a time, such as a trait, a weather pattern, or a management practice, and see how the plant responds.

## The GEMINI Project

GEMINI is an international research project that brings together plant breeding, high-throughput phenotyping, and crop modeling to support smallholder farmers in Sub-Saharan Africa. It focuses on two staple crops of the region, sorghum and cowpea. Breeding sits at the center of the project. Breeders must judge how a variety will perform across the wide range of soils, climates, and farming practices in the region, known as genotype × environment × management (G×E×M) interactions, yet field trials can sample only a small share of these conditions. GEMINI combines field measurements with predictive modeling so breeders can estimate how a genotype will perform in places and seasons where it has not yet been tested. Helios is the modeling engine behind this effort.

## GEMINI Phase I: Linking Sensing and Simulation

Phase I established the proof of concept: field imagery of sorghum and cowpea could be turned into a calibrated virtual crop that predicts performance across environments.

**Functional-structural crop model:** Helios was developed into a functional-structural plant model for the GEMINI crops. It couples each plant's 3D architecture with physiological sub-models for light interception, photosynthesis, stomatal conductance, and leaf energy balance, so that structure and function are simulated together, leaf by leaf.

**Field-based calibration:** Crop-specific architecture models and leaf optical properties for cowpea and common bean were measured in GEMINI field experiments and built into Helios. This anchored the virtual plants in real measurements from the field.

**Image-based parameter estimation:** Ground-based robotic platforms and low-altitude drones imaged breeding plots at high resolution. Because Helios can render what a camera would see, simulated and real images could be compared directly. This allowed genotype-specific model parameters to be estimated from imagery at high throughput.

## GEMINI Phase II: Predicting Performance in New Environments

Breeders must decide which lines to cross, advance, and release long before those lines have been tested in most of the places farmers will grow them. In Phase II, the modeling team will build tools for predicting how specific sorghum and cowpea genotypes will perform across Sub-Saharan Africa, including under future climates. The work addresses two gaps identified in Phase I: predicting new genotypes in new environments, and predicting yield and stress tolerance. These tools will be delivered to partner breeding programs through the Helios user interface and the GEMINI App.

**Genotype-specific parameterization:** Each genotype will be described by a set of physiological parameters estimated from intensive ground and drone sensing at a small number of on-station sites: Kiboko in Kenya, IITA-Kano in Nigeria, and supporting sites in California. For traits that are difficult to capture in images, such as daylength sensitivity or node number, genomic information on known major-effect genes will help constrain these parameters. This way, every genotype carries a physiological "fingerprint" that can be applied in any environment.

**Linking canopy processes to yield:** Imagery reveals much about canopy growth but little about how yield is formed. Phase II will add a carbohydrate-dynamics module for sorghum and cowpea. It will track how sugars produced by photosynthesis are supplied, allocated, and remobilized between source organs (leaves and stems) and sink organs (pods, panicles, and grain) from vegetative growth through flowering and grain fill. The module will also represent how drought, heat around flowering, and nutrient limitation disrupt this balance. This links the canopy processes Helios already simulates to grain yield, seed weight, fodder yield, and yield stability under stress, which are the outcomes that determine a variety's value to farmers.

**Characterizing target populations of environments:** To predict performance anywhere, the model needs to know what "anywhere" looks like. Helios will be driven by high-resolution gridded weather and soil data (ERA5-Land, MERRA-2, IMERG, and iSDAsoil), checked against ground measurements from partner programs. Simulating crops across these data will help define the Target Population of Environments (TPE) each variety must serve and identify the factors that limit performance in each. Climate projections will extend this view about ten years ahead, so breeders can see how their target environments may shift.

**Validating in untested environments:** Predictions will be tested against multi-environment trials from regional sparse-testing networks, including PAT, ADCIN, and the West African cowpea regional trials, as well as managed-stress sites. Each prediction will carry a measure of uncertainty. Validation will focus on the most demanding case, new genotypes in new environments, where Phase I showed the largest gaps. The goal is predictions accurate enough to guide real decisions on crossing, advancement, and product placement.
