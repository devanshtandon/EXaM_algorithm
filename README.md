# EXaM_algorithm

This repository contains a python implementation for the EXaM algorithm. The paper attached describes the development of the algorithm in further detail. 

## Abstract
Randomized Controlled Trials (RCT) enroll hundreds of millions of subjects and randomize treatment with a large impact on human lives. Experiment-as-Market (EXaM) is an alternative design for RCT that respects subjects' welfare by incorporating information on predicted treatment effects and willingness to pay. This paper presents an algorithm developed to implement the EXaM mechanism by computing a market equilibrium, solving a problem similar to Fisher's general equilibrium model. The algorithm efficiently computes a market equilibrium using iterative random local search to find a market clearing price that maximizes subject utility. To evaluate the algorithm and EXaM, I use experimental data from a RCT to find an alternate treatment assignment matching (under EXaM), which leads to an increase in predicted subject welfare while replicating the treatment effects. The algorithm correctly and efficiently computes a market equilibrium, empirically verifies properties of EXaM, and provides an implementation viable for practical use.

## Setup

The inputs to the algorithm are: 
1. $n$ the number of subjects, $m$ the number of treatments
2. A list of capacities for each treatment of size $m$, ($(c_t)\in \mathbb{N}$ such that $\sum_t c_t =n$) and budget constraint $b$ 
3. A Willingness-To-Pay (WTP) matrix of size $n$ x $m$, where $(w_{it})$ is subject $i$'s WTP for treatment $t$
4. A Predicted-Trreatment-Effect (PTE) matrix of size $n$ x $m$, where $(e_{it})$ is subject $i$'s PTE for treatment $t$

The algorithm outputs:
1. A $n$ x $m$ matrix of equilibrium demand -- the probability matrix. $(p^*_{it})$ is treatment $t$'s assignment probability for subject $i$ 
2. A $n$ x $m$ matrix of the market clearing equilibrium price $\pi^*_{te}$, which is defined by 2 parameters as $\pi^*_{te} = \alpha^*e+\beta^*_t$. $(\pi^*_{te})$ is the treatment $t$'s equilibrium price, defined for a subject with a given $e_{it}$.
\end{enumerate}
