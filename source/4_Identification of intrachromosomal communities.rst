==============================================
Identification of intrachromosomal communities
==============================================

.. contents::
    :local:

1. cluster_for_hic
-------------------
After preparing the Hi-C interaction matrices, clustering algorithm (ModularityOptimizer.jar) is used to identify network communities.

.. code-block:: python

   dna.cluster_for_hic(modularity_function = 1, resolution_parameter = 1.0, optimization_algorithm = 3, n_random_starts = 10, n_iterations = 100, random_seed = 0, print_output = 1)

Arguments
~~~~~~~~~
**Optional arguments:**

- ``modularity_function``: The modularity function for clustering method where 1 = standard and 2 = alternative. The default is 1.

- ``resolution_parameter``: The resolution of clustering method. The default is 1.0.

- ``optimization_algorithm``: The selection of optimization algorithm where 1 = original Louvain algorithm, 2 = Louvain algorithm with multilevel refinement, and 3 = SLM algorithm. The default is 3.

- ``n_random_starts``: The number of random starts for clustering. The default is 10.

- ``n_iterations``: The number of iterations per random start. The default is 100.

- ``random_seed``: The seed of the random number generator. The default is 0.

- ``print_output``: Whether or not to print output to the console (0 = no; 1 = yes). The default is 1.

Data path
~~~~~~~~~
**output data path:**
Then, cluter results like nodes and communities are organized into .tsv format, while networks are transformed into .json format. 
All these results can be found in `/out_data_folder/hic_data/resolution/hic_community_data`.

.. code-block:: python

   dna.cluster_to_json()


2. estimate_community_size
---------------------------

The next function is to find the cutoff value for valid community. 

.. note::

   This function requires the first two functions finished (dna.cluster_for_hic() and dna.cluster_to_json()). It is recommended to get the optimal cutoff by using all 23 chromosomes, but again, this is more time consuming.


.. code-block:: python

   dna.estimate_community_size(cohort, chromosome, cutoff4Proportion = 0.02, fig_dpi = 300)

Arguments
~~~~~~~~~
**Required arguments:**

- ``cohort``: The dataset you want to investigate.

- ``chromosome``: The chromosome you want to investigate, i.e. ['chr1', 'chr2', ...]. If you want to check all the chromosome, please use 'whole_genome'. Whole genome estimation is recommended but time consuming.

**Optional arguments:**

- ``cutoff4Proportion``: The proportion is used to determine the minimal size of valid community. The default is 0.02.

- ``fig_dpi``: Figure resolution in dots per inch. The default is 300.


3. cluster_community_structure
------------------------------

Next, valid communities should be identified in all clusters. Hi-C interactions and other genomic features within each community need to be analyzed.

.. code-block:: python

   dna.cluster_community_structure(minCluster_size = 20, fig_dpi = 300)


Arguments
~~~~~~~~~
**Optional arguments:**

- ``minCluster_size``: The minimum size (or number of interactions) of valid communities. It is recommeded to use module estimate_community_size to identify the optimal value at a specific window resolution. The default is 20. Value smaller than 3 is not accepted.

- ``fig_dpi``: Figure resolution in dots per inch. The default is 300.

Data path
~~~~~~~~~
**output data path:**
Through this, a summary of interactions and modularity score of network clustering and valid communities are exported to a table located in `/out_data_folder/hic_data/resolution/hic_community_figures`.


4. cluster_super_network
-------------------------

Next, valid communities should be identified in all clusters. Hi-C interactions and other genomic features within each community need to be analyzed.

.. code-block:: python

   dna.cluster_community_structure(minCluster_size = 20, fig_dpi = 300)


Arguments
~~~~~~~~~
**Optional arguments:**

- ``minCluster_size``: The minimum size (or number of interactions) of valid communities. It should be consistent with the minCluster_size in cluster_community_structure. The default is 20. Value smaller than 3 is not accepted.

- ``fig_dpi``: Figure resolution in dots per inch. The default is 300.

Data path
~~~~~~~~~
**output data path:**
The exported super networks can be found in `/out_data_folder/hic_data/resolution/hic_community_figures`.