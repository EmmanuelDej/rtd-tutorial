.. _terra:

Terra
=====

Deployment Status
-----------------
**Cluster deployed, currently in testing and early user access mode.**

General Usage Policies
----------------------
**Access to Terra is granted with the condition that you will understand and adhere to all TAMU HPRC and Grace-specific policies.**

General policies can be found on the `HPRC Policies Page <https://hprc.tamu.edu/policies/>`_ .

Accessing Terra
---------------
Most access to Terra is done via a secure shell session. In addition, **two-factor authentication** is required to login to any cluster.

Users on **Windows** computers use either `Puttty <http://www.putty.org/>`_ or `MobaXterm <http://mobaxterm.mobatek.net/>`_ . If MobaXterm works on your computer, it is usually easier to use. When starting an ssh session in PuTTY, choose the connection type 'SSH', select port 22, and then type the hostname 'grace.hprc.tamu.edu'. For MobaXterm, select 'Session', 'SSH', and then remote host 'grace.hprc.tamu.edu'. Check the box to specify username and type your NetID. After selecting 'Ok', you will be prompted for Duo Two Factor Authentication. For more detailed instructions, visit the `Two Factor Authentication <https://hprc.tamu.edu/wiki/Two_Factor#MobaXterm/>`_  page.

Users on **Mac** and **Linux/Unix** should use whatever SSH-capable terminal is available on their system. The command to connect to Grace is as follows. Be sure to replace [NetID] with your TAMU NetID.

.. code-block:: php

  [user1@localhost ~]$ ssh [NetID]@grace.hprc.tamu.edu

.. note::
  In this example [user1@localhost ~]$ represents the command prompt on your local machine. 
  
Your login password is the same that used on `Howdy <https://howdy.tamu.edu/>`_ . You will not see your password as your type it into the login prompt.

Off Campus Access
*****************
Please visit `this page <https://hprc.tamu.edu/wiki/HPRC:Remote_Access>`_  to find information on accessing Grace remotely.

For more detailed instructions on how to access our systems, please see the `HPRC Access page <https://hprc.tamu.edu/wiki/HPRC:Access>`_ .

Navigating Grace and Storage Quotas
-----------------------------------
When you first access Grace, you will be within your *home* directory. This directory has smaller storage quotas and should not be used for general purpose.

You can navigate to your *home* directory with the following command:

.. code-block:: php

  [NetID@grace1 ~]$ cd /home/NetID
  
Your *scratch* directory has more storage space than your *home* directory and is recommended for general purpose use. You can navigate to your *scratch* directory with the following command:

.. code-block:: php

  [NetID@grace1 ~]$ cd /scratch/user/NetID
  
You can navigate to *scratch* or *home* easily by using their respective environment variables.

Navigate to *scratch* with the following command:

.. code-block:: php

  [NetID@grace1 ~]$ cd $SCRATCH
  
Navigate to *home* with the following command:

.. code-block:: php

  [NetID@grace1 ~]$ cd $HOME
  
.. note::
  Your *scratch* directory is restricted to 1TB/250,000 files of storage. This storage quota is **expandable** upon request. A user's *scratch* directory is **NOT**  backed up.

  Your *home* directory is restricted to 10GB/10,000 files of storage. This storage quota is **not expandable**. A user's *home* directory is backed up on a nightly basis.
  
You can see the current status of your storage quotas with:

.. code-block:: php

  [NetID@grace1 ~]$ showquota
  
If you need a storage quota increase, please contact us with justification and the expected length of time that you will need the quota increase.

Transferring Files
------------------
Files can be transferred to Grace using the scp command or a file transfer program.

Our users most commonly utilize:

* `WinSCP <https://winscp.net/eng/download.php>`_  - Straightforward, legacy
* `FileZilla Client <https://filezilla-project.org/>`_  - Easy to use, additional features, available on most platforms
* `MobaXterm Graphical SFTP <https://mobaxterm.mobatek.net/features.html>`_  - Included with MobaXterm

.. tip:: 
  While GUIs are acceptable for file transfers, the cp and scp commands are much quicker and may significantly benefit your workflow.

