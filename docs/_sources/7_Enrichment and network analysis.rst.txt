===============================
Enrichment and network analysis
===============================
.. contents::
    :local:

1. diegs_enrichment
---------------------
In this section, differentially interacting and expressed genes (DIEGs) need to be identified from the selected significant nodes. Gene enrichment analysis should be performed based on these DIEGs.

.. code-block:: python

   dna.diegs_enrichment(cohort1, cohort2, method = 'relativeRatio', pval_cutoff = 0.05, fig_dpi = 300)

Arguments
~~~~~~~~~
**Required arguments:**

- ``cohort1``: Cohort 1 with all the above steps completed.

- ``cohort2``: Cohort 2 with all the above steps completed.

- ``method``: Methods for selecting differentially expressed genes ('relativeRatio': relative ratio; 'foldChange': fold change). The default is 'relativeRatio'.

**Optional arguments:**

- ``pval_cutoff``: P-value for screen for significant nodes in network_sigNodes. The default is 0.05.

- ``fig_dpi``: Figure resolution in dots per inch. The default is 300.


.. ATTENTION::

   After obtaining DIEGs, users should go to DAVID website for gene enrichment analysis based on these DIEGs if they want to get figures of enrichment analysis.

2. diegs_subnetwork
------------------------------

Then, subnetworks based on the selected DIEGs and genomic information within each node can be obtained.

.. code-block:: python

   dna.diegs_subnetwork(cohort1, cohort2, chromosome, pval_cutoff = 0.05)

Arguments
~~~~~~~~~
**Required arguments:**

- ``cohort1``: Cohort 1 with all the above steps completed.

- ``cohort2``: Cohort 2 with all the above steps completed.

- ``chromosome``: Methods for selecting differentially expressed genes ('relativeRatio': relative ratio; 'foldChange': fold change). The default is 'relativeRatio'.

**Optional arguments:**

- ``pval_cutoff``: P-value for screen for significant nodes in network_sigNodes. The default is 0.05.

Data path
~~~~~~~~~
**output data path:**
The subnetworks, genomic features (histone markers of enhancer/repressor, gene expression) as well as gene names within each node are exported to `/out_data_folder/differential_network_analysis`.
