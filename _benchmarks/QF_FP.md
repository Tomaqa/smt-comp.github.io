---
layout: logic
division: QF_FP
description: http://smtlib.cs.uiowa.edu/logics.shtml#QF_FP
tracks:
- name: track_single_query
  n_insts: 250
  n_excluded: 0
  status: competitive
- name: track_incremental
  n_insts: 2
  n_excluded: 0
  status: non-competitive
- name: track_single_query_challenge
  n_insts: 0
  n_excluded: 0
  status: competitive
- name: track_incremental_challenge
  n_insts: 0
  n_excluded: 0
  status: competitive
- name: track_unsat_core
  n_insts: 10031
  n_excluded: 0
  status: non-competitive
- name: track_model_validation
  n_insts: 0
  n_excluded: 0
  status: competitive
---
QF_FP Incremental Track track participated only by Z3, CVC4.  
QF_FP Unsat Core Track track participated only by Z3, CVC4.

We encountered issues with the
[benchmark scrambler](https://github.com/smt-comp/scrambler) on two benchmarks
in this division
(fixed in [053bb79](https://github.com/SMT-COMP/scrambler/commit/053bb79a79b39749284e4bef31ffc6438a52adf8)).  
An expression `(fp.leq a x b)` was scrambled to `(fp.gt x a b)` instead of
`(fp.gt b a x)`, which resulted in a flipped result in the following two
benchmarks:
- non-incremental/QF_FP/schanda/spark/guarded_div_1.smt2
- non-incremental/QF_FP/schanda/spark/average_2.smt2

These two benchmarks are thus **excluded** from this division.