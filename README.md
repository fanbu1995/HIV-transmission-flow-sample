# HIV-transmission-flow-sample
Code sample for the HIV transmission flow project

This repo includes some Python code for recovering HIV transmission flow between individuals using a multi-type Poisson process model with Dirichlet-Process hierarchical Gaussian mixture densities. 

The manuscript is still under writing so only a coarse description about the model is provided here.

The goal is to uncover the age pattern of HIV transmissions between heterosexual partners. For each female-male pair, we can acquire scores (between 0 and 1) that are computed from deep viral sequencing; those scores provide evidence on (1) how likely there is a transmission link between them, and (2) how likely the transmission direction is from the male to the female.

Using those pair-wise scores, we can build a model that has 3 layers of latent spatial Poisson processes on the age-by-age surface. 