Reliably Transferring Large Files
*********************************
For files larger than several GB, you will want to consider the use of a more fault-tolerant utility such as rsync.

.. code-block:: php

  [NetID@grace1 ~]$ rsync -av [-z] localdir/ userid@remotesystem:/path/to/remotedir/
  
An rsync example can be seen on the `Ada Fast Transfer <https://hprc.tamu.edu/wiki/Ada:Fast_Data_Transfer#Data_transfer_using_rsync>`_  page.

Managing Project Accounts
-------------------------
The batch system will charge SUs from the either the account specified in the job parameters, or from your default account (if this parameter is omitted). To avoid errors in SU billing, you can view your active accounts, and set your default account using the `myproject <https://hprc.tamu.edu/wiki/HPRC:myproject>`_   command.

Finding Software
----------------
Software on Grace is loaded using **hierarchical modules**.

A list of the most popular software on our systems is available on the `HPRC Available Software <https://hprc.tamu.edu/wiki/SW>`_   page.

To list all software installed as a module on Grace, use the mla utility:

.. code-block:: php

  [NetID@grace1 ~]$ mla
  
To search for a specific piece of software installed as a module on Grace using the mla utility:

.. code-block:: php

  [NetID@grace1 ~]$ mla keyword
  
To **search for** particular software by keyword, use:

.. code-block:: php

  [NetID@grace1 ~]$ module spider keyword
  
To see how to load a module, use the full module name:

.. code-block:: php

  [NetID@grace1 ~]$ module spider Perl/5.32.0
  
You will see a message like the following:

.. code-block:: php

  You will need to load all module(s) on any one of the lines below before the "Perl/5.32.0" module is available to load.

      GCCcore/10.2.0
  
Load the base dependency module(s) first then the full module name

.. code-block:: php

  [NetID@grace1 ~]$ module load GCCcore/10.2.0  Perl/5.32.0
  
To list all currently loaded modules, use:

.. code-block:: php

  [NetID@grace1 ~]$ module list
  
To see what other modules can be loaded with the base dependency module (for example when GCCcore/10.2.0 is loaded)

.. code-block:: php

  [NetID@grace1 ~]$ module avail
  
To remove all currently loaded modules, use:

.. code-block:: php

  [NetID@grace1 ~]$ module purge
  
If you need **new software** or **an update**, please contact us with your request.

There are restrictions on what software we can install. There is also regularly a queue of requested software installations. 
Please account for **delays **in your installation request timeline.

Running Your Program / Preparing a Job File
-------------------------------------------
In order to properly run a program on Grace, you will need to create a job file and submit a job to the batch system. The batch system is a load distribution implementation that ensures convenient and fair use of a shared resource. Submitting jobs to a batch system allows a user to reserve specific resources with minimal interference to other users. All users are required to submit resource-intensive processing to the compute nodes through the batch system - **attempting to circumvent the batch system is not allowed.**

On Grace, **Slurm** is the batch system that provides job management. More information on **Slurm** can be found in the `Grace Batch <https://hprc.tamu.edu/wiki/Grace:Batch>`_  page.
 
The simple example job file below requests 1 core on 1 node with 2.5GB of RAM for 1.5 hours. **Note that typical nodes on Grace have 48 cores with 384 GB of usable memory and ensure that your job requirements will fit within these restrictions.** Any modules that need to be loaded or executable commands will replace the *"#First Executable Line"* in this example.


.. code-block:: php
  
  #!/bin/bash
  ##ENVIRONMENT SETTINGS; CHANGE WITH CAUTION
  #SBATCH --export=NONE        #Do not propagate environment
  #SBATCH --get-user-env=L     #Replicate login environment

  ##NECESSARY JOB SPECIFICATIONS
  #SBATCH --job-name=JobExample1     #Set the job name to "JobExample1"
  #SBATCH --time=01:30:00            #Set the wall clock limit to 1hr and 30min
  #SBATCH --ntasks=1                 #Request 1 task
  #SBATCH --ntasks-per-node=1        #Request 1 task/core per node
  #SBATCH --mem=2560M                #Request 2560MB (2.5GB) per node
  #SBATCH --output=Example1Out.%j    #Send stdout/err to "Example1Out.[jobID]"

  #First Executable Line
  
