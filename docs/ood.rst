.. _ood:

OOD Portal
==========
What is TAMU HPRC OnDemand Portal
---------------------------------
The TAMU HPRC OnDemand portal is based on `Open OnDemand <https://openondemand.org/>`_ , an open source web platform through which users can access HPC clusters and 
services with a web browser. The portal provides an intuitive and easy-to-use interface and allows new users to be instantly productive at using the HPC resources 
for their research, and at the same time, provides an alternative convenient way for experienced users to access the HPC resources. The portal has a flexible and 
extensible design that makes it easy to deploy new services as needed.

Services Provided
-----------------
* Job submission and monitoring
* File transfer and management
* File editing
* Shell access
* Interactive applications
 * Abaqus
 * Ansys
 * IGV
 * LS-PREPOST
 * Matlab
 * Jupyter Notebook
 * Paraview
 * VNC
 * Rstudio
 * JupyterLab
 * JBrowse

How to Access
-------------
We recommend you access the Grace or Terra portal through their landing page at

      https://portal.hprc.tamu.edu
      
Click the portal you want to connect. The portals are CAS authenticated. All active HPRC users have access to both portals using their NetID and password. You will only be authenticated once, and before your session expires, you can freely access both portals without further authentication.

If accessing from off-campus, the TAMU VPN is needed.

You can go directly to the Grace or Terra portal using one of the following URLs:

  https://portal-terra.hprc.tamu.edu
  
  https://portal-grace.hprc.tamu.edu

Two-Factor Authentication Requirement
*************************************
Starting October 1, 2018, the Division of Information Technology will require use of Duo NetID Two Factor Authentication on its Virtual Private Network (VPN) (connect.tamu.edu) service.

Duo provides a second layer of security to Texas A&M accounts.


If you are not already enrolled in Duo and plan to use VPN, you can enroll now at duo.tamu.edu. Enrolling is as easy as 1-2-3:

#. Choose your device and download the Duo Mobile app. (We strongly recommend the mobile app as the most user-friendly option.)

#. Start your enrollment at https://gateway.tamu.edu/duo-enroll/;

#. Remember: Once you sign up, you will need your Duo-enrolled device when you log in to most Texas A&M resources.

For more information, consult IT's knowledge base article for Duo: https://u.tamu.edu/KB0012105

Using the Portal
----------------
Each service provided by the portal is available at the navigation bar at the top of the page.

.. image:: images/Navigation-bar.png

Files
*****
The first option in the navigation bar is the "Files" drop down menu. From this menu, a user can view a file explorer at either their home directory or scratch directory.

Some users may find the visual interface of the file explorer more intuitive than shell based file exploring. All files in the directory are shown on screen, along with the file tree or hierarchy.

.. image:: images/1200px-File-explorer.png
Normal file management commands are available with the click of a button. These include:

* Viewing files
* Text editing
* Copy/Paste
* Renaming files
* Creating files
* Creating directories
* Deleting files
* File upload/download
The 'View' button will display the highlighted file in the browser, as long as the file type is supported by the browser. Luckily modern browsers support many different types of files, from simple text files, to image files, to complicated multimedia files. This feature can be very convenient and useful if you want to quickly review a file, since you don't have to download the file to your local machine first and then review it, as what you would be doing if you had connected to a cluster using putty or mobaxterm.

File Editor
***********
File editor allows you to edit a file selected. It cannot be accessed from the main menu, but is available through the File app or Job Composer. In File app, you first select a file, then click 'Edit' from the File app interface. Then a new tab will be opened and you can edit the file in the editor. In Job Composer, you can edit the job script by clicking 'Open Editor' at the bottom of Job Composer.

Cluster Shell Access
********************
Shell access to any of the three clusters is available from this drop down menu with one click. Shell access app is similar to ssh client such as Putty and MobaXterm. it allows users to login to a cluster with their NetID and password.

