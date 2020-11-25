# HIV-transmission-flow-sample
Code sample for the HIV transmission flow project

This repo includes some `Python` code for recovering HIV transmission flow between individuals using a multi-type Poisson process model with Dirichlet-Process hierarchical Gaussian mixture densities. 

The manuscript is still under writing so only a coarse description about the model is provided here.

The goal is to uncover the age pattern of HIV transmissions between heterosexual partners. For each male-female pair, we can acquire scores (between 0 and 1) that are computed from deep viral sequencing; those scores provide evidence on (1) how likely there is a transmission link between them, and (2) how likely the transmission direction is from the male to the female.

Using those pair-wise scores, we can build a model that has 3 layers of latent spatial Poisson processes on the age-by-age surface. The 3 layers represent 3 types of male-female pairs in the sample:

1. transmission from male to female
2. transmission from female to male
3. no tranmission between the pair

The density function for each Poisson process is modeled as a Gaussian mixture (with a hierarchical structure of the 3 processes), with Dirichlet process priors that allow us to have a flexible number of mixture components. 

A fully Bayesian inference scheme is implemented to estimate all parameters of this hierarchical model. There are two code scripts:

1. `main3.py`: the main module that defines the model and runs inference (on simulated data and realistic simulated data)
2. `utilsHupdate.py`: utility functions that will be imported into the main module

(**Note**: the "realistic" simulated dataset is proprietary so it's not included here.)
