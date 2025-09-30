[![INFORMS Journal on Computing Logo](https://INFORMSJoC.github.io/logos/INFORMS_Journal_on_Computing_Header.jpg)](https://pubsonline.informs.org/journal/ijoc)

# Mathematical models and exact algorithms for kidney exchange problems with immunosuppressants

This archive is distributed in association with the [INFORMS Journal on
Computing](https://pubsonline.informs.org/journal/ijoc) under the [Creative Commons Attribution (CC BY)](LICENSE).

The software and data in this repository are a snapshot of the software and data
that were used in the research reported on in the paper 
[Mathematical models and exact algorithms for kidney exchange problems with immunosuppressants](https://doi.org/10.1287/ijoc.2024.1071) by Maxence Delorme, Wendy Liu and David Manlove.

**Important: This code is being developed on an on-going basis at 
https://github.com/mdelorme2/Mathematical_models_and_exact_algorithms_for_kidney_exchange_problems_with_immunosuppressants. Please go there if you would like to
get a more recent version or would like support.**

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