Copy/Paste can be done with hot keys. To copy text from the shell access terminal, highlight the text with a mouse, then the highlighted text will be coped into the clipboard. To paste a text from the clipboard to the terminal, type 'Ctrl+v'.

Shell access works with Firefox and Chrome only.

Copy/Paste in VNC
/////////////////
If launching an interactive session in the portal, there are a few extra steps that need to be taken. Please reference the media below, or the summary of steps below that for more information. 

.. image:: images/PortalDemo.gif

#. Open the toolbar on the left of the screen and select "Clipboard".
#. If you want to paste text from your host computer to the remote session, paste the text in the clipboard box. You can then use the middle-mouse button (MMB) to paste it in your terminal.
#. If you want to copy text from the remote session to your host computer's clipboard, simply highlight the text in the terminal. It will appear in the Clipboard toolbar pop-out where you can copy it to your host clipboard.

Jobs
****
From the jobs drop down menu, a user can view their active jobs or compose and submit jobs using the job composer.

Active Jobs
///////////
The active jobs menu provides information about running jobs the cluster, including their JobID, name, user, account, time used, queue, and status. Clicking the arrow to the left of a given job will reveal more details, such as where it was submitted from, which node it's running on, when it was submitted, process IDs, memory, and CPU time.

.. image:: images/1200px-Activejobs.png

Job Composer
////////////
When first launched, the job composer will walk the user through each of its features, covering the whole process of creating, editing, and submitting a job.

The job composer provides some template job scripts the user can choose from. Once a template is selected, you need to edit the template to provide customized job content. This can be done by clicking 'Open Editor' underneath the job script contents.

The job composer has a specific directory in the user's scratch to store the jobs it has created. We call the directory the job composer's root directory. New jobs created by the job composer will have a sub-directory in the root directory. The name of the sub-directory is same as the index of the job, which is an integer maintained by the job composer. The first job has an index 1, the second job has an index 2, and so on. Knowing this is very important to help us using the job composer more effectively.

There are two ways to cope with the default directory created by the job composer.

.. image:: images/Jobcomposer.png

**Method 1:** using the default directory as the working directory of your job. This means you need to upload all input files to that directory before you can click the submit button. This can be easily done by clicking 'Open Dir' right beneath the job script contents. A file explorer will open the job directory in a new tab where you can do file transfers.

**Method 2:** if you already have the input files stored somewhere in the cluster and don't want to move them around, or you prefer to have an organized directories by yourself, you can simply add one command line in the job script before any other command line, where /path/to/job_working_dir is the directory you want all the commands to be executed:

.. code-block:: php

      cd /path/to/job_working_dir
   
Common Problems
***************
#. The session starts and quits immediately.

      Check your quota in your home and scratch. If you see a full or close to full usage, clean your disk space and try again.

#. In ANSYS Workbench, not all windows are available in the foreground.

      Right click the bottom panel title bar "Unsaved Project - Workbench" and select maximize

Log out
*******
To properly log out the portal, you must do two things: (1) log out the portal by clicking 'Log out' from the top navigation bar; (2) close the browser to completely terminate the session.

**Be aware that only logout of the portal is not enough. You must also close the entire browser (not just the tab)**, a side effect of CAS. This is very important if you are using a public computer.

Cleanup
*******
The portal stores temporary files for interactive apps in $SCRATCH/ondemand/data/sys/dashboard/. Although the disk space used by those files accumulate slowly, it is a good habit to clean this directory periodically.

