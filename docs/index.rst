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

   * **New GPU nodes in the Terra cluster: Four** new GPU nodes are now available in the Terra Cluster.  Each GPU node has two Intel Skylake Xeon Gold 5118 20-core processors, 192 GB of memory and two NVIDIA 32GB V100 GPUs. To use these new GPU nodes, please submit jobs to the '''gpu''' queue on Terra by including the following job directive in your job scripts:

   .. code-block:: php


      #SBATCH --gres=gpu:v100:1            #Request 1 GPU per node can be 1 or 2

      #SBATCH --partition=gpu              #Request the GPU partition/queue

**Getting an Account**
================

   * **Understanding HPRC:** For a brief overview of what services HPRC offers, see `this video <https://www.youtube.com/watch?v=rfqtDigwgMg&list=PLHR4HLly3i4YrkNWcUE77t8i-AkwN5AN8>`_ in our getting started series on YouTube.

   * **New to HPRC's resources?** `This page <https://hprc.tamu.edu/resources/>`_ explains the HPRC resources available to the TAMU community. Also see the `Policies Page <https://hprc.tamu.edu/policies/>`_ to better understand the rules and etiquette of cluster usage..

   * **Accessing the clusters:** All computer systems managed by the HPRC are available for use to TAMU faculty, staff, and students who require large-scale computing capabilities. The HPRC hosts the `Ada <https://hprc.tamu.edu/wiki/Ada>`_ , `Terra <https://hprc.tamu.edu/wiki/Terra>`_ , and `Grace <https://hprc.tamu.edu/wiki/Grace:Intro>`_  clusters at TAMU. To apply for or renew an HPRC account, please visit the `Account Applications <https://hprc.tamu.edu/apply/>`_  page. For information on how to obtain an allocation to run jobs on one of our clusters, please visit the `Allocations Policy <https://hprc.tamu.edu/policies/allocations.html>`_  page. *All accounts expire and must be renewed in September of each year.*

**Using The Clusters**
================
   * **QuickStart Guides:** For just the "need-to-know" information on getting started with our clusters, visit our QuickStart pages. Topics discussed include cluster access, file management, the batch system, setting up a software environment using modules, creating your own job files, and project account management. `Grace Quickstart Guide <https://hprc.tamu.edu/wiki/Grace:QuickStart>`_ , `Terra Quickstart Guide <https://hprc.tamu.edu/wiki/Terra:QuickStart>`_ .

   * **Batch Jobs:** As a shared resource between many users, each cluster must employ a batch system to schedule a time for each user's job to run. Without such a system, one user could use a disproportionate amount of resources, and cause other users' work to stall. Ada's batch system is called LSF, and Terra's batch system is called SLURM. While similar in function, they differ in their finer details, such as job file syntax. Information relevant to each system can be found below.
`here. <https://www.youtube.com/channel/UCgeDEHE5GwkxYUGS0FDLmPw?disable_polymer=true>`_ 
https://hprc.tamu.edu/wiki/Grace:Batch
   +----------------------------------------------------------+---------------------------------------------------------+ 
   | Grace / Slurm Batch Pages                                | Terra / Slurm Batch Pages                               |
   +==========================================================+=========================================================+ 
   | `Complete Grace Batch Page <https://u.tamu.edu/GBatch>`_ |`Complete Terra Batch Page <https://u.tamu.edu/TBatch>`_ | 
   +----------------------------------------------------------+---------------------------------------------------------+
   | `Job Submission (sbatch) <https://u.tamu.edu/GSBatch>`_  |`Job Submission (sbatch) <https://u.tamu.edu/TSBatch>`_  |               
   +----------------------------------------------------------+---------------------------------------------------------+ 
   | `Grace Queue Structure <https://u.tamu.edu/GBQueue>`_    | `Terra Queue Structure <https://u.tamu.edu/TBQueue>`_   | 
   +----------------------------------------------------------+---------------------------------------------------------+
   
   Creating your own batch jobs: the `tamubatch Page <https://hprc.tamu.edu/wiki/SW:tamubatch>`_ provides information on how to use tamubatch to create and submit jobs easily.
   
  * **Troubleshooting:** While we cannot predict all bugs and errors, some issues on our clusters are common enough to catalog. See the `Common Problems and Quick Solutions Page <https://hprc.tamu.edu/wiki/HPRC:CommonProblems>`_ for a small collection of the most prevalent issues. For further assistance, users can contact **help@hprc.tamu.edu** to open a support ticket.
  
**HPRC's YouTube Channel**
================
   * **Prefer visual learning?** HPRC has launched its official YouTube channel where you can find video versions of our help guides, recordings of our short courses, and more! Subscribe `here. <https://www.youtube.com/channel/UCgeDEHE5GwkxYUGS0FDLmPw?disable_polymer=true>`_ 

**Further Reading**
================
