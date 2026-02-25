---
title: "Formalization of efficient polyhedral computations"
collection: publications
permalink: /publications/thesis
date: 2025-12-11
---

**Authors:** Quentin Canu

## Abstract

The study of the complexity of the simplex algorithm is an open problem marked by several key events. The refutation of Hirsch conjecture, which sought to determine an upper bound on the number of pivots required to execute the simplex method, is one of them. 

However, this proof required a stage of numerical computations which, although feasible by hand, show that the need for a computer-certified calculation could be an asset in the search for other completeness results of the simplex algorithm. Proof assistants are the preferred tools for certifying programs and formalizing mathematics. They are based on programming languages that allow high-level data types to be defined, so that they can be manipulated to obtain proof terms.

However, these same data types are inefficient when used for numerical computations. We prefer data types that are closer to machine representation. Solving the issue of numerical computations within proof assistants requires solving the problem of managing equivalence between these different representations of the same data. 

The aim of this thesis is to study the place of numerical computations within proof assistants, by implementing in Coq an algorithm for certifying the structure of a polytope, the geometric object underlying the execution of the simplex algorithm. By implementing two versions of this same algorithm, manipulating high-level data on the one hand and low-level data on the other, we set up a methodology for refining the data and proving equivalence between the two programs. The two versions are then proven to be equivalent using this methodology, and each serves its own purpose. The low-level version is run directly in Coq and therefore performs numerical computations. The high-level version is proved correct, and so its output value can be used as a hypothesis in writing other proofs. To illustrate how this works, we produce a formal proof of the refutation of Hirsch's conjecture, entrusting the computations to the low-level algorithm and interpreting the results obtained using the high-level algorithm.

Nevertheless, the performance of the low-level algorithm, dedicated to numerical computations, suffers in comparison with informal solutions with the same aim. Another aim of this thesis work is to interpret and propose solutions to improve these performance results. We have identified that the arithmetic of the rationals constitutes a real limitation during the execution of the algorithm. We therefore propose a number of solutions aimed at limiting this impact, by means of finer control over the size of the coefficients computed or the size of the files manipulated. Our most promising solution aims to limit the number of operations on the rationals by imitating the lazy evaluation strategy, which performs a computation only when it has never been performed before. 

Download paper here: [HAL](https://theses.hal.science/tel-05495841)