.. code-block:: php

      rm -rf $SCRATCH/ondemand/data/sys/dashboard/batch_connect/sys/*
      

Interactive Apps
----------------
Each piece of software listed above in the "services provided" section is directly available to launch from this menu. When a piece of software is selected, you will see the interface for job parameters such as number of cores, wall time, memory, and type of node. If you are not sure what to change, the default values work fine. Once you fill out the form, click 'Launch' and the app will be launched as a job. It will first go into a queue, and when ready, a button will become available to view the interface of the chosen software.

Interactive sessions can be managed via the "My Interactive Sessions" button on the navigation bar.

We have tried to provide the most commonly used GUI software packages on the Interactive Apps drop-down menu. If a software is not available, you can always run it within VNC, which is provided on the drop-down menu. To run a GUI application in the VNC session on the portal, follow these steps.

#. Click 'VNC' from 'Interactive Apps' and start a vnc session. 
#. In the terminal within the new tab, load the module for the software you want to run. 
#. If you have chosen a GPU node, please run

.. code-block:: php
      
      vglrun app_name
  
Otherwise, type the app_name from the command line directly.

RStudio
*******
To install CRAN packages, start RStudio with enough memory for the install process: 10 cores and 2GB per core for example.

RStudio automatically enables a web proxy so you only need to run the install.packages command or other commands for Github and Bioconductor package installations.

If you are having problems with Bioconductor or github R packages installations, contact the HPRC helpdesk to request installation.

JupyterLab
**********

Anaconda
////////

Default conda environment
+++++++++++++++++++++++++
You can use the default conda environment in the JupyterLab portal app by selecting Anaconda/3-5.0.0.1 or Anaconda3/2020.07 and leaving the 'Optional Conda Environment to be activated' field blank.

The default environment for Anaconda/3-5.0.0.1 is jupyterlab-v1.2.3_R-3.6.1 which has the R console installed.

The default environment for Anaconda3/2020.07 is /sw/hprc/sw/Anaconda3/2020.07/envs/jupyterlab_v2.2.9_R-3.6.1 which has the R console installed.

Custom Anaconda/3-5.0.0.1 conda environment
+++++++++++++++++++++++++++++++++++++++++++
You can create your own JupyterLab conda environment using Anaconda for use on the HPRC portal but you must use one of the Anaconda versions that are on the JupyterLab `HPRC portal webpage <https://portal-terra.hprc.tamu.edu/pun/sys/dashboard/batch_connect/sys/jupyterlab/session_contexts/new>`_ .

Notice that you will need to make sure you have enough available file quota (~30,000) since conda creates thousands of files.

To to create an Anaconda conda environment called jupyterlab, do the following on the command line:

.. code-block::
      
      module purge
      module load Anaconda/3-5.0.0.1
      conda create -n jupyterlab
      
After your jupyterlab environment is created, you will see output on how to activate and use your jupyterlab environment

.. code-block:: php
      
      #
      # To activate this environment, use:
      # > source activate jupyterlab
      #
      # To deactivate an active environment, use:
      # > source deactivate
      #
      
Then you can install jupyterlab (specifying a version if needed) and add packages to your jupyterlab environment

.. code-block:: php
      
      source activate jupyterlab
      conda install -c conda-forge jupyterlab
      conda install -c conda-forge package-name
      
You can specify a specific package version with the install command. For example to install pandas version 1.1.3:

.. code-block:: php
      
      conda install -c conda-forge pandas=1.1.3
  
To remove downloads after packages are installed.

.. code-block:: php

      conda clean -t

When using Anaconda/3-5.0.0.1, use just the environment name in the 'Optional Environment to be activated' field which in this example will be **jupyterlab**

Custom Anaconda3/2020.07 conda environment
++++++++++++++++++++++++++++++++++++++++++
You can create your own JupyterLab conda environment using Anaconda for use on the HPRC portal but you must use one of the Anaconda versions that are on the JupyterLab `HPRC portal webpage <https://portal-terra.hprc.tamu.edu/pun/sys/dashboard/batch_connect/sys/jupyterlab/session_contexts/new>`_ .

Notice that you will need to make sure you have enough available file quota (~30,000) since conda creates thousands of files.

When using Anaconda3/2020.07, you will need to move your ~/.conda directory to $SCRATCH and make a symbolic link since Anaconda3 may fill up your $HOME disk quota:

.. code-block:: php

      cd
      mv .conda $SCRATCH
      ln -s $SCRATCH/.conda
      
To to create an Anaconda conda environment called jupyterlab, do the following on the command line:

.. code-block:: php
      
      module purge
      mkdir -p /scratch/user/your_netid/Anaconda3/2020.07/envs
      module load Anaconda3/2020.07
      conda create --prefix /scratch/user/your_netid/Anaconda3/2020.07/envs/jupyterlab
      
After your jupyterlab environment is created, you will see output on how to activate and use your jupyterlab environment. You can use 'source activate' instead of 'conda activate'

.. code-block:: php

      #
      # To activate this environment, use:
      # > conda activate /scratch/user/your_netid/Anaconda3/2020.07/envs/jupyterlab
      #
      # To deactivate an active environment, use:
      # > conda deactivate
      #

Then you can install jupyterlab (specifying a version if needed) and add packages to your jupyterlab environment

.. code-block:: php

      source activate /scratch/user/your_netid/Anaconda3/2020.07/envs/jupyterlab
      conda install -c conda-forge jupyterlab
      conda install -c conda-forge package-name
      
You can specify a specific package version with the install command. For example to install pandas version 1.1.3:

.. code-block:: php
      conda install -c conda-forge pandas=1.1.3

To remove downloads after packages are installed.

.. code-block:: php
      
      conda clean -t

When using Anaconda3/2020.07, you must use the full path to the environment in the 'Optional Environment to be activated' field. In this example it will be **/scratch/user/your_netid/Anaconda3/2020.07/envs/jupyterlab**

