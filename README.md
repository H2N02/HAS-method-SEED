# HAS-method-SEED
Artifacts for CP, MILP, and SAT verification of SEED differential characteristics.
SEED Hybrid Differential Search

This repository provides the solver-based modeling artifacts and verification scripts for the paper:

Towards the optimal differential trails for ISO Standard SEED

The repository focuses on the reproducibility of the CP, MILP, and SAT experiments used in the differential-characteristic search and unrestricted verification of SEED.

Overview

SEED is an ISO-standardized 128-bit block cipher. This repository contains solver-based models for searching and verifying differential characteristics of reduced-round SEED.

The artifacts support the following results reported in the paper:

CP models for 1-, 2-, and 3-round SEED differential search;
MILP models for 4-round and 7-round SEED verification;
SAT models for 4-round and 7-round SEED verification;
unrestricted 7-round SAT verification showing that no valid 7-round SEED differential trail with weight at most 124 exists;
four 7-round differential characteristics with probability 2^−125.

Repository Structure

The repository is organized as follows:

Directory	Solver / Tool	Rounds	Description
cp/	Chuffed	1, 2, 3	CP models for reduced-round SEED differential search
milp/	Gurobi	4, 7	MILP models for reduced-round and 7-round verification
sat/	CryptoMiniSat	4, 7	SAT models for unrestricted differential verification
Requirements

The following solvers are used in the experiments:

Chuffed for CP models;
Gurobi Optimizer for MILP models;
CryptoMiniSat for SAT models.

The MILP experiments require a valid Gurobi license. Academic users can obtain an academic license from Gurobi.

Different solver versions and hardware platforms may lead to different runtimes, but the reported feasibility and infeasibility results should remain unchanged.

CP Experiments

The cp/ directory contains CP models for 1-, 2-, and 3-round SEED differential search. These models are solved using Chuffed.

The CP models are mainly used to validate the component-level differential propagation constraints of SEED, including S-box transformations, modular additions, and bitwise operations.

MILP Experiments

The milp/ directory contains MILP models for 4-round and 7-round SEED verification. These models are solved using Gurobi.

The MILP models are used as part of the unrestricted solver-based verification experiments. In the 7-round case, the MILP model is used to test whether direct full-space verification can efficiently prove the nonexistence of trails below the target bound.

SAT Experiments

The sat/ directory contains SAT models for 4-round and 7-round SEED verification. These models are solved using CryptoMiniSat.

The unrestricted 7-round SAT model is used to verify that no valid 7-round SEED differential trail with weight at most 124 exists in the full search space. This certifies that the weight-125 trails found by the structure-guided hybrid search are globally optimal single-trail differential characteristics.

Main Verification Result

The most important verification result is:

No valid 7-round SEED differential trail with w(τ)≤124 exists.

Therefore, the best single-trail probability for 7-round SEED is confirmed as 2^−125.

Notes on Reproducibility

The released artifacts are intended to support the reproducibility of the solver-based modeling and verification experiments. The runtime may vary depending on solver versions, parameter settings, and hardware platforms.

The structure-guided hybrid search is used to efficiently find the weight-125 trails, while the unrestricted SAT verification is used to certify their global optimality.

Citation

If you use this repository, please cite the corresponding paper:

Towards the optimal differential trails for ISO Standard SEED

BibTeX information will be added after publication.

License

This repository is released under the MIT License.

BibTeX information will be added after publication.

License

This repository is released under the MIT License.
