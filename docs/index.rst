.. image:: images/Hprc_banner_tamu.png
.. sidebar:: Optional Sidebar Title
   :subtitle: Optional Sidebar Subtitle
   Subsequent indented lines comprise
   the body of the sidebar, and are
   interpreted as body elements.

.. toctree::
   :maxdepth: 4
   :caption: Contents:
   

**Announcements**
================

* **Ada to Grace Migration:** Users should begin migrating from Ada to Grace now. Read more on our `Ada to Grace migration FAQ <https://hprc.tamu.edu/wiki/HPRC:AdaGraceFAQ>`_
* **Grace Cluster Status:** Cluster deployed, currently in testing and early user access mode. 

* **New GPU nodes in the Terra cluster: Four** new GPU nodes are now available in the Terra Cluster.  Each GPU node has two Intel Skylake Xeon Gold 5118 20-core processors, 192 GB of memory and two NVIDIA 32GB V100 GPUs. To use these new GPU nodes, please submit jobs to the '''gpu''' queue on Terra by including the following job directive in your job script:
==========================
#SBATCH --gres=gpu:v100:1            #Request 1 GPU per node can be 1 or 2
==========================
#SBATCH --partition=gpu              #Request the GPU partition/queue
==========================
