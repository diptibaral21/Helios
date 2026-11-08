# Helios: 3D Crop Modeling for Environment-Aware Breeding

## What Is Helios?

Helios is an open-source, three-dimensional plant and canopy simulation platform developed at the University of California, Davis. It represents plants explicitly at the organ level and simulates the physical and physiological processes governing their growth, including leaf development and senescence, radiation interception, photosynthesis, stomatal regulation of transpiration, and carbon partitioning among organs. Grounded in physics and plant physiology, Helios functions as a mechanistic, whole-plant model capable of reproducing crop growth under realistic environmental conditions. Individual traits, weather variables, or management practices can be varied independently to quantify their effects on plant performance.

## The GEMINI Project

GEMINI is an international research initiative that integrates plant breeding, high-throughput phenotyping, and crop modeling to support smallholder agriculture in Sub-Saharan Africa, with a focus on sorghum and cowpea. Breeding decisions in the region depend on genotype × environment × management (G×E×M) interactions across highly diverse soils, climates, and farming systems, yet field trials sample only a small fraction of these conditions. GEMINI combines field observations with mechanistic modeling to predict genotype performance in untested locations and seasons, with Helios serving as the core modeling platform.

## GEMINI Phase I: Linking Sensing and Simulation

Phase I established a proof of concept demonstrating that field imagery of sorghum and cowpea can be translated into calibrated virtual crops capable of predicting performance across environments.

**Functional-structural crop model:** Helios was adapted as a functional-structural plant model for the GEMINI crops, coupling 3D plant architecture with physiological sub-models for light interception, photosynthesis, stomatal conductance, and leaf energy balance at the individual-leaf scale.

**Field-based calibration:** Crop-specific architectural models, together with leaf optical properties for cowpea and common bean measured in GEMINI field experiments, were incorporated into Helios to anchor simulations in empirical observations.

**Image-based parameter estimation:** High-resolution imagery of breeding plots was acquired using ground-based robotic platforms and low-altitude drones. Direct comparison of observed imagery with Helios-rendered synthetic imagery enabled high-throughput estimation of genotype-specific model parameters.

## GEMINI Phase II: Predicting Performance in New Environments

Crossing, advancement, and release decisions are typically made before candidate lines have been evaluated in most of their target environments. Phase II will develop tools to predict the performance of sorghum and cowpea genotypes across Sub-Saharan Africa under current and projected climates. This work addresses two limitations identified in Phase I: prediction for untested genotypes in untested environments, and prediction of yield and stress tolerance. The resulting tools will be delivered to partner breeding programs through the Helios user interface and the GEMINI App.

**Genotype-specific parameterization:** Genotypes will be characterized by physiological parameters estimated from intensive ground and aerial sensing at on-station sites in Kiboko (Kenya), IITA-Kano (Nigeria), and California. Parameters for traits not readily captured in imagery, such as daylength sensitivity and node number, will be constrained using genomic information on known major-effect loci.

**Linking canopy processes to yield:** A carbohydrate-dynamics module will be developed for sorghum and cowpea to represent assimilate supply, allocation, and remobilization between source organs (leaves and stems) and sink organs (panicles, pods, and grain) from vegetative growth through grain fill. The module will incorporate the effects of drought, photothermal stress at flowering, and nutrient limitation, linking simulated canopy processes to grain yield, seed weight, fodder yield, and yield stability.

**Characterizing target populations of environments:** Helios will be driven by high-resolution gridded weather and soil datasets (ERA5-Land, MERRA-2, IMERG, and iSDAsoil), benchmarked against ground measurements from partner programs. Large-scale simulations will delineate the Target Populations of Environments (TPEs) and identify the factors limiting performance within each, while climate projections will extend this characterization approximately ten years into the future.

**Validating in untested environments:** Predictions, accompanied by quantified uncertainty, will be evaluated against multi-environment trial data from regional sparse-testing networks, including PAT, ADCIN, and the West African cowpea regional trials, as well as managed-stress sites. Particular emphasis will be placed on untested genotypes in untested environments, with the objective of achieving predictive accuracy sufficient to inform crossing, advancement, and product-placement decisions.
