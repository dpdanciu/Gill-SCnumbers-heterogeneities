# Gill_SCnumbers-heterogeneities

This is the source code used for analysing data and performing simulations for the paper
"Identifying stem cell numbers and functional heterogeneities". All plots found in the paper have been produced
via this code. 

The code is written in Wolfram Mathematica, version 12.0. The notebook contains the following subsections:

1. Data adjustment: This section should only be performed once, so that the original dataset is adjusted in the form
required for the analysis and quantification. At the end, the final data are exported, and then it will be used in the 
following steps.
2. Function definitions: This section comprises all functions implemented by the user, for the goal of the project. 
This is an intialization cell, thus is run everytime if the kernel has been cleared.
3. Data import: Here the final data are imported. These are the adjusted data produced in the first section, so once
that section has been run once and the final data saved, in the following runs one must only import the existing final data.
This is an intialization cell, as the data must be imported everytime the kernel has been cleared.
4-5. Parameter estimation: This can be performed either using the algorithmic or the analytic approach (as explained
in the paper). In both cases, the program estimates the best values for parameters n and p, namely the number of stem
cells residing in the niche and the probability of division, respectively, i.e. the probability that the cell which has
just divided will divide again next. The estimation is performed by employing the Nelder-Mead method, within the 
minimization of the objective function (defined in section 2).
6. In silico data generation (homogeneous model): Here, 2 extreme scenarios are simulated - the stem cell model, in which 
one single stem cell is responsible for generating the entire mini-arch; and the progenitor model, in which each filament is 
produced by a different progenitor cell (i.e. 8 cells). Further, a homogeneous scenario with 2 stem cells is considered, where the two stem 
cells have equal probabilities of being selected for division, i.e. for filament generation.
7. In silico data generation (heterogeneous model): In this section, in silico data are generated based on the
parameter values obtained in from the estimation in section 4/5.
8. Parametric colour plots: Here a colour map of the objective function with respect to n and p is produced,
in order to get a general impression of the minima distributions.
9. Stacked plots (homogeneous model): The simulated data of the homogeneous model, produced in section 6, are plotted here with respect to 
the number of switches s (x-axis) and the number of labelled filaments f (colour code). Each bar shows the 
frequency of observing a certain number of switches in the data, and is split into parts of different colours to
assess how many filaments are labelled in each of these cases.
10-11. Stacked plots (heterogeneous model): In this section, plots similar to those in section 9 are produced. In addition,
here the experimental data are also plotted on the same graph, next to the simulated data, for comparison. The algorithmic
approach plots the frequency of observing a pair (s,f) of switches and labelled filaments in the data (D) and 
in the simulations (S) - the simulated data are the ones produced in section 7, based on the estimated parameters. The 
analytic approach skips the step of in silico data generation and directly computes the probabilities of 
observing a pair (s,f), instead of estimating it from a large simulated dataset.

Sections 2 and 3 are initialization cells and thus must be run everytime when the kernel has been cleared. 
The other sections should be run according to the goal.

----------------------------------------------------------------
     Copyright (C) 2019 Diana-Patricia Danciu
     Email: dpdanciu@math.uni-heidelberg.de

     This program is free software: you can redistribute it and/or modify
     it under the terms of the GNU General Public License as published by
     the Free Software Foundation, either version 3 of the License, or
     (at your option) any later version.

     This program is distributed in the hope that it will be useful,
     but WITHOUT ANY WARRANTY; without even the implied warranty of
     MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
     GNU General Public License for more details.

     You should have received a copy of the GNU General Public License
     along with this program.  If not, see <https://www.gnu.org/licenses/>.