**NOTE: When using Anaconda3/2020.07 to create a virtualenv, the installation will add lines to your ~/.bashrc file that you should delete since these lines which automatically load your virtualenv which will interfere with other jobs and modules.**

Python
//////

Default python virtualenv
+++++++++++++++++++++++++

You can use the default virtualenv in the JupyterLab portal app by selecting Python/3.7.4-GCCcore-8.3.0 and leaving the 'Optional Conda Environment to be activated' field blank.

The default virtualenv has `Jupyterlmod <https://github.com/cmd-ntrf/jupyter-lmod>`_  installed which allows you to load compatible software modules to use in your notebook.

Type 'toolchains' on the Terra command line to see a table of compatible toolchains.

To load additional software modules, click the 'Softwares' icon in the left most part of your JupyterLab notebook. Search for modules with a compatible toolchain (such as TensorFlow/2.2.0-foss-2019b-Python-3.7.4) and click 'Load' once and wait for the LOADED MODULES section to refresh.

If you have already started your notebook before loading modules, you will need to restart the kernel in order for the loaded module to be available by clicking Kernel -> Restart Kernel... in the top JupyterLab menu or click the 'Restart the kernel' icon at the top of the notebook.

If you get 'Server Connection Error' messages after restarting the kernel, stop all other notebooks you have running by clicking the 'Running Terminals and Kernels' button in the left panel menu and then 'SHUT DOWN' all other running KERNEL SESSIONS.

Custom python virtualenv
++++++++++++++++++++++++

You can create your own virtualenv to use with the JupyterLab portal app but in most cases the default virtualenv should work for you.

You must create your virtualenv using one of the Python modules listed on the JupyterLab HPRC portal webpage.

Here is an example of creating your own virtualenv on a login node.

.. code-block:: php
      
      module load Python/3.7.4-GCCcore-8.3.0
      mkdir -p /scratch/user/your_netid/pip_envs/Python/3.7.4-GCCcore-8.3.0
      cd /scratch/user/your_netid/pip_envs/Python/3.7.4-GCCcore-8.3.0
      virtualenv jupyterlab
      source /scratch/user/your_netid/pip_envs/Python/3.7.4-GCCcore-8.3.0/jupyterlab/bin/activate
      pip install juypter
      pip install jupyterlab
      pip install additional_packages
      
Then in the JupyterLab portal app, select the Python/3.7.4-GCCcore-8.3.0 Module and enter the **full path** of the activate command found in your virtualenv into the 'Optional Conda Environment to be activated' field.

