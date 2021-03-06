.. title:: Nutanix Enterprise Private Cloud Bootcamp

.. toctree::
   :maxdepth: 2
   :caption: Enterprise Private Cloud
   :name: _enterprise_privatecloud
   :hidden:

   dayinlife/dayinlife
   prismops/prismops_capacity_lab/prismops_capacity_lab
   files/files
   flow_secure_fiesta/flow_secure_fiesta

.. toctree::
  :maxdepth: 2
  :caption: Optional Labs
  :name: _optional_labs


  image_create/image_create
.. lab_image_configuration/lab_image_configuration

.. toctree::
  :maxdepth: 2
  :caption: Appendix
  :name: _appendix
  :hidden:

  tools_vms/windows_tools_vm
  tools_vms/linux_tools_vm
  appendix/glossary

.. toctree::
  :maxdepth: 2
  :caption: Optional
  :name: _pismops
  :hidden:

  prismops/prismops_rightsize_lab/prismops_rightsize_lab
  security/security


.. _getting_started:

---------------
Getting Started
---------------

Welcome to the Nutanix Enterprise Private Cloud Bootcamp! This workbook accompanies an instructor-led session that introduces Nutanix Core technologies and many common management tasks.

You will explore Prism Central and become familiar with its features and navigation. You will use Prism to perform basic cluster administration tasks, including storage and networking. You will also walk through basic VM deployment and management tasks with Prism and AHV. Finally, you will explore VM data protection, including snapshots and replication. The instructor explains the exercises and answers any additional questions that you may have.

At the end of the bootcamp, attendees should understand the Core concepts and technologies that make up the Nutanix Enterprise Cloud stack and should be well prepared for a hosted or onsite proof-of-concept (POC) engagement.

What's New
++++++++++

- Workshop updated for the following software versions:
    - AOS & PC 5.16.2.x

- Optional Lab Updates:


Agenda
++++++

Morning Session:

- Presentations
- Lab A: A Day in the Life
- Lab B: Prism Pro Capacity Runway

Afternoon Session:

- Presentations
- Lab C: Consolidating Storage with Files
- Lab D: Securing Applications with Flow

Introductions
+++++++++++++

- Name
- Familiarity with Nutanix

Initial Setup
+++++++++++++

- Take note of the *Passwords* being used.
- Log into your virtual desktops (connection info below)

Environment Details
+++++++++++++++++++

Nutanix Workshops are intended to be run in the Nutanix Hosted POC environment. Your cluster will be provisioned with all necessary images, networks, and VMs required to complete the exercises.

Networking
..........

Hosted POC clusters follow a standard naming convention:

- **Cluster Name** - POC\ *XYZ*
- **Subnet** - 10.**38**.\ *XYZ*\ .0
- **Cluster IP** - 10.**38**.\ *XYZ*\ .37

For example:

- **Cluster Name** - POC208
- **Subnet** - 10.38.208.0
- **Cluster IP** - 10.38.208.37

Throughout the Workshop there are multiple instances where you will need to substitute *XYZ* with the correct octet for your subnet, for example:

.. list-table::
   :widths: 25 75
   :header-rows: 1

   * - IP Address
     - Description
   * - 10.38 .\ *XYZ*\ .37
     - Nutanix Cluster Virtual IP
   * - 10.38 .\ *XYZ*\ .39
     - **PC** VM IP, Prism Central
   * - 10.38 .\ *XYZ*\ .40
     - **DC** VM IP, NTNXLAB.local Domain Controller

Each cluster is configured with 2 VLANs which can be used for VMs:

.. list-table::
  :widths: 25 25 10 40
  :header-rows: 1

  * - Network Name
    - Address
    - VLAN
    - DHCP Scope
  * - Primary
    - 10.38.\ *XYZ*\ .1/25
    - 0
    - 10.38.\ *XYZ*\ .50-10.21.\ *XYZ*\ .124
  * - Secondary
    - 10.38.\ *XYZ*\ .129/25
    - *XYZ1*
    - 10.38.\ *XYZ*\ .132-10.21.\ *XYZ*\ .253

Credentials
...........

.. note::

  The *<Cluster Password>* is unique to each cluster and will be provided by the leader of the Workshop.

.. list-table::
   :widths: 25 35 40
   :header-rows: 1

   * - Credential
     - Username
     - Password
   * - Prism Element
     - admin
     - customerSE/4u
   * - Prism Central
     - admin
     - customerSE/4u
   * - Controller VM
     - nutanix
     - customerSE/4u
   * - Prism Central VM
     - nutanix
     - customerSE/4u

Each cluster has a dedicated domain controller VM, **DC**, responsible for providing AD services for the **NTNXLAB.local** domain. The domain is populated with the following Users and Groups:

.. list-table::
   :widths: 25 35 40
   :header-rows: 1

   * - Group
     - Username(s)
     - Password
   * - Administrators
     - Administrator
     - nutanix/4u
   * - SSP Admins
     - adminuser01-adminuser25
     - nutanix/4u
   * - SSP Developers
     - devuser01-devuser25
     - nutanix/4u
   * - SSP Consumers
     - consumer01-consumer25
     - nutanix/4u
   * - SSP Operators
     - operator01-operator25
     - nutanix/4u
   * - SSP Custom
     - custom01-custom25
     - nutanix/4u
   * - Bootcamp Users
     - user01-user25
     - nutanix/4u

Access Instructions
+++++++++++++++++++

The Nutanix Hosted POC environment can be accessed a number of different ways:

Labs: POC221, POC176, POC204, POC215

Lab Access User Credentials
...........................

PHX Based Clusters:
**Username:** PHX-POCxxx-User01 (up to PHX-POCxxx-User20), **Password:** customerSE/4u


Frame VDI
.........

Login to: https://frame.nutanix.com/x/labs


**Login:** PHX-POCxxx-User01@nutanixdc.local (up to PHX-POCxxx-User20), **Password:** *<Provided by Instructor>*


Parallels VDI
.................

PHX Based Clusters Login to: https://xld-uswest1.nutanix.com

RTP Based Clusters Login to: https://xld-useast1.nutanix.com

**Nutanix Employees** - Use your **NUTANIXDC** credentials
**Non-Employees** - Use **Lab Access User** Credentials


Nutanix Version Info
++++++++++++++++++++

- **AHV Version** - AHV 20170830.337
- **AOS Version** - 5.16.1.x
- **PC Version** - 5.16.1.x
