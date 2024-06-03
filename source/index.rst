.. image:: logo_Helse_Sør-Øst.png
   :width: 80
   :align: left
   :target: https://www.helse-sorost.no/

.. image:: logo_Oslo_universitetssykehus_OUS.png
   :width: 150
   :align: left
   :target: https://www.oslo-universitetssykehus.no/

.. image:: logo_Akershus-universitetssykehus.png
   :width: 150
   :align: left
   :target: https://www.ahus.no/

.. image:: logo_uio.png
   :width: 105
   :align: left
   :target: https://www.uio.no/

|

================================================================================
DNAICI: Differential Network Analysis in Intra-chromosomal Community Interaction
================================================================================

Introduction
============
The advancement of both sequencing technologies and computational approaches have revolutionized the field of three-dimensional (3D) chromatin architecture. In order to fully utilize the multi-omics data of 3D chromosomes and mine hidden biological information, we presented **D**ifferential **N**etwork **A**nalysis in **I**ntra-chromosomal **C**ommunity **I**nteraction (DNAICI)，a Python package that combines Hi-C data, epigenetic modifications, and topological features to predict differentially interacting and expressed genes.

This webpage provides instructions for integrative analysis of multi-omics data, from data preprocessing to downstream differential analysis. The default values for parameters used in this instructions are designed for demo data (e.g. `cohort = 'untreated'`, `chromosome = ['chr18','chr19']`), which includes multi-omics data of two chromosomes of from untreated tamoxifen-sensitive MCF7 cell line and one hour estrogen (E2)-treated MCF7 cell line. The full data including tamoxifen-resistant cell line MCF7TR were used to generate the results in our paper.


Contents
========
.. toctree::
   :maxdepth: 1

   1_Installation
   2_Hi-C_data preprocessing
   3_Multi-omics_data preprocessing
   4_Identification of intrachromosomal communities
   5_Enrichment of genomic features
   6_Differential interacting nodes
   7_Enrichment and network analysis
   Paper related files



Useful links for DNAICI
=======================

- `DNAICI package <https://github.com/differential-network-analysis/dnaici>`_

- `Demo data <https://github.com/differential-network-analysis/dnaici/tree/master/demo>`_

- `Full data <https://drive.google.com/file/d/1YbdZ7y5bRNqbP_4hVt6rcZM2Om1PoA-b/view>`_



Citation
==========

Stay tuned...



Other useful links
====================

- `HOMER <http://homer.ucsd.edu/homer/index.html>`_

- `Bedtools <https://bedtools.readthedocs.io/en/latest/>`_

- `UCSC <https://genome.ucsc.edu/>`_