Example of what to enter in the 'Optional Conda Environment to be activated' field:

.. code-block:: php

      /scratch/user/your_netid/pip_envs/Python/3.7.4-GCCcore-8.3.0/jupyterlab/bin/activate

Web Access
//////////
Although compute nodes do not have access to the internet, the JupyterLab app uses a proxy server by default which allows your JupyterLab session to have access to the internet.

Jupyter Notebook
****************
HPRC supports three kinds of environment for Jupyter Notebooks: Conda, Module + Python virtualenv, and Singularity.

All three of these allow some customization by the user, to varying degrees. Broadly speaking:

* Conda: software built by external repository. Provides quick access to commonly-used python packages. Can be extended by the user. Version choices are limited. Recommended for novice users.
* Module + Python virtualenv: software built and maintained by HPRC, optimized for use on our cluster. Can be extended by the user. New software can be requested. Recommended for experienced users.
* Singularity: software built by anyone, anywhere. Fully customizable by the user. Recommended for research groups who collaborate on software builds across multiple clusters.

HPRC provides Jupyter Notebook installations for use with our Conda and Python modules. You can also create your own Jupyter Notebook environment using either a Python environment or Anaconda environment for use on the HPRC Portal, but you must use one of the Module versions that are available on the Jupyter Notebook HPRC portal web page.

Your custom Notebook environment must be created on the command line for later use on the Jupyter Notebook portal app.

Notice that you will need to make sure you have enough available file quota (~10,000) since conda and pip creates thousands of files.

This table can help you decide when to use a Python module and when to use an Anaconda module for installing python packages.

.. image:: images/PythonAnacondaTable.png

`understanding-conda-and-pip <https://www.anaconda.com/blog/understanding-conda-and-pip>`_ 

.. note::
      
      you must activate the python virtualenv or anaconda environment before installing packages with 'pip install --user' or 'conda install'

Python
//////

A Python module can be used to create a virtual environment to be used in the portal Jupyter Notebook app when all you need is Python packages.

You can use a default Python virtual environment in the Jupyter Notebook portal app by leaving the "Optional Environment to be activated" field blank.

To to create a Python virtual environment called my_notebook-python-3.6.6-intel-2018b (you can name it whatever you like), do the following on the command line. You can save your virtual environments in any $SCRATCH directory you want. In this example a directory called /scratch/user/mynetid/pip_envs is used but you can use another name instead of pip_envs

.. code-block:: php

      mkdir /scratch/user/mynetid/pip_envs
      
A good practice is to name your environment so that you can identify which Python version is in your virtualenv so that you know which module to load.

The next three lines will create your virtual environment. You can use any one of the modules listed on the Jupyter notebook portal app. Python/3.6.6-intel-2018b is used in this example

.. code-block:: php

      module purge
      module load Python/3.6.6-intel-2018b
      virtualenv --system-site-packages /scratch/user/mynetid/pip_envs/my_notebook-python-3.6.6-intel-2018b
      
We recommend enabling --system-site-packages so that any modules you load will continue to function.

Then you can activate the virtual environment by using the full path to the activate command inside your virtual environment and install Python packages.

.. code-block:: php

      source /scratch/user/mynetid/pip_envs/my_notebook-python-3.6.6-intel-2018b/bin/activate
      pip install notebook
      pip install optional-python-package-name
      
You can use your Python/3.6.6-intel-2018b environment in the Jupyter Notebook portal app by selecting the Python/3.6.6-intel-2018b module in the portal app page and providing the name including full path to the activate command for your Python/3.6.6-intel-2018b virtual environment in the "Optional Environment to be activated" box (i.e. /scratch/user/mynetid/pip_envs/my_notebook-python-3.6.6-intel-2018b/bin/activate). The activate command is found inside the bin directory of your virtual env. An example of what to put in the "Optional Environment to be activated" box is the full path used in the source command above.

