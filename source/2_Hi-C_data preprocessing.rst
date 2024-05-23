=======================
Hi-C data preprocessing 
=======================

.. contents::
    :local:

The section is designed for data preprocessing of raw omics data. 

1. estimate_resolution
-----------------------------
Before preprocessing, we can first explore the parameter super resolution in HOMER.

.. note::

   This step is not required.


.. code-block:: python

   dna.estimate_resolution(chromosome, cal_type, cohort1, cohort2 = "", fig_dpi = 300)

Arguments
~~~~~~~~~
**Required arguments:**

- ``chromosome``: The chromosome you want to investigate, i.e. ['chr1', 'chr2', ...]. If you want to check all the chromosome, please use 'whole_genome'. Whole genome estimation is recommended but time consuming.

- ``cal_type``: the type of calculation, where 0: comparison between different resolution, 1: comparison between different super resolution with resolution equal to 50kb, 2: comparison between different super resolution with resolution equal to 100kb, 3: comparison between different super resolution with resolution equal to 500kb.

- ``cohort1``: The experimental condition for input data.


**Optional arguments:**

- ``cohort2``: The additional experimental condition for input data if you want to compare with cohort1. The default is "".

- ``fig_dpi``: Figure resolution in dots per inch. The default is 300.


2. preprocess_hic_tag2homer
-----------------------------

Next, applying HOMER to raw Hi-C data (HICUP) to filter and reorganize significant intra-chromosomal interactions.



.. code-block:: python

   dna.preprocess_hic_tag2homer(super_resolution, p_value = 0.1, zscore = 1.0)


Arguments
~~~~~~~~~
**Required arguments:**

- ``super_resolution``: The range of signal averaging. In the manual of HOMER, it is recommended that super resolution be the same as resolution.

**Optional arguments:**

- ``p_value``: Cutoff for intra-chromosomal interactions. The default is ``0.1``.

- ``zscore``: Cutoff for intra-chromosomal interactions. The default is ``1.0``.

Data path
~~~~~~~~~
**input data path:**
`/in_data_folder/hic_data/hicup_processed/cohort`

**output data path:**
`/out_data_folder/hic_data/hic_interaction_homer`

3. preprocess_hic_homer2bed
-----------------------------
Then, BEDTools is used to convert HOMER exported significant interactions to bed format files and Hi-C adjacency matrices are build with predefined resolution.



.. code-block:: python

   dna.preprocess_hic_homer2bed(genome_version = 'hg19', fig_dpi = 300)


Arguments
~~~~~~~~~
**Required arguments:**

- ``genome_version``: Chromosome regions such as hg19, hg38. The default is 'hg19'.

**Optional arguments:**

- ``fig_dpi``: Figure resolution in dots per inch. The default is 300.

Data path
~~~~~~~~~

**output data path:**
The output data including heatmap of interactions, are stored in `/out_data_folder/hic_data/hic_interaction_bed`.