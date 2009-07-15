---
title: Remove PDB disordered atoms
permalink: wiki/Remove_PDB_disordered_atoms
layout: wiki
tags:
 - Cookbook
---

Problem
-------

You have a PDB with disordered atoms, i.e. different atomic positions
with occupancies that add up to 100%. From this PDB you want to create a
new one having only one set of the disordered atoms. This can be
necessary if you want to perform RMSD calculations or Molecular Dynamics
simulations.

Solution
--------