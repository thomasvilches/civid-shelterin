ABM simulating shelter-in strategies against COVID-19. Presented on Work "Projecting the impact of Targeted Vaccination on COVID-19 Outbreaks in the United States". Authors:

This ABM is based on the one presented by Affan S. in the link
https://github.com/affans/covid19abm.jl

It was modified to include shelter-in strategies, masking, comorbidity and a age-based herd immunity previously calibrated.

In other to run the simulations enter in Julia and use either
include("simulations.jl"), if you wont use a cluster, or
include("simulations_cluster.jl"), if you will use a cluster (note that it is done using "Cluster manager" package and slurm).

After including the above, run simulations using
run_param(beta,isoscen,herd_im_v,mcv,nsims)

in which the arguments are
beta = the probability transmission (the default is 0.08 which generates 60% of Attack Rate without any kind of control)
isoscen = scenarios of shelter-in (description below)
herd_im_v  = integer vector with the percentage of herd immunity one wants to run. The possible values are 0, 5, 10, 20.
mcv = masking compliance
nsims = integer. Number of monte carlo simulations to be performed

The age distribution and vaccine coverage is set to USA reports.
Special attention to parameter fsevere. It is the probability that a severe individual isolate themselve, limiting their contacts to 3 per day. The default value is 1.0, but calibration must be performed to fsevere = 0.0.

"simlevel" files have the temporal dynamics of individual class they indicates, e.g. "simlevel_ded_inc_ag3.dat" stands for incidence of deads in age group 3. "prev" means prevalence.
hos = hospitalization, icu = icu hospitalization, lat = latent. It has a "heading"

isoscen description:

to be updated