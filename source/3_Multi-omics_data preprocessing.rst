===============================
Multi-omics data preprocessing 
===============================

.. contents::
    :local:

The section is designed for data preprocessing of raw omics data. 

1. preprocess_omics_map2hic
-----------------------------
For other omics data, they are first organized into bed format files.


.. code-block:: python

   dna.preprocess_omics_map2hic(multi_omics)

Arguments
~~~~~~~~~
**Required arguments:**

- ``multi_omics``: Only accept 'gene expression', 'nucleosome density', and 'histone marker' currently. Other omics data can also be added if they have been appropriately prepared.

Data path
~~~~~~~~~
**input data path:**
`/in_data_folder/multi_omics`

**output data path:**
`/out_data_folder/multi_omics/resolution/out_data`


2. preprocess_omics_heatmap
-----------------------------

Then, multi-omics datasets are mapped to the Hi-C adjacency matrices and heatmaps are drawn based on the genomic feature matrices.

.. code-block:: python

   dna.preprocess_omics_heatmap(multi_omics, type_of_calculation, fig_dpi = 300)


Arguments
~~~~~~~~~
**Required arguments:**

- ``multi_omics``: Only accept 'gene expression', 'nucleosome density', and 'histone marker' currently. Other omics data can also be added if they have been appropriately prepared.

- ``type_of_calculation``: Two options for the value of multi-omics data in the crossed window. It should be setted as 'mean' or 'max'.

**Optional arguments:**

- ``fig_dpi``: Figure resolution in dots per inch. The default is 300.

Data path
~~~~~~~~~
**output data path:**
With the output of the previous function as input, the zscore matrix and heatmap are generated to `/out_data_folder/multi_omics/resolution/out_plot`.
