=================
Installation
=================

.. contents::
    :local:


Download
============

Dnaici is written in Python and should be run in Python. The package can be downloaded from the  `DNAICI GitHub page <https://github.com/differential-network-analysis/dnaici>`_. Alternatively, you can use the following command:

.. code-block:: bash
    
    wget https://github.com/differential-network-analysis/dnaici.git

Currently, DNAICI cannot be downloaded using pip install dnaici.


Requirements
============

HOMER and Bedtools are required by data preprocessing. Java environment are required by clustering algorithm SLM (Smart Local Moving: ModularityOptimizer.jar).


Initialize package
======================

Change to the correct working directory in Python first. It should be inside **dnaici-master/dnaici/**

.. code-block:: python

    import os   
    os.chdir(path-to-dnaici)

Then dnaici could be imported successfully

.. code-block:: python

    from dnaici import dnaici
    dna = dnaici.DNAICI(in_data_folder,
                        out_data_folder, 
                        cohort = 'untreated', 
                        chromosome = ['chr18', 'chr19'], 
                        resolution = 500000)



Arguments
==========

- ``in_data_folder``: Input data directory where Hi-C, gene expression, nucleosome density, histone marker, genome index, and other necessary datasets are deposited.

- ``out_data_folder``: Output data directory where you hope to store processed Hi-C, gene expression, nucleosome density, histone marker and other analysis results.

- ``cohort``: The experimental condition for input data. The default is 'untreated', representing untreated MCF7 cell line. It can be changed to 'tamr', which represent tamoxifen-resistant MCF7 cell line for demo data, or 't0' and 't1' for full data. If you are using your own datasets, make sure the input is consistent with the name of your dataset, .

- ``chromosome``: List of chromosomes you want to investigate. The default is ['chr18', 'chr19'], designed for demo data. If you want to get the complete results for 23 chromosomes, please let the input be 'whole_genome'.

- ``resolution``: The resolution is used to divide the chromosome into equally sized window bin for analysis. The default is 500000, representing 500 kilobase pair. Due to the computational complexity, a relatively large input (e.g. 1000000 or 500000), which represent a low resolution, is recommended for the first round calculation.



Package Contents
======================
The package folder will contain the following:

- ``demo``: The input demo data for users

- ``dnaici``: The main program of DANICI

- ``README.md``: Short guides to DANICI and demo



