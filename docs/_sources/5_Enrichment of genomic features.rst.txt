==============================
Enrichment of genomic feature
==============================
.. contents::
    :local:

1. enrichment_permutation
--------------------------
After dividing the chromosome into several valid structures, random permutation tests of enrichment are performed by comparing genomic features within and outside each community.

.. code-block:: python

   dna.enrichment_permutation(permutation = 100, pval_cutoff = 0.01, fig_dpi = 300)

Arguments
~~~~~~~~~
**Optional arguments:**

- ``permutation``: Resampling times of random permutation test of genomic enrichment. The default is 100.

- ``pval_cutoff``: Cutoff for features in a community is significantly higher/lower than randomly selected samples. The default is 0.01.

- ``fig_dpi``: Figure resolution in dots per inch. The default is 300.

2. enrichment_heatmap
------------------------------

Then, draw both tval and pval of genomic feautre heatmaps from enrichment_permutation.

.. code-block:: python

   dna.enrichment_heatmap(permutation = 100, fig_dpi = 300)


Arguments
~~~~~~~~~
**Optional arguments:**

- ``permutation``: Number of sampling when doing permutation test in enrichment_permutation. The default is 100.

- ``fig_dpi``: Figure resolution in dots per inch. The default is 300.

Data path
~~~~~~~~~
**output data path:**
The permutation results are stored in `/out_data_folder/hic_data/resolution/hic_community_figures`.
