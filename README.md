# BPPLIB – A Bin Packing Problem Library

The BPPLIB is a collection of codes, benchmarks, and links for the one-dimensional Bin Packing and Cutting Stock problem. 

If you need to refer to material taken from this library, please cite M. Delorme, M. Iori, and S. Martello. [BPPLIB: A library for bin packing and cutting stock problems](https://link.springer.com/article/10.1007/s11590-017-1192-z). *Optimization Letters*, 12(2):235-250, 2018.

This page maintained by M. Delorme (m.delorme@tilburguniversity.edu), M. Iori (manuel.iori@unimore.it), and S. Martello (silvano.martello@unibo.it).

## Problem description

The bin packing problem (BPP) can be informally defined in a very simple way. We are given $n$ items, each having an integer weight $w_j (j = 1, ..., n)$, and an unlimited number of identical bins of integer capacity $c$. The objective is to pack all the items into the minimum number of bins so that the total weight packed in any bin does not exceed the capacity.

Similarly, in the cutting stock problem (CSP), we are given $m$ item types, each having an integer weight $w_j$ and an integer demand $d_j (j = 1, ..., m)$, and an unlimited number of identical bins (frequently called rolls in the literature) of integer capacity $c$. The objective is to produce $d_j$ copies of each item type $j$ using the minimum number of bins so that the total weight packed in any bin does not exceed its capacity. A CSP instance can be easily transformed into an equivalent BPP instance and vice-versa.

For a recent survey on these problems, see M. Delorme, M. Iori, and S. Martello. [Bin Packing and Cutting Stock Problems: Mathematical Models and Exact Algorithms](https://www.sciencedirect.com/science/article/pii/S0377221716302491). *European Journal of Operational Research*, 255(1):1–20, 2016.

## Previous surveys on the BPP and the CSP

E.G. Coffman Jr., J. Csirik, G. Galambos, S. Martello, and D. Vigo. [Bin packing approximation algorithms: Survey and classification](https://link.springer.com/rwe/10.1007/978-1-4419-7997-1_35). In P.M. Pardalos, D.-Z. Du, and R.L. Graham, editors, *Handbook of Combinatorial Optimization*, pages 455-531, Springer New York, 2013.

G. Wäscher, H. Haußner, and H. Schumann. [An improved typology of cutting and packing problems](https://www.sciencedirect.com/science/article/pii/S037722170600292X). *European Journal of Operational Research*, 183(3):1109–1130, 2007.

J.M. Valério de Carvalho. [LP models for bin packing and cutting stock problems](https://www.sciencedirect.com/science/article/pii/S0377221702001248). *European Journal of Operational Research*, 141(2):253–273, 2002.

P.E. Sweeney and E.R. Paternoster. [Cutting and packing problems: a categorized, application-orientated research bibliography](https://www.tandfonline.com/doi/abs/10.1057/jors.1992.101). *Journal of the Operational Research Society*, pages 691–706, 1992.

R.W. Haessler and P.E. Sweeney. [Cutting stock problems and solution procedures](https://www.sciencedirect.com/science/article/pii/0377221791902935). *European Journal of Operational Research*, 54(2):141–150, 1991. 

H. Dyckhoff. [A typology of cutting and packing problems](http://sciencedirect.com/science/article/pii/037722179090350K). *European Journal of Operational Research*, 44(2):145–159, 1990.

E.G. Coffman Jr., M.R. Garey, and D.S. Johnson. [Approximation algorithms for bin packing - an updated survey]. In G. Ausiello, M. Lucertini, and P. Serafini, editors, *Algorithm Design for Computer System Design*, pages 49–106, Springer Vienna, 1984.

## Codes 

### Branch-and-bound

MTP is a branch-and-bound algorithm for the BPP proposed by S. Martello and P. Toth in [Knapsack Problems: Algorithms and Computer Implementations](https://silvano333.github.io/kp.html). John Wiley & Sons, Chichester, 1990.

BISON is a branch-and-bound algorithm for the BPP proposed by A. Scholl, R. Klein, and C. Jürgens in [Bison: a fast hybrid procedure for exactly solving the one-dimensional bin packing problem](https://www.sciencedirect.com/science/article/pii/S0305054896000822). *Computers & Operations Research*, 24(7):627-645, 1997. The code is not available online, but can be obtained at request from the authors.

The CVRPSEP package is a collection of routines dedicated to the Capacitated Vehicle Routing Problem. One of them is a branch-and-bound algorithm, similar to MTP, specifically designed to solve the BPP. The package relies on [A new branch-and-cut algorithm for the capacitated vehicle routing problem](https://link.springer.com/article/10.1007/s10107-003-0481-8). *Mathematical Programming*, 100(2):423–445, 2004, by J. Lysgaard, A.N. Letchford, and R.W. Eglese.

### Branch-and-price

BELOV is a branch-and-cut-and-price algorithm for the CSP proposed by G. Belov and G. Scheithauer in [A branch-and-cut-and-price algorithm for one dimensional stock cutting and two-dimensional two-stage cutting](https://www.sciencedirect.com/science/article/pii/S0377221704006150). *European Journal of Operational Research*, 171(1):85–106, 2006.

SCIP-BP is a branch-and-price algorithm for the BPP provided as an example when downloading the [SCIP Otimization Suite](https://www.scipopt.org/).

### Pseudo-polynomial formulations

For the codes implemented by ourself, we propose a version requiring the commercial ILP solver Cplex.

ONECUT is an algorithm based on a pseudo-polynomial formulation of the CSP solved throught an ILP solver. It uses the model proposed by H. Dyckhoff in [A new linear programming approach to the cutting stock problem](https://pubsonline.informs.org/doi/10.1287/opre.29.6.1092). *Operations Research*, 29(6):1092–1104, 1981.

ARCFLOW is an algorithm based on a pseudo-polynomial formulation of the CSP solved throught an ILP solver. It uses the model proposed by J.M. Valério de Carvalho in [Exact solution of bin-packing problems using column generation and branch-and-bound](https://link.springer.com/article/10.1023/A:1018952112615). *Annals of Operations Research*, 86:629–659, 1999.

DPLOW is an algorithm based on a pseudo-polynomial formulation of the BPP solved throught an ILP solver. It uses the model proposed by H. Cambazard and B. O’Sullivan in [Propagating the bin packing constraint using linear programming](https://link.springer.com/chapter/10.1007/978-3-642-15396-9_13). *Principles and Practice of Constraint Programming–CP 2010*, pages 129–136. Springer, 2010.

[VPSolver](https://vpsolver.fdabrandao.pt/) is a software than can solve vector packing problems using pseudo-polynomial formulation. Limited to 1 dimension, this problem becomes a CSP. It relies on [Bin packing and related problems: General arc-flow formulation with graph compression](https://www.sciencedirect.com/science/article/pii/S0305054815002762). *Computers & Operations Research*, 69:56-67, 2016, by  F. Brandão and J.P. Pedroso. 

### Computer codes which appeared after the publication of the BPPLIB

IADA is an iterative aggregation/disaggregation algorithm to solve pseudo-polynomial network flow models with side constraints (including the BPP). It was proposed by F. Clautiaux, S. Hanafi, R. Macedo, M-E Voge, and C. Alves in [Iterative aggregation and disaggregation algorithm for pseudo-polynomial network flow models with side constraints](https://www.sciencedirect.com/science/article/pii/S0377221716308037). *European Journal of Operational Research*, 258(2):467–477, 2017. 

[MIM](https://sites.google.com/view/jfcote/) is an algorithm based on an arc-flow formulation with Meet-in-the-Middle patterns and further reduction crieria, solved through an ILP solver (Cplex in the provided implementation). It was proposed by J. F. Côté and M. Iori in [The Meet-in-the-Middle Principle for Cutting and Packing Problems](https://pubsonline.informs.org/doi/10.1287/ijoc.2018.0806). *INFORMS Journal on Computing*, 30(4): 646-661, 2018.

[REFLECT](https://github.com/mdelorme2/Extending-the-reflect-flow-formulation-to-variable-sized-1D-cutting-and-skiving-stock-problems/tree/main/1_CSP-SSP/3_REFLECT) is an algorithm based on a pseudo-polynomial formulation of the CSP solved through an ILP solver. It uses the model proposed by M. Delorme and M. Iori in [Enhanced Pseudo-Polynomial Formulations for Bin Packing and Cutting Stock Problem](https://pubsonline.informs.org/doi/10.1287/ijoc.2018.0880). *INFORMS Journal on Computing*, 32(1):101-119, 2020.

EXM is a branch-and-price-and-cut algorithm to solve the BPP. It was proposed by L. Wei, Z. Luo , R. Baldacci, and A. Lim in [A New Branch-and-Price-and-Cut Algorithm for One-Dimensional Bin-Packing Problems](https://pubsonline.informs.org/doi/10.1287/ijoc.2018.0867). *INFORMS Journal on Computing*, 32(2):428-443, 2020.

[VRPSolver](https://vrpsolver.math.u-bordeaux.fr/) is a branch-and-price-and-cut algorithm to solve the vehicle routing and other related problems (including the BPP). It uses the techniques proposed by A. Pessoa, R. Sadykov, E. Uchoa, and F. Vanderbeck in [A generic exact solver for vehicle routing and related problems](https://link.springer.com/article/10.1007/s10107-020-01523-z). *Mathematical Programming*, 183:483–523, 2020.

NF-F is a branch-and-price algorithm to solve certain packing problems (including the BPP). It uses the techniques proposed by V.L. de Lima, M. Iori, and F.K. Miyazawa in [Exact solution of network flow models with strong relaxations](https://link.springer.com/article/10.1007/s10107-022-01785-9). *Mathematical Programming*, 197:813–846, 2022.

[BCCF](https://github.com/stefanoconiglio/A-Numerically-Exact-Algorithm-for-the-Bin-Packing-Problem) is a numerically exact branch-and-price algorithm to solve the BPP. It uses the techniques proposed by R. Baldacci, S. Coniglio , J.-F. Cordeau , and F. Furini in [A Numerically Exact Algorithm for the Bin-Packing Problem](https://pubsonline.informs.org/doi/10.1287/ijoc.2022.0257). *INFORMS Journal on Computing*, 36(1): 141-162, 2023.

## Folder organization

The different folders correspond to the following methods in our paper:

| Folder  | Name used in the paper |
| ------------- | ------------- |
| 1_CYCLE | CF+NONE |
| 1_CYCLE2 | CF+1RA |
| 1_CYCLE3 | CF+PICORA |
| 1_CYCLE3LP | CF+PICORA+RCVF |
| 3_EEF | EEF+NONE |
| 3_EEF2 | EEF+1RA |
| 3_EEF3 | EEF+PICORA |
| 3_EEF3LP | EEF+PICORA+RCVF |
| 4_PIEF | PIEF+NONE |
| 4_PIEF2 | PIEF+1RA |
| 4_PIEF3 | PIEF+PICORA |
| 4_PIEF3LP | PIEF+PICORA+RCVF |
| 5_HCF | HCF+NONE |
| 5_HCF2 | HCF+1RA |
| 5_HCF3 | HCF+PICORA |
| 5_HCF3LP | HCF+PICORA+RCVF |
| CHAINS/1_CYCLE3LP_CHAIN1 | CF+PICORA+DPICEF+RCVF |
| CHAINS/1_CYCLE3LP_CHAIN3 | CF+PICORA+IPICEFTH4+RCVF |
| HCA/1_CYCLE_HCA | CF-HCA |
| HCA/1_CYCLE3_HCA | CF-VG+PICORA-CG |

## Code description

All algorithms are coded in C++ and part of our methods require the commercial solver Gurobi (we used version 11.0.2). The files have the following contents:

| Name  | Description |
| ------------- | ------------- |
| Allocation.cpp | contains a number of secondary functions (this file is usually the same for each subfolder)  |
| Allocation.h | header file corresponding to Allocation.cpp (this file is usually the same for each subfolder)  |
| main.cpp | front-end code for using the method  |
| main.h | header file corresponding to main.cpp  |
| makefile | used for compiling under linux (it needs to be updated by the user)  |
| time.cpp | generic file used to measure the computation time  |
| time.h | header file corresponding to time.cpp  |

## Running the software

Once compiled, the following command can be used to run the algorithm:
- ./PROGRAM "./PATH_INSTANCE" "NAME_INSTANCE" "./PATH_AND_NAME_OUTPUT_GENERAL" "K" "B" for the 16 first approaches
- ./PROGRAM "./PATH_INSTANCE" "NAME_INSTANCE" "./PATH_AND_NAME_OUTPUT_GENERAL" "K" "L" "B" for the next 2 approaches
- ./PROGRAM "./PATH_INSTANCE" "NAME_INSTANCE" "./PATH_AND_NAME_OUTPUT_GENERAL" "K" "B" "P" "S" for the last 2 approaches

where

- PROGRAM is the name of the compiled software 
- ./PATH_INSTANCE is the relative path of the folder where the instance to solve is located
- NAME_INSTANCE is the name of the instance to solve
- ./PATH_AND_NAME_OUTPUT_GENERAL is the name of the file (together with its relative path) where performance metrics (such as the optimality status, the CPU time required, or the number of variables) are stored after solving an instance
- K is the maximum cycle size
- L is the maximum chain length (only for the models allowing chains)
- B is the maximum number of reserve arcs allowed 
- P is the probability for an arc that is not compatible to be half-compatible (only for the models considering half-compatible arcs)
- S is the random seed (only for the models considering half-compatible arcs)

## Details of instances
Moreover, "CHAINS/_INPUT.rar" contains a txt-file for the newly generated test instances. 
See "https://wpettersson.github.io/kidney-webapp/#/" for a detailed explanation of the generated instance files.

## Ongoing Development

This code is being developed on an on-going basis at the author's
[GitHub site](https://github.com/mdelorme2/Mathematical_models_and_exact_algorithms_for_kidney_exchange_problems_with_immunosuppressants).

## Support

For support in using this software, submit an
[issue](https://github.com/mdelorme2/Mathematical_models_and_exact_algorithms_for_kidney_exchange_problems_with_immunosuppressants/issues/new).