Loading additional Lmod modules
+++++++++++++++++++++++++

The default Python/3.7.4-GCCcore-8.3.0 virtualenv for JupyterLab on Terra has Jupyterlmod installed which allows the user to load any module built with the GCCcore-8.3.0 or 2019b toolchains after starting jupyter notebook in JupyterLab.

You can install the `jupyterlmod <https://github.com/cmd-ntrf/jupyter-lmod>`_  package in your python virtual environment on Terra which will allow you to load additional system modules that you may need or may have used during the creation of your virtual environment on Terra for use with the Terra Jupyter Notebook portal app.

To add this feature to your existing Terra virtual environment, do the following on the command line prior to launching Jupyter Notebook on the portal (you can use Python/3.6.6-foss-2018b if the additional module(s) you need are not available with the intel-2018b toolchain):

.. code-block:: php

      module purge
      module load Python/3.6.6-intel-2018b
      source /scratch/user/mynetid/pip_envs/my_notebook-python-3.6.6-intel-2018b/bin/activate
      pip install jupyter jupyterlmod
      
Then launch the Terra Jupyter Notebook portal app using your optional environment and click the 'Softwares' tab in your notebook and search for system modules.

Select a module or multiple modules that match the toolchain and python version that you used in creating your virtual environment and then click enter to load the module.

The 'Loaded Modules' list will update in a few seconds to reflect the additional module(s) loaded.

You can save your modules loaded using the 'collection' button at the right side of the notebook 'softwares' page so that you just have to select the collection instead of searching for modules each time you want to use your python virtual environment.

Anaconda
////////

Anaconda is different than Python's virtualenv in that you can install other types of software such as R and R packages in your environment.

Anaconda also manages the installation path and installs in your $SCRATCH/.conda directory so you don't have to create a directory prior to creating an environment.

The recommended Anaconda module to use for Python 3 is Anaconda/3-5.0.0.1

To to create an Anaconda conda environment called my_notebook (you can name it whatever you like), do the following on the command line:

.. code-block:: php

      module purge
      module load Anaconda/3-5.0.0.1
      conda create -n my_notebook

After your my_notebook environment is created, you will see output on how to activate and use your my_notebook environment

.. code-block:: php
      
      #
      # To activate this environment, use:
      # > source activate my_notebook
      #
      # To deactivate an active environment, use:
      # > source deactivate
      #
      
Then you need to install notebook and then you can add optional packages to your my_notebook environment

.. code-block:: php

      source activate my_notebook
      conda install -c conda-forge notebook
      conda install -c conda-forge optional-package-name
      
You can use your Anaconda/3-5.0.0.1 environment in the Jupyter Notebook portal app by selecting the Anaconda/3-5.0.0.1 module in the portal app page and providing just the name (without the full path) of your Anaconda/3-5.0.0.1 environment in the "Optional Environment to be activated" box. In the example above, the value to enter is: **my_notebook**

Errors importing a python package
+++++++++++++++++++++++++++++++++

Sometimes the latest or specific versions of a python package does not work in a specific Anaconda environment due to incompatibility with the Python version or with other packages.

Default Python version
++++++++++++++++++++++

You can try installing an older version of a python package by searching available versions on anaconda.org and specify a specific version to install.

For example, if you have Python 3.6.11 and numpy 1.19.2 and see the following error:


.. code-block:: php
      
      import numpy

      ModuleNotFoundError: No module named 'numpy.core._multiarray_umath'
      
Install an older version of numpy (the following command automatically overwrites the currently installed numpy version)

.. code-block:: php
      
      conda install -c conda-forge numpy=1.15.4
      
In the above example, this resolved an 'import numpy' error in an environment with Python 3.6.11 with numpy 1.19.2 by downgrading numpy which also downgraded other packages:

