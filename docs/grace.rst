.. _grace:

Grace
=====

Deployment Status
-----------------
**Cluster deployed, currently in testing and early user access mode.**

General Usage Policies
----------------------
**Access to Grace is granted with the condition that you will understand and adhere to all TAMU HPRC and Grace-specific policies.**

General policies can be found on the `HPRC Policies Page <https://hprc.tamu.edu/policies/>`_ .

Accessing Grace
---------------
Most access to Grace is done via a secure shell session. In addition, **two-factor authentication** is required to login to any cluster.

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
