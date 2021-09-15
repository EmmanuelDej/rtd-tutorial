.. image:: images/Hprc_banner_tamu.png

**Announcements**

* '''Ada to Grace Migration: ''' Users should begin migrating from Ada to Grace now. Read more on our [[:HPRC:AdaGraceFAQ | Ada to Grace migration FAQ]].

* '''Grace Cluster Status: ''' Cluster deployed, currently in testing and early user access mode. 

* '''New GPU nodes in the Terra cluster: '''  '''Four''' new GPU nodes are now available in the Terra Cluster.  Each GPU node has two Intel Skylake Xeon Gold 5118 20-core processors, 192 GB of memory and two NVIDIA 32GB V100 GPUs. To use these new GPU nodes, please submit jobs to the '''gpu''' queue on Terra by including the following job directive in your job script:

<pre>
#SBATCH --gres=gpu:v100:1            #Request 1 GPU per node can be 1 or 2
#SBATCH --partition=gpu              #Request the GPU partition/queue
</pre>
========================================

.. toctree::
   :maxdepth: 2
   :caption: Contents:



Indices and tables
==================

* :ref:`genindex`
* :ref:`modindex`
* :ref:`search`
