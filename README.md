# BPPLIB – A Bin Packing Problem Library

This page maintained by M. Delorme (m.delorme@tilburguniversity.edu), M. Iori (manuel.iori@unimore.it), and S. Martello (silvano.martello@unibo.it). 

The BPPLIB is a collection of codes, benchmarks, and links for the one-dimensional Bin Packing and Cutting Stock problem. 

If you need to refer to material taken from this library, please cite M. Delorme, M. Iori, and S. Martello. [BPPLIB: A library for bin packing and cutting stock problems](https://link.springer.com/article/10.1007/s11590-017-1192-z). *Optimization Letters*, 12(2):235-250, 2018.


## Problem description

The bin packing problem (BPP) can be informally defined in a very simple way. We are given $n$ items, each having an integer weight $w_j (j = 1, ..., n)$, and an unlimited number of identical bins of integer capacity $c$. The objective is to pack all the items into the minimum number of bins so that the total weight packed in any bin does not exceed the capacity.

Similarly, in the cutting stock problem (CSP), we are given $m$ item types, each having an integer weight $w_j$ and an integer demand $d_j (j = 1, ..., m)$, and an unlimited number of identical bins (frequently called rolls in the literature) of integer capacity $c$. The objective is to produce $d_j$ copies of each item type $j$ using the minimum number of bins so that the total weight packed in any bin does not exceed its capacity. A CSP instance can be easily transformed into an equivalent BPP instance and vice-versa.

For a recent survey on these problems, see M. Delorme, M. Iori, and S. Martello. [Bin Packing and Cutting Stock Problems: Mathematical Models and Exact Algorithms](https://www.sciencedirect.com/science/article/pii/S0377221716302491). *European Journal of Operational Research*, 255(1):1–20, 2016.

## Cite

To cite the contents of this repository, please cite both the paper and this repo, using their respective DOIs.

https://doi.org/10.1287/ijoc.2024.1071

https://doi.org/10.1287/ijoc.2024.1071.cd

Below is the BibTex for citing this snapshot of the repository.

```
@misc{DLM25,
  author =        {Maxence Delorme and Wendy Liu and David Manlove},
  publisher =     {INFORMS Journal on Computing},
  title =         {Mathematical models and exact algorithms for kidney exchange problems with immunosuppressants},
  year =          {2025},
  doi =           {10.1287/ijoc.2024.1071.cd},
  url =           {https://github.com/INFORMSJoC/2024.1071},
  note =          {Available for download at https://github.com/INFORMSJoC/2024.1071},
}  
```

## Description

The goal of this software is to evaluate different exact approaches to solve the Kidney Exchange Problem with Reserve Arcs (KEP-RA) and the Kidney Exchange Problem with Half-Compatible Arcs (KEP-HCA), 
and also to evaluate the number of transplants enabled by each reserve/half-compatible arc in various settings.

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
