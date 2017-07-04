# Undergraduate Research

## Motivation
As an undergraduate at Harvey Mudd College, I had the opportunity to participate in academic research during my junior and senior years. My group researched gas-permeable polymer membranes. Chemical separation processes account for a large fraction of the nation's energy consumption. Semi-permeable membranes are therefore attractive as a low-cost, energy-efficient method for separating gas mixtures. However, there has traditionally been a tradeoff between a membrane's permeability, which dictates the flow rate across it, and its selectivity, which determines how well it is able to allow the desired gas(es) through while blocking the unwanted gas(es). But [recent research](http://pubs.acs.org/doi/full/10.1021/cm020672j) has discovered that incorporating nanoparticles into certain polymers increases their permeability without sacrificing selectivity. My group sought to explain the underlying cause for this phenomenon and characterize it across a wider selection of nanoparticle and polymer types.

<figure>
    <img class="centered" src="/media/permeationChamber.png" alt="Permeation testing setup" style="width: 90%;">
    <figcaption>Permeation testing apparatus. Gas flows in from the top right, through the sample chamber on the left, and out through the bottom right. Two pressure transducers measure the pressure on either side of the sample chamber.</figcaption>
</figure>

## My Role
My responsibilities were twofold: I constructed and ran molecular computer simulations, while also performing gas permeation experiments on the polymer membranes we synthesized. The goal of the simulations was to first recreate the experimental results mentioned above and then use the models to understand the interactions between the polymer and nanoparticles at the atomic level. The construction of each model involves a significant degree of pseudorandomness, meaning there is a large amount of variance from one model to the next. We therefore created and ran many different simulations to build up a distribution that we could compare to experimental results.

<figure>
    <img class="centered" src="/media/polymerModel.png" alt="Screenshot of polymer model" style="width: 70%;">
    <figcaption>Molecular model showing polymer chains (black and gray) and nitrogen molecules (blue, enlarged for visibility).</figcaption>
</figure>

## Results
In addition to running numerous simulations, I improved the way we analyzed the results of each simulation. Previously, we had been discarding a large portion of the data due to strict thresholding, i.e. if a portion of the data didn't meet a certain requirement, it was ignored. This had the effect of dramatically reducing our sample size when analyzing each simulation. I replaced this logic with a more detailed approach that included a much larger fraction of the dataset, thereby increasing our confidence in each the analysis of each individual model. By increasing the quality of our analysis, we were able to build up confidence in our results over fewer simulations, essentially making our computation time more efficient. I also wrote a grant proposal for additional computational resources from Amazon Web Services through their [Cloud Credits for Research](https://aws.amazon.com/grants/) program. The proposal was accepted, which increased our computing power by an order of magnitude.