Note: If your job file has been written on an older Mac or DOS workstation, you will need to use "dos2unix" to remove certain characters that interfere with parsing the script.

.. code-block:: php

  [NetID@grace1 ~]$ dos2unix MyJob.slurm
  
More information on **job options** can be found in the `Building Job Files <https://hprc.tamu.edu/wiki/Grace:Batch#Building_Job_Files>`_ section of the `Grace Batch <https://hprc.tamu.edu/wiki/Grace:Batch>`_  page.

More information on **dos2unix** can be found on the `dos2unix <https://hprc.tamu.edu/wiki/SW:dos2unix>`_  section of the `HPRC Available Software <https://hprc.tamu.edu/wiki/SW>`_  page.

Submitting and Monitoring Jobs
------------------------------
Once you have your job file ready, it is time to submit your job. You can submit your job to slurm with the following command:

.. code-block:: php
  [NetID@grace1 ~]$ sbatch MyJob.slurm
  Submitted batch job 3606
 
After the job has been submitted, you are able to monitor it with several methods. To see the status of all of your jobs, use the following command:

.. code-block:: php
  [NetID@grace1 ~]$ squeue -u NetID
  JOBID       NAME                USER                    PARTITION   NODES CPUS STATE       TIME        TIME_LEFT   START_TIME           REASON      NODELIST            
  3606        myjob2              NetID                   short       1     3    RUNNING     0:30        00:10:30    2016-11-27T23:44:12  None        tnxt-[0340] 
  
To see the status of one job, use the following command, where XXXX is the JobID:

.. code-block:: php
  [NetID@grace1 ~]$ squeue --job XXXX
  JOBID       NAME                USER                    PARTITION   NODES CPUS STATE       TIME        TIME_LEFT   START_TIME           REASON      NODELIST            
  XXXX        myjob2              NetID                   short       1     3    RUNNING     0:30        00:10:30    2016-11-27T23:44:12  None        tnxt-[0340]  

To cancel a job, use the following command, where XXXX is the JobID:

.. code-block:: php

  [NetID@grace1 ~]$ scancel XXXX
  
More information on  `Job Submission <https://hprc.tamu.edu/wiki/Grace:Batch#Job_Submission>`_  and  `Job Monitoring <https://hprc.tamu.edu/wiki/Grace:Batch#Job_Monitoring_and_Control_Commands>`_  Slurm jobs can be found at the `Grace Batch System <https://hprc.tamu.edu/wiki/Grace:Batch>`_  page.

tamubatch
---------
**tamubatch** is an automatic batch job script that submits jobs for the user without the need of writing a batch script on the clusters. The user just needs to provide the executable commands in a text file and tamubatch will automatically submit the job to the cluster. There are flags that the user may specify which allows control over the parameters for the job submitted.

*tamubatch is still in beta and has not been fully developed. Although there are still bugs and testing issues that are currently being worked on, tamubatch can already submit jobs to both the clusters if given a file of executable commands.*

For more information, `visit this page. <https://hprc.tamu.edu/wiki/SW:tamubatch>`_ 

Graphic User Interfaces (Visualization)
---------------------------------------
The use of GUIs on Grace is a more complicated process than running non-interactive jobs or doing resource-light interactive processing.

You have **two options** for using GUIs on Grace.

The **first option** is to use the `Open On Demand Portal <https://portal.hprc.tamu.edu/>`_ ,which is a web interface to our clusters. Users must be connected to the campus network either directly or via VPN to access the portal. More information can be found `here <https://hprc.tamu.edu/wiki/SW:Portal>`_ , or on our `YouTube channel <https://www.youtube.com/watch?v=dqa2ZzsEmQs&list=PLHR4HLly3i4aJJDxKTZIpxyJG6uSqgAgd/>`_ 

The **second option** is to run on the login node. When doing this, you **must** observe the fair-use policy of login node usage. Users commonly violate these policies by accident, resulting in terminated processes, confusion, and warnings from our admins.