.. code-block:: php
      
      The following packages will be DOWNGRADED:

            matplotlib:       3.3.2-0                  conda-forge --> 3.2.0-1                  conda-forge
            matplotlib-base:  3.3.2-py36h2451756_0     conda-forge --> 3.2.0-py36h250f245_1     conda-forge
            numpy:            1.19.2-py36he0f5f23_1    conda-forge --> 1.15.4-py36h8b7e671_1002 conda-forge
            scipy:            1.5.2-py36h832618f_0     conda-forge --> 1.4.1-py36h921218d_0     conda-forge
            
         
Web Access
//////////

Jupyter Notebook runs on the compute nodes which do not have internet access.

If you need internet access for your notebook then enable the proxy using the following.

Terra
+++++

Run the following lines in your notebook:

.. code-block:: php
      
      import os
      os.environ['http_proxy'] = '10.76.5.24:8080'
      os.environ['https_proxy'] = '10.76.5.24:8080'
      
Grace
+++++

Run the following lines in your notebook:

.. code-block:: php
      
      import os
      os.environ['http_proxy'] = '10.73.132.63:8080'
      os.environ['https_proxy'] = '10.73.132.63:8080'
      
Spark Jupyter Notebook
**********************

default notebook
////////////////
You can use a default Python virtual environment in the Spark Jupyter Notebook portal app by leaving the "Optional Python Environment to be activated" field blank.

The default Spark notebook uses the module Spark/2.4.0-intel-2018b-Hadoop-2.7-Java-1.8-Python-3.6.6 and the following python packages jupyter, numpy, sklearn, pandas, seaborn, pyarrow

create your own notebook
////////////////////////

You can create your own Spark Jupyter Notebook python virtual environment for use on the HPRC Portal but you must use the following module to create your Python virtualenv

.. code-block:: php

      GRACE:
      module load iccifort/2019.5.281  impi/2018.5.288  Spark/2.4.5-Python-3.7.4-Java-1.8
     
.. code-block:: php

      TERRA:
      module load Spark/2.4.0-intel-2018b-Hadoop-2.7-Java-1.8-Python-3.6.6

Notice that you will need to make sure you have enough available file quota (~10,000) since pip creates thousands of files.

To create a Python virtual environment called my_spark_notebook-python-3.6.6-foss-2018b (you can name it whatever you like), do the following on the command line. You can save your virtual environments in any $SCRATCH directory you want. In this example a directory called /scratch/user/mynetid/pip_envs is used but you can use another name instead of pip_envs

.. code-block:: php

      mkdir -p /scratch/user/mynetid/pip_envs

A good practice is to name your environment so that you can identify which Python version is in your virtualenv so that you know which module to load.

The next three lines will create your virtual environment using the Spark module on Terra.

.. code-block:: php

      module purge
      module load Spark/2.4.0-intel-2018b-Hadoop-2.7-Java-1.8-Python-3.6.6
      export SPARK_HOME=$EBROOTSPARK
      virtualenv /scratch/user/mynetid/pip_envs/my_spark_notebook-python-3.6.6-foss-2018b
      
Then you can activate the virtual environment by using the full path to the activate command inside your virtual environment and install Python packages.

First install the required dependencies (jupyter, numpy, sklearn, pandas, seaborn, pyarrow) then you can install your additional packages.

.. code-block:: php

      source /scratch/user/mynetid/pip_envs/my_spark_notebook-python-3.6.6-foss-2018b/bin/activate
      python3 -m pip install jupyter
      python3 -m pip install numpy
      python3 -m pip install sklearn
      python3 -m pip install pandas
      python3 -m pip install seaborn
      python3 -m pip install pyarrow

When you are finished installing your python packages, go to the Spark Jupyter Notebook portal app and enter the full path of your virtualenv in the field 'Optional Python Environment to be activated' such as /scratch/user/mynetid/pip_envs/my_spark_notebook-python-3.6.6-foss-2018b in this example. 

Additional Information
----------------------
Ohio Supercomputing Center has video for OOD at:

 https://youtu.be/DfK7CppI-IU
