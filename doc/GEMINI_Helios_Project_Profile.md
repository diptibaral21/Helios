# Helios: 3D Crop Modeling for Predictive Breeding

## Background

Breeding programs for sorghum and cowpea in Sub-Saharan Africa must make crossing, advancement, and product-placement decisions for genotypes that have not been evaluated in most of the environments where they will be grown. Multi-environment field trials cover a limited number of sites and generate sparse, noisy data, while the region encompasses a wide range of soils, rainfall regimes, temperatures, and management practices. Predictive tools that account for genotype × environment × management (G×E×M) interactions are therefore needed to extend inference beyond tested conditions.

## The Helios Modeling Platform

Helios is an open-source, three-dimensional plant simulation platform developed at the University of California, Davis. It represents plants explicitly at the organ level, leaf by leaf, and simulates the biophysical and physiological processes that govern growth. These include radiation transfer through the canopy, photosynthesis, stomatal conductance, leaf energy balance, plant hydraulics, and carbohydrate allocation among organs. As a mechanistic, whole-plant model, Helios links genotype-specific physiological traits to weather, soil, and management, enabling simulation of crop responses under conditions not represented in observed data. Helios also generates synthetic camera, LiDAR, and annotated imagery of simulated plants, allowing direct comparison with field sensing data. The platform is available as a C++ library with a Python interface (PyHelios) and a graphical user interface.

## GEMINI Phase I: Integration of Sensing and Simulation

GEMINI is a research project that integrates plant breeding, high-throughput phenotyping, and crop modeling in support of breeding programs serving smallholder farmers in Sub-Saharan Africa, with a focus on sorghum and cowpea. Phase I established the proof of concept for a sensing-to-prediction pipeline built on Helios.

**Crop-specific model development.** Architectural models for sorghum and cowpea were developed in Helios, and leaf optical properties for cowpea and common bean measured in GEMINI field experiments were incorporated into the platform.

**Image-based parameter estimation.** Breeding plots were imaged at high resolution using ground-based robotic platforms and low-altitude drones. Comparison of observed imagery with Helios-rendered synthetic imagery enabled high-throughput estimation of genotype-specific model parameters.

**Identified limitations.** Phase I identified two principal limitations. First, parameters associated with yield formation could not be reliably estimated from imagery, and the representation of abiotic-stress responses was less developed than the model's treatment of light interception, water use, and canopy architecture. Second, predictive ability was lowest for untested genotypes in untested environments.

## GEMINI Phase II: Breeder-Ready G×E×M Prediction

Phase II will convert the Phase I proof of concept into an operational G×E×M prediction toolkit for routine use by partner breeding programs. These include CIMMYT-Kenya, IITA-Kano, Makerere University, ISRA/CERAAS-Senegal, and the ADCIN and West African cowpea regional networks. The toolkit will be delivered through the Helios user interface and the GEMINI App. The modeling component addresses the Phase I limitations through two objectives.

### Yield and Abiotic-Stress Modeling

Helios includes a general carbohydrate budget that tracks carbon gained through photosynthesis and expended on growth and maintenance, with growth reduction and abortion of flowers and fruit under carbon limitation. This framework has been developed and tested primarily for perennial tree crops such as almond. Phase II will extend and calibrate it for the GEMINI crops, beginning with sorghum.

**Source–sink carbohydrate dynamics.** Assimilate supply, allocation, and remobilization between source organs (leaves and stems) and sink organs (panicles, pods, and grain) will be represented across vegetative growth, flowering, and grain fill, with genotype-specific allocation parameters.

**Stress effects on carbon balance.** Drought, photothermal stress around flowering, and nutrient limitation will be coupled to the carbohydrate balance to represent their effects on grain yield, seed weight, and yield stability.

**Parameterization of yield traits.** Yield-related parameters that cannot be estimated from imagery will be constrained using ground-truth yield and seed-weight data together with genomic information for traits with known major-effect loci, such as daylength sensitivity and node number.

**Validation.** Yield predictions will be evaluated against multi-environment trial data from on-station, regional, and managed-stress sites.

### Prediction in Untested Environments

Genotype parameters are estimated from intensive sensing at a limited number of on-station sites, including Kiboko (Kenya), IITA-Kano (Nigeria), and supporting sites in California. Phase II will extend these parameters to locations across Sub-Saharan Africa, with quantified uncertainty.

**Gridded environmental inputs.** Reanalysis and satellite products (ERA5-Land, MERRA-2, and IMERG) will supply radiation, temperature, humidity, and precipitation, and iSDAsoil will supply soil texture and fertility. These products will be benchmarked against ground-based weather and soil measurements from partner programs.

**Climate projections.** Historical reanalysis data will be adjusted using climate-scenario statistics to provide approximately ten-year projections of Target Population of Environments (TPE) structure.

**Input sensitivity analysis.** Perturbation experiments will quantify the precision of weather and soil inputs required to meet predictive targets for flowering time, grain protein, and yield.

**Validation across G×E scenarios.** Predictions will be evaluated for tested and untested genotypes in tested and untested environments, with emphasis on untested genotypes in untested environments. Data will come from sparse-testing networks including PAT, ADCIN, and the West African cowpea regional trials.

## Expected Outcomes

Phase II will provide a mechanistic, environment-aware framework for predicting yield and stress tolerance of sorghum and cowpea genotypes across Sub-Saharan Africa under current and projected climates. Model outputs will support selection-index workflows and decisions on crossing, advancement, and product placement. Models, software, and results will be released through open-access publications and the public Helios and GEMINI App repositories.
