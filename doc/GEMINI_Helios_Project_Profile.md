# Helios: Predicting Crop Performance Where It Has Never Been Tested

## The Breeder's Dilemma

Every season, plant breeders working on sorghum and cowpea in Sub-Saharan Africa make decisions that shape what smallholder farmers will eventually grow: which parents to cross, which lines to advance, and where a new variety should be recommended for release. These decisions rest on a question about the future. How will a variety that has never been tested perform in a place where it has never been grown?

Field trials can answer only part of this question. They are conducted at a limited number of sites, they are costly to run, and the data they produce are often sparse and noisy. Meanwhile, the region spans an enormous range of soils, rainfall regimes, and temperatures, and farmers manage their crops in very different ways. Testing every variety in every environment is not possible. Breeders therefore need a way to reason beyond the trials they have, and to anticipate how genotype, environment, and management (G×E×M) will interact in places they have not yet sampled.

## A Virtual Crop Grounded in Physiology

Helios, an open-source three-dimensional plant simulation platform developed at the University of California, Davis, provides that capability. Rather than relying on statistical patterns from past trials, Helios builds a virtual plant organ by organ and leaf by leaf, and simulates the processes that drive its growth. Sunlight is traced through the canopy to every leaf. Photosynthesis converts that light into sugars. Stomata regulate the exchange of water and carbon dioxide with the air. Leaf energy balance sets leaf temperature, and a carbohydrate budget governs how carbon is partitioned among the plant's organs. Because each process is grounded in physics and plant physiology, Helios functions as a mechanistic, whole-plant model, a digital counterpart of a real crop growing in a real environment.

This mechanistic foundation is what allows Helios to reason about new conditions. A model that follows how a plant responds to light, heat, and water can be asked how that plant would respond to a different climate, soil, or management practice. Researchers can change one factor at a time and observe the consequences for growth and performance.

## GEMINI Phase I: Connecting the Field to the Model

The GEMINI project brings together plant breeding, high-throughput phenotyping, and crop modeling to support breeding programs serving smallholder farmers in Sub-Saharan Africa. In its first phase, GEMINI set out to show that Helios could connect what is observed in the field to what can be predicted by simulation.

The team adapted Helios to the GEMINI crops by developing architectural models for sorghum and cowpea and incorporating leaf optical properties measured in GEMINI field experiments. Breeding plots were then imaged at high resolution by ground-based robotic platforms and low-altitude drones. Because Helios can render what a camera would see, simulated and observed images could be compared directly. This simulation-to-reality link made it possible to estimate genotype-specific model parameters from imagery at high throughput, so each variety could be represented in the model by its own physiological characteristics. Phase I thereby established a working proof of concept: a pipeline running from field sensing, to a calibrated virtual crop, to predictions of performance across environments.

## What Phase I Revealed

The proof of concept also clarified where the approach needed to mature. Helios proved strong in representing the physical side of the plant, including light capture, water use, and canopy development. It was less developed in two areas that matter most to breeders.

The first concerns yield. Imagery reveals a great deal about canopy growth but little about how a plant converts captured energy into grain, and the model's response to abiotic stresses such as drought and heat lagged behind the rest of its physiology. Yet yield and its stability under stress are precisely the outcomes that determine a variety's value to farmers.

The second concerns reach. Predictions were most reliable where a genotype or an environment had already been observed, and weakest in the case breeders face most often: a new genotype in a new environment. Detailed measurements can be collected at only a few research stations, while breeding programs operate across an entire continent.

## GEMINI Phase II: From Proof of Concept to Breeder-Ready Prediction

GEMINI Phase II addresses these two limitations directly. Its aim is to transform the Phase I pipeline into an operational G×E×M prediction toolkit that partner breeding programs can use routinely, delivered through the Helios user interface and the GEMINI App. Partners include CIMMYT-Kenya, IITA-Kano, Makerere University, ISRA/CERAAS-Senegal, and the ADCIN and West African cowpea regional networks. Within this effort, the modeling work proceeds along two complementary lines: first, ensuring that Helios predicts the right outcomes, and second, ensuring that it can predict them wherever they are needed.

### From Canopy Processes to Yield and Stress Tolerance

Helios already contains the foundation for modeling yield. Its general carbohydrate budget tracks the carbon each shoot gains through photosynthesis and spends on growth and maintenance. When carbon runs short, the model slows growth or sheds flowers and fruit. This framework, however, has been developed and tested primarily on perennial tree crops such as almond, and annual grain crops allocate their resources very differently.

Phase II will extend and calibrate this framework for the GEMINI crops, beginning with sorghum. The model will track how sugars produced in source organs (leaves and stems) are allocated and later remobilized to sink organs (panicles, pods, and grain) through vegetative growth, flowering, and grain fill. This creates a mechanistic bridge from the processes Helios already simulates well to the outcomes breeders need: grain yield, seed weight, and yield stability. Abiotic stresses, including drought, heat around flowering, and nutrient limitation, will then be coupled to this carbon balance, so the model can represent how stress reduces the carbon available for grain.

Some yield-related traits cannot be observed from a drone. For these, ground-truth yield and seed-weight data from research plots will be combined with genomic information for traits governed by well-characterized genes, such as daylength sensitivity and node number. This allows model parameters to be estimated for each variety even where imaging falls short. Yield predictions will be validated against multi-environment trial data from on-station, regional, and managed-stress sites.

### From a Few Research Sites to an Entire Region

Predicting the right outcomes is necessary but not sufficient. Breeders need those predictions across every environment in which their varieties may be grown. Genotype parameters are estimated through intensive sensing at a small number of research stations, including Kiboko in Kenya, IITA-Kano in Nigeria, and supporting sites in California. Phase II will develop the means to carry this knowledge to any location in Sub-Saharan Africa, with an honest account of how uncertain each prediction is.

To do so, Helios will be driven by environmental datasets that already span the region: satellite and global reanalysis products for temperature, solar radiation, humidity, and rainfall (ERA5-Land, MERRA-2, and IMERG), and a high-resolution soil dataset for texture and fertility (iSDAsoil). Because these datasets cannot be trusted uncritically, they will be benchmarked against weather and soil measurements collected by partner programs, establishing where they are reliable and where they are not.

Because varieties released today will be grown over the coming decade, historical weather records will be adjusted using climate-scenario projections, giving breeders a forward-looking view of how their Target Populations of Environments may shift. Controlled sensitivity experiments, in which weather and soil inputs are deliberately perturbed, will then determine how precise these inputs must be to meet the project's predictive targets for flowering time, grain protein, and yield.

Finally, predictions will be validated across all four combinations of genotype and environment: a known genotype in a known environment, a known genotype in a new environment, a new genotype in a known environment, and, most demanding of all, a new genotype in a new environment. These tests draw on regional sparse-testing networks, including PAT, ADCIN, and the West African cowpea regional trials.

## Toward Decisions Breeders Can Act On

Together, these advances give Helios both depth and reach. The first makes the model predict yield and stress tolerance. The second allows those predictions to extend across Sub-Saharan Africa and into future climates. Combined, they allow a breeder to ask, "How will this variety perform in that region, under stress?" and receive an answer grounded in plant physiology that can guide which crosses to make, which lines to advance, and where new varieties should be placed. All models, software, and results will be shared openly through publications and the public Helios and GEMINI App repositories.
