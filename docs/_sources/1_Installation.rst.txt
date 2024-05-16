=================
Installation
=================

.. contents::
    :local:

Download
============

Dnaici is written in Python. It can be installed and accessed from the command line and is available for both Linux and macOS operating systems. The package can be downloaded from the  `EpiMapper GitHub page <https://github.com/EpiMapper-pipeline/code/tree/main/epimapper>`_. Alternatively, you can use the following command:

Install
============

Requirements
============

HOMER and Bedtools are required by data preprocessing. Java environment and ModularityOptimizer.jar are required by clustering algorithm.

Package Installation
======================

.. code-block:: python

   from dnaici import dnaici
   dna = dnaici.DNAICI(in_data_folder, out_data_folder, cohort = 'untreated', chromosome = ['chr18', 'chr19'], resolution = 500000)


Arguments
==========

- ``in_data_folder``: Input data directory where Hi-C, gene expression, nucleosome density, histone marker, and chromosome regions hg19 are deposited.

- ``out_data_folder``: Output data directory where processed Hi-C, gene expression, nucleosome density, histone marker and other analysis results are deposited.

- ``cohort``: The experimental condition for input data. The default is 'untreated', representing untreated MCF7 cell line. It can be changed to 'tamr' for demo data, or 't0' and 't1' for full data.

- ``chromosome``: List of chromosomes you want to investigate. The default is ['chr18', 'chr19']. If you want to get the complete results for 23 chromosomes, please let the input be 'whole_genome'.

- ``resolution``: The resolution is used to divide the chromosome into equally sized window bin for analysis. The default is 500000, representing 500 kilobase pair.

.. note::

   Currently, DNAICI cannot be downloaded using pip install dnaici.


Package Contents
======================
The package folder will contain the following:
