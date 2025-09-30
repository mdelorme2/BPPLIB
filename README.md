# BPPLIB – A Bin Packing Problem Library

The BPPLIB is a collection of codes, benchmarks, and links for the one-dimensional Bin Packing and Cutting Stock problem. 

If you need to refer to material taken from this library, please cite M. Delorme, M. Iori, and S. Martello. [BPPLIB: A library for bin packing and cutting stock problems](https://link.springer.com/article/10.1007/s11590-017-1192-z). *Optimization Letters*, 12(2):235-250, 2018.

This page maintained by M. Delorme (m.delorme[at]tilburguniversity[dot]edu), M. Iori (manuel.iori[at]unimore[dot]it), and S. Martello (silvano.martello[at]unibo[dot]it).

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

E.G. Coffman Jr., M.R. Garey, and D.S. Johnson. [Approximation algorithms for bin packing - an updated survey](https://link.springer.com/chapter/10.1007/978-3-7091-4338-4_3). In G. Ausiello, M. Lucertini, and P. Serafini, editors, *Algorithm Design for Computer System Design*, pages 49–106, Springer Vienna, 1984.

## Codes 

### Branch-and-bound

MTP is a branch-and-bound algorithm for the BPP proposed by S. Martello and P. Toth in [Knapsack Problems: Algorithms and Computer Implementations](https://silvano333.github.io/kp.html). John Wiley & Sons, Chichester, 1990. The code is not available online, but can be obtained at request from the authors.

BISON is a branch-and-bound algorithm for the BPP proposed by A. Scholl, R. Klein, and C. Jürgens in [Bison: a fast hybrid procedure for exactly solving the one-dimensional bin packing problem](https://www.sciencedirect.com/science/article/pii/S0305054896000822). *Computers & Operations Research*, 24(7):627-645, 1997. The code is not available online, but can be obtained at request from the authors.

The [CVRPSEP](https://sites.google.com/view/jens-lysgaard/cvrpsep) package is a collection of routines dedicated to the Capacitated Vehicle Routing Problem. One of them is a branch-and-bound algorithm, similar to MTP, specifically designed to solve the BPP. The package relies on [A new branch-and-cut algorithm for the capacitated vehicle routing problem](https://link.springer.com/article/10.1007/s10107-003-0481-8). *Mathematical Programming*, 100(2):423–445, 2004, by J. Lysgaard, A.N. Letchford, and R.W. Eglese.

### Branch-and-price

BELOV is a branch-and-cut-and-price algorithm for the CSP proposed by G. Belov and G. Scheithauer in [A branch-and-cut-and-price algorithm for one dimensional stock cutting and two-dimensional two-stage cutting](https://www.sciencedirect.com/science/article/pii/S0377221704006150). *European Journal of Operational Research*, 171(1):85–106, 2006. The code is not available online, but can be obtained at request from the authors.

[SCIP-BP](https://scipopt.org/scip/doc/html/BINPACKING_MAIN.php) is a branch-and-price algorithm for the BPP provided as an example when downloading the [SCIP Otimization Suite](https://www.scipopt.org/).

### Pseudo-polynomial formulations

[ONECUT](Codes/ONECUT.rar) is an algorithm based on a pseudo-polynomial formulation of the CSP solved throught an ILP solver. It uses the model proposed by H. Dyckhoff in [A new linear programming approach to the cutting stock problem](https://pubsonline.informs.org/doi/10.1287/opre.29.6.1092). *Operations Research*, 29(6):1092–1104, 1981.

[ARCFLOW](Codes/ARCFLOW.rar) is an algorithm based on a pseudo-polynomial formulation of the CSP solved throught an ILP solver. It uses the model proposed by J.M. Valério de Carvalho in [Exact solution of bin-packing problems using column generation and branch-and-bound](https://link.springer.com/article/10.1023/A:1018952112615). *Annals of Operations Research*, 86:629–659, 1999.

[DPLOW](Codes/DPFLOW.rar) is an algorithm based on a pseudo-polynomial formulation of the BPP solved throught an ILP solver. It uses the model proposed by H. Cambazard and B. O’Sullivan in [Propagating the bin packing constraint using linear programming](https://link.springer.com/chapter/10.1007/978-3-642-15396-9_13). *Principles and Practice of Constraint Programming–CP 2010*, pages 129–136. Springer, 2010.

[VPSolver](https://vpsolver.fdabrandao.pt/) is a software than can solve vector packing problems using pseudo-polynomial formulation. Limited to 1 dimension, this problem becomes a CSP. It relies on [Bin packing and related problems: General arc-flow formulation with graph compression](https://www.sciencedirect.com/science/article/pii/S0305054815002762). *Computers & Operations Research*, 69:56-67, 2016, by  F. Brandão and J.P. Pedroso. 

### Computer codes which appeared after the publication of the BPPLIB

IADA is an iterative aggregation/disaggregation algorithm to solve pseudo-polynomial network flow models with side constraints (including the BPP). It was proposed by F. Clautiaux, S. Hanafi, R. Macedo, M-E Voge, and C. Alves in [Iterative aggregation and disaggregation algorithm for pseudo-polynomial network flow models with side constraints](https://www.sciencedirect.com/science/article/pii/S0377221716308037). *European Journal of Operational Research*, 258(2):467–477, 2017. The code is not available online, but can be obtained at request from the authors.

[MIM](https://sites.google.com/view/jfcote/) is an algorithm based on an arc-flow formulation with Meet-in-the-Middle patterns and further reduction crieria, solved through an ILP solver (Cplex in the provided implementation). It was proposed by J. F. Côté and M. Iori in [The Meet-in-the-Middle Principle for Cutting and Packing Problems](https://pubsonline.informs.org/doi/10.1287/ijoc.2018.0806). *INFORMS Journal on Computing*, 30(4): 646-661, 2018.

[REFLECT](REFLECT.rar) is an algorithm based on a pseudo-polynomial formulation of the CSP solved through an ILP solver. It uses the model proposed by M. Delorme and M. Iori in [Enhanced Pseudo-Polynomial Formulations for Bin Packing and Cutting Stock Problem](https://pubsonline.informs.org/doi/10.1287/ijoc.2018.0880). *INFORMS Journal on Computing*, 32(1):101-119, 2020.

EXM is a branch-and-price-and-cut algorithm to solve the BPP. It was proposed by L. Wei, Z. Luo , R. Baldacci, and A. Lim in [A New Branch-and-Price-and-Cut Algorithm for One-Dimensional Bin-Packing Problems](https://pubsonline.informs.org/doi/10.1287/ijoc.2018.0867). *INFORMS Journal on Computing*, 32(2):428-443, 2020. The code is not available online, but can be obtained at request from the authors.

[VRPSolver](https://vrpsolver.math.u-bordeaux.fr/) is a branch-and-price-and-cut algorithm to solve the vehicle routing and other related problems (including the BPP). It uses the techniques proposed by A. Pessoa, R. Sadykov, E. Uchoa, and F. Vanderbeck in [A generic exact solver for vehicle routing and related problems](https://link.springer.com/article/10.1007/s10107-020-01523-z). *Mathematical Programming*, 183:483–523, 2020.

NF-F is a branch-and-price algorithm to solve pseudo-polynomial network flow models with strong relaxations (including the BPP). It uses the techniques proposed by V.L. de Lima, M. Iori, and F.K. Miyazawa in [Exact solution of network flow models with strong relaxations](https://link.springer.com/article/10.1007/s10107-022-01785-9). *Mathematical Programming*, 197:813–846, 2022. The code is not available online, but can be obtained at request from the authors.

[BCCF](https://github.com/stefanoconiglio/A-Numerically-Exact-Algorithm-for-the-Bin-Packing-Problem) is a numerically exact branch-and-price algorithm to solve the BPP. It uses the techniques proposed by R. Baldacci, S. Coniglio , J.-F. Cordeau , and F. Furini in [A Numerically Exact Algorithm for the Bin-Packing Problem](https://pubsonline.informs.org/doi/10.1287/ijoc.2022.0257). *INFORMS Journal on Computing*, 36(1): 141-162, 2023.

## Benchmarks

All instances are given in the two following formats:

- In the BPP format:
  - Number of items ($n$)
  - Capacity of the bins ($c$)
  - For each item $j (j = 1,...,n)$:
    - Weight ($w_j$)
​​
- In the CSP format:
​​  - Number of item types ($m$)
  - Capacity of the bins ($c$)
  - For each item type $j (j = 1,...,m)$:
    - Weight ($w_j$) and demand ($d_j$)​​

## Remarks, questions, suggestion

Please send an email to m.delorme[at]tilburguniversity[dot]edu
