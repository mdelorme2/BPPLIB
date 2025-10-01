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

MTP is a branch-and-bound algorithm for the BPP proposed by S. Martello and P. Toth in [Knapsack Problems: Algorithms and Computer Implementations](https://silvano333.github.io/kp.html). John Wiley & Sons, Chichester, 1990. The code is not available online, but it can be obtained from the authors upon request.

BISON is a branch-and-bound algorithm for the BPP proposed by A. Scholl, R. Klein, and C. Jürgens in [Bison: a fast hybrid procedure for exactly solving the one-dimensional bin packing problem](https://www.sciencedirect.com/science/article/pii/S0305054896000822). *Computers & Operations Research*, 24(7):627-645, 1997. The code is not available online, but it can be obtained from the authors upon request.

The CVRPSEP package is a collection of routines dedicated to the Capacitated Vehicle Routing Problem. One of them is a branch-and-bound algorithm, similar to MTP, specifically designed to solve the BPP. The package relies on [A new branch-and-cut algorithm for the capacitated vehicle routing problem](https://link.springer.com/article/10.1007/s10107-003-0481-8). *Mathematical Programming*, 100(2):423–445, 2004, by J. Lysgaard, A.N. Letchford, and R.W. Eglese. The code is available on an [external website](https://sites.google.com/view/jens-lysgaard/cvrpsep).

### Branch-and-price

BELOV is a branch-and-cut-and-price algorithm for the CSP proposed by G. Belov and G. Scheithauer in [A branch-and-cut-and-price algorithm for one dimensional stock cutting and two-dimensional two-stage cutting](https://www.sciencedirect.com/science/article/pii/S0377221704006150). *European Journal of Operational Research*, 171(1):85–106, 2006. The code is not available online, but it can be obtained from the authors upon request.

SCIP-BP is a branch-and-price algorithm for the BPP provided as an example when downloading the [SCIP Otimization Suite](https://www.scipopt.org/). The code is available on an [external website](https://scipopt.org/scip/doc/html/BINPACKING_MAIN.php).

### Pseudo-polynomial formulations

[ONECUT](Codes) is an algorithm based on a pseudo-polynomial formulation of the CSP solved throught an ILP solver. It uses the model proposed by H. Dyckhoff in [A new linear programming approach to the cutting stock problem](https://pubsonline.informs.org/doi/10.1287/opre.29.6.1092). *Operations Research*, 29(6):1092–1104, 1981.

[ARCFLOW](Codes) is an algorithm based on a pseudo-polynomial formulation of the CSP solved throught an ILP solver. It uses the model proposed by J.M. Valério de Carvalho in [Exact solution of bin-packing problems using column generation and branch-and-bound](https://link.springer.com/article/10.1023/A:1018952112615). *Annals of Operations Research*, 86:629–659, 1999.

[DPLOW](Codes) is an algorithm based on a pseudo-polynomial formulation of the BPP solved throught an ILP solver. It uses the model proposed by H. Cambazard and B. O’Sullivan in [Propagating the bin packing constraint using linear programming](https://link.springer.com/chapter/10.1007/978-3-642-15396-9_13). *Principles and Practice of Constraint Programming–CP 2010*, pages 129–136. Springer, 2010.

VPSolver is a software than can solve vector packing problems using pseudo-polynomial formulation. Limited to 1 dimension, this problem becomes a CSP. It relies on [Bin packing and related problems: General arc-flow formulation with graph compression](https://www.sciencedirect.com/science/article/pii/S0305054815002762). *Computers & Operations Research*, 69:56-67, 2016, by  F. Brandão and J.P. Pedroso. The code is available on an [external website](https://vpsolver.fdabrandao.pt/).

### Computer codes which appeared after the publication of the BPPLIB

IADA is an iterative aggregation/disaggregation algorithm to solve pseudo-polynomial network flow models with side constraints (including the BPP). It was proposed by F. Clautiaux, S. Hanafi, R. Macedo, M-E Voge, and C. Alves in [Iterative aggregation and disaggregation algorithm for pseudo-polynomial network flow models with side constraints](https://www.sciencedirect.com/science/article/pii/S0377221716308037). *European Journal of Operational Research*, 258(2):467–477, 2017. The code is not available online, but it can be obtained from the authors upon request.

MIM is an algorithm based on an arc-flow formulation with Meet-in-the-Middle patterns and further reduction crieria, solved through an ILP solver (Cplex in the provided implementation). It was proposed by J. F. Côté and M. Iori in [The Meet-in-the-Middle Principle for Cutting and Packing Problems](https://pubsonline.informs.org/doi/10.1287/ijoc.2018.0806). *INFORMS Journal on Computing*, 30(4): 646-661, 2018. The code is available on an [external website](https://sites.google.com/view/jfcote/).

[REFLECT](Codes) is an algorithm based on a pseudo-polynomial formulation of the CSP solved through an ILP solver. It uses the model proposed by M. Delorme and M. Iori in [Enhanced Pseudo-Polynomial Formulations for Bin Packing and Cutting Stock Problem](https://pubsonline.informs.org/doi/10.1287/ijoc.2018.0880). *INFORMS Journal on Computing*, 32(1):101-119, 2020.

EXM is a branch-and-price-and-cut algorithm to solve the BPP. It was proposed by L. Wei, Z. Luo , R. Baldacci, and A. Lim in [A New Branch-and-Price-and-Cut Algorithm for One-Dimensional Bin-Packing Problems](https://pubsonline.informs.org/doi/10.1287/ijoc.2018.0867). *INFORMS Journal on Computing*, 32(2):428-443, 2020. The code is not available online, but it can be obtained from the authors upon request.

VRPSolver is a branch-and-price-and-cut algorithm to solve the vehicle routing and other related problems (including the BPP). It uses the techniques proposed by A. Pessoa, R. Sadykov, E. Uchoa, and F. Vanderbeck in [A generic exact solver for vehicle routing and related problems](https://link.springer.com/article/10.1007/s10107-020-01523-z). *Mathematical Programming*, 183:483–523, 2020. The code is available on an [external website](https://vrpsolver.math.u-bordeaux.fr/).

NF-F is a branch-and-price algorithm to solve pseudo-polynomial network flow models with strong relaxations (including the BPP). It uses the techniques proposed by V.L. de Lima, M. Iori, and F.K. Miyazawa in [Exact solution of network flow models with strong relaxations](https://link.springer.com/article/10.1007/s10107-022-01785-9). *Mathematical Programming*, 197:813–846, 2022. The code is not available online, but it can be obtained from the authors upon request.

BCCF is a numerically exact branch-and-price algorithm to solve the BPP. It uses the techniques proposed by R. Baldacci, S. Coniglio , J.-F. Cordeau , and F. Furini in [A Numerically Exact Algorithm for the Bin-Packing Problem](https://pubsonline.informs.org/doi/10.1287/ijoc.2022.0257). *INFORMS Journal on Computing*, 36(1): 141-162, 2023. The code is available on an [external website](https://github.com/stefanoconiglio/A-Numerically-Exact-Algorithm-for-the-Bin-Packing-Problem).

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

and can be downloaded from [here](Instances/Benchmarks) in both the BPP and the CSP formats.

**Falkenauer** are the instances used by E. Falkenauer in [A hybrid grouping genetic algorithm for bin packing](https://link.springer.com/article/10.1007/BF00226291). *Journal of Heuristics*, 2(1):5–30, 1996. They were downloaded from the [OR-library](https://people.brunel.ac.uk/~mastjjb/jeb/info.html). They are divided into two classes of 80 instances each: the first class has uniformly distributed item sizes (**Falkenauer U**) with $n$ between 120 and 1000, and c = 150. The instances of the second class (``Falkenauer T'') includes the so-called triplets, i.e., groups of three items (one large, two small) that need to be assigned to the same bin in any optimal packing, with $n$ between 60 and 501, and c = 1000.

**Scholl** are the instances used by A. Scholl, R. Klein, and C. Jürgens in [Bison: a fast hybrid procedure for exactly solving the one-dimensional bin packing problem](https://www.sciencedirect.com/science/article/pii/S0305054896000822). *Computers & Operations Research*, 24(7):627–645, 1997. They are divided into three sets of 720, 480, and 10, respectively, uniformly distributed instances with $n$ between 50 and 500. The capacity $c$ is between 100 and 150 (set **Scholl 1**), equal to 1000 (set **Scholl 2**), and equal to 100 000 (set **Scholl 3**), respectively.

**Wäscher** are some of the instances (those regarded as the most difficult ones) used by G. Wäscher and T. Gau in [Heuristics for the integer one-dimensional cutting stock problem: a computational study](https://link.springer.com/article/10.1007/BF01539705). *OR Spectrum*, 18(3):131–44, 1996. They were downloaded from the [ESICUP website](https://www.euro-online.org/websites/esicup/). These 17 hard instances (according to the standards of that time) have $n$ between 27 and 239 and $c$ = 10 000.

**Schwerin** are the instances used by P. Schwerin and G. Wäscher in [The bin-packing problem: a problem generator and some numerical experiments with FFD packing and MTP](https://www.sciencedirect.com/science/article/pii/S0969601697000257). *International Transactions in Operational Research*, 4(5–6):377–389, 1997. They were downloaded from the [ESICUP website](https://www.euro-online.org/websites/esicup/). They are divided into two sets (**Schwerin 1** and **Schwerin 2**) of 100 instances each with $n$ = 100 and $n$ = 120, respectively, and $c$ = 1000.

**Hard28** are the instances used by J.E. Schoenfield in Fast, exact solution of open bin packing problems without linear programming. Technical report, US Army Space and Missile Defense Command, Huntsville, Alabama, USA, 2002.  They were downloaded from the [ESICUP website](https://www.euro-online.org/websites/esicup/). These 28 instances have $n$ between 160 and 200, and $c$ = 1000. 

**Randomly Generated** are the instances randomly generated by M. Delorme, M. Iori, and S. Martello in [Bin Packing and Cutting Stock Problems: Mathematical Models and Exact Algorithms](https://www.sciencedirect.com/science/article/pii/S0377221716302491). *European Journal of Operational Research*, 255(1):1-20, 2016. They have different values of $n$ (50, 100, 200, 300, 400, 500, 750, 1000), $c$ (50, 75, 100, 120, 125, 150, 200, 300, 400, 500, 750, 1000)$, and of the minimum (0.1 $c$, 0.2 $c$) and maximum (0.7 $c$, 0.8 $c$)$ item weight. For each quadruplet ($n$, $c$, minimum weight, maximum weight), 10 instances were generated. 

**ANI AI** are the difficult instances (according to the standards of that time) proposed by M. Delorme, M. Iori, and S. Martello in [Bin Packing and Cutting Stock Problems: Mathematical Models and Exact Algorithms](https://www.sciencedirect.com/science/article/pii/S0377221716302491). *European Journal of Operational Research*, 255(1):1-20, 2016.

**GI** are the instances proposed by T. Gschwind and S. Irnich in [Dual Inequalities for Stabilized Column Generation Revisited](https://pubsonline.informs.org/doi/10.1287/ijoc.2015.0670). *INFORMS Journal on Computing*, 28(1):175-194, 2016.

The solution of all instances can be found [here](Instances/Solutions). 

## Problem generators

**BPPGEN** is a problem generator for the BPP proposed by P. Schwerin and G. Wäscher in [The bin-packing problem: a problem generator and some numerical experiments with FFD packing and MTP](https://www.sciencedirect.com/science/article/pii/S0969601697000257). *International Transactions in Operational Research*, 4(5–6):377–389, 1997.

**CUTGEN1** is a problem generator for the CSP proposed by T. Gau and G. Waescher in [CUTGEN1: A Problem Generator for the Standard One-dimensional Cutting Stock Problem](https://www.sciencedirect.com/science/article/pii/037722179500023J). *European Journal of Operational Research*, 84(3):572-579, 1995.

## Bibliography and useful links

[This](Others) is a BibTex file of relevant references for the bin packing and the cutting stock problems up to 2016.

Here are some interesting links related to the BPP and the CSP:
- [ESICUP](https://www.euro-online.org/websites/esicup/)
- [OR-library](https://people.brunel.ac.uk/~mastjjb/jeb/info.html)

## BppGame: An interactive visual solver

An open source visual ScalaFX application to interactively solve BPP and CSP instances can be downloaded, as a compressed file, from [here](Others). The application is derived from a more general tool for the solution of two-dimensional packing problems proposed by G. Costa, M. Delorme, M. Iori, E. Malaguti, and S. Martello in [Training software for orthogonal packing problems](https://www.sciencedirect.com/science/article/pii/S0360835217302887). *Computers & Industrial Engineering*, 111:139-147, 2017.

The easiest way to test BppGame is to execute the following sequence of actions:
- Click on "Bin Packing Problem" and extract its contents
- Click on "BppGame-1.3.2"
- Click on "bin"
- Execute "BppGame.bat" (Windows) or "BppGame" (Linux)
- Click on "Sample problems" 

# Remarks, questions, suggestions

Please send an email to m.delorme[at]tilburguniversity[dot]edu with object "BPPLIB".
