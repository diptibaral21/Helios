# Predicting Crop Performance in Untested Environments in Sub-Saharan Africa

## Introduction

Let me start with a problem plant breeders face every season. A breeder working on sorghum or cowpea in Africa has to make big decisions. Which plants should I cross? Which lines should I keep? Where should I recommend this new variety to farmers? These choices shape what smallholder farmers will eventually grow.

The difficulty is that breeders almost never have the full picture. They have field trials, but only at a limited number of sites, and the data from those trials are sparse and noisy.

Yet the real question is always about the future: how will a variety that has never been tested perform in a place where it has never been grown?

Africa has a huge range of soils, rainfall, and temperatures. We cannot test every variety everywhere. This is the challenge GEMINI II takes on.

Instead of relying only on past trial results, we use Helios, a 3D crop model that links plant physiology, such as light capture, water use, and growth, to weather, soil, and management. Because it follows how a plant responds to light, heat, and water, it can reason about conditions it has never seen. The first phase of GEMINI showed this works as a proof of concept. Now we are turning it into a tool breeders can use routinely.

My PhD sits within this effort and has two parts. First, making Helios predict the outcomes that matter most to breeders and farmers, namely yield and stress tolerance. Second, making it predict in places we have never measured. I will take you through each part.

## Part 1: Predicting Yield and Stress Tolerance

The first part of my work starts with a limitation we know about in Helios today.

The model is already good at the physical side of the plant: how it captures light, how it uses water, and how its shape develops. What it does not yet capture well is how the plant turns that energy into yield. And the way the model responds to stress, such as drought or heat, is less developed than the rest.

Yet yield and stress tolerance are exactly what breeders and farmers care about most.

Helios already has a foundation for this. It includes a general carbohydrate budget that tracks the carbon each shoot gains from photosynthesis and spends on growth and maintenance. When carbon runs short, the model slows growth or drops flowers and fruit. So far, this has mostly been developed and tested on almond trees. But sorghum is a very different plant.

So my first job is to extend this framework and calibrate it for sorghum. This links what Helios already does well, photosynthesis, to the outcomes we need: grain yield, seed weight, and yield stability.

Next, we will connect stress, such as drought and heat, to this sugar balance, so the model can show how stress cuts into the carbon available for grain.

There is a practical problem, though. Some yield-related traits cannot be seen from a drone. For those, we will combine ground-truth yield data from research plots with genetic information, for traits where the genes involved are well known. That lets us estimate the model settings for each variety, even where imaging falls short.

Finally, we will test the yield predictions against data from multi-environment research trials.

After this part, the model predicts the right outcomes. But so far, it can only do that where we have measured the plant. Breeders need those predictions everywhere their varieties might be grown. That is my second part.

## Part 2: Predicting in Untested Environments

The second part of my work is about reach. The question is simple to state and hard to answer: if we have measured a plant carefully in a few places, how do we predict how it will behave in a place we have never visited?

We collect very detailed measurements at a few research sites, where drones and ground robots help us learn each variety's traits. But breeding programs work across a whole continent. So we need a way to carry what we learn at those few sites to anywhere in Sub-Saharan Africa, and to say honestly how uncertain each prediction is.

The solution is to feed Helios with environmental data that already cover the whole region. Satellite and global weather datasets give us temperature, sunlight, and rainfall, and a soil dataset gives us soil texture and fertility. We will plug these in as direct inputs. But we cannot simply trust them. So we will compare them with real weather and soil measurements collected by our partner programs, to learn where these datasets are reliable and where they are not.

Next, we will add climate projections. Breeders are choosing varieties that will be grown over the next decade, so they need to know how conditions may shift. We will adjust historical weather data using climate scenarios to give them a forward-looking view.

Then comes a question that is easy to overlook: how good do the input data have to be? We will run controlled experiments where we deliberately change the weather and soil inputs and see how much the predictions move. That tells us how precise the data must be to hit our targets for flowering time, grain protein, and yield.

Finally, we will test everything. We will check predictions in four situations: a known plant in a known place, a known plant in a new place, a new plant in a known place, and the hardest one, a new plant in a new place.

## Bringing It Together

Bringing the two parts together: the first makes Helios predict yield and stress tolerance, and the second lets it make those predictions across Africa. Combined, a breeder can ask, "How will this variety perform in that region, under stress?" and get an answer that can guide which crosses to make.
