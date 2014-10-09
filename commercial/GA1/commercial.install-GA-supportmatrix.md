---
layout: default
title: "HP Helion OpenStack&#174; Support Matrix"
permalink: /helion/openstack/ga/support-matrix/
product: commercial.ga

---
<!--PUBLISHED-->


<script>

function PageRefresh {
onLoad="window.refresh"
}

PageRefresh();

</script>

<!--
<p style="font-size: small;"> <a href="/helion/openstack/services/overview/">&#9664; PREV</a> | <a href="/helion/openstack/">&#9650; UP</a> | <a href="/helion/openstack/ga/install/overview/">NEXT &#9654;</a> </p>
-->

# HP Helion OpenStack&#174; Support Matrix
 
To ensure the performance and stability of the HP Helion OpenStack environment, it is very important to meet the requirements and conform to the recommendations.

This page provides an overview of the hardware and software that is supported for HP Helion OpenStack, including setup and configuration information. 

* [Supported Hardware](#supportedhw)
* [Supported Configurations](#supportedconfigurations)
* [Hardware Requirements](#baremetal)
* [Software Requirements](#software-requirements)
	* [Other seed cloud host requirements and recommendations](#otherseed)

##Deployment Architecture<a name="deploy-arch"></a>

The following diagrams depict simplified deployment scenarios:

* <a href="javascript:window.open('/content/documentation/media/topology_kvm.png','_blank','toolbar=no,menubar=no,resizable=yes,scrollbars=yes')">KVM deployment of HP Helion OpenStack</a> (opens in a new window)
* <a href="javascript:window.open('/content/documentation/media/topology_esx.png','_blank','toolbar=no,menubar=no,resizable=yes,scrollbars=yes')">ESX deployment of HP Helion OpenStack</a> (opens in a new window)

## Supported Hardware {#supportedhw}

The following hardware has been tested and verified to work with HP Helion OpenStack:

### HP Proliant BladeSystem

- [BL160 Gen8](http://www8.hp.com/us/en/products/proliant-servers/#!view=grid&page=1&facet=ProLiant-SL-Scalable)
- [BL420c Gen8](http://www8.hp.com/us/en/products/proliant-servers/product-detail.html?oid=5249562)
- [BL460c Gen8](http://www8.hp.com/us/en/products/proliant-servers/product-detail.html?oid=5177949)
- [BL465c Gen8](http://www8.hp.com/us/en/products/proliant-servers/product-detail.html?oid=5193137)
- [BL660c Gen8](http://www8.hp.com/us/en/products/proliant-servers/product-detail.html?oid=5268287)

### HP Proliant Rack Servers

- [DL310 Gen8](http://www8.hp.com/us/en/products/proliant-servers/#!view=grid&page=1&facet=ProLiant-SL-Scalable)
- [DL320 Gen8](http://www8.hp.com/us/en/products/proliant-servers/product-detail.html?oid=5379527)
- [DL360 Gen8](http://www8.hp.com/us/en/products/proliant-servers/product-detail.html?oid=5249570)
- [DL380 Gen8](http://www8.hp.com/us/en/products/proliant-servers/product-detail.html?oid=5177957)
- [DL385 Gen8](http://www8.hp.com/us/en/products/proliant-servers/product-detail.html?oid=5249584)
- [DL560 Gen8](http://www8.hp.com/us/en/products/proliant-servers/product-detail.html?oid=5268290)
- [DL580 G7](http://www8.hp.com/us/en/products/proliant-servers/product-detail.html?oid=4142916)
- [DL580 Gen8 Legacy boot support only, no uEFI](http://www8.hp.com/us/en/products/proliant-servers/product-detail.html?oid=5177957)

### HP Proliant Tower Servers

- [ML310 Gen8](http://www8.hp.com/us/en/products/proliant-servers/product-detail.html?oid=5249594)
- [DL350 Gen8](http://www8.hp.com/us/en/products/proliant-servers/product-detail.html?oid=5260584)
<br>
### HP Proliant Scalable Systems

- [SL230s Gen8](http://www8.hp.com/us/en/products/proliant-servers/#!view=grid&page=1&facet=ProLiant-SL-Scalable)
- [SL250s Gen8](http://www8.hp.com/us/en/products/proliant-servers/product-detail.html?oid=5177941)
- [SL270s Gen8](http://www8.hp.com/us/en/products/proliant-servers/product-detail.html?oid=5177945)
- [SL4540 Gen8](http://www8.hp.com/us/en/products/proliant-servers/product-detail.html?oid=5287871)

### IBM systems ###

- [IBM System x3550 M4 Server](http://www-03.ibm.com/systems/x/hardware/rack/x3550m4/)
<br>CPU: Intel(R) Xeon(R) CPU E5-2650 0 @ 2.00GHz
<br>Storage controller: LSI MegaRAID <ServerRAID M5110>  01.33.00
<br>Network: Intel(R) Gigabit Ethernet Network Driver - version 5.0.5-k
<br>Memory: 256 GB
 

### Dell systems###

- [Power Edge R620](http://www.dell.com/us/business/p/poweredge-r620/pd)
<br>BIOS version: 1.4.8
<br>CPU: 2 (Intel(R) Xeon(R) CPU E5-2650 0 @ 2.00GHz   max 3600 MHz  8 cores
<br>Memory: 256 GB
<br>Network Device: Broadcom   (4 Port)
<br>Storage controller: Integrated RAID controller 1:





## Supported Configurations<a name="supportedconfigurations"></a>

HP supports the following configurations for HP Helion OpenStack deployment:



- Host Interconnects/Protocols: 
   
      * 10Gb Software iSCSI
      * 8Gb and 16Gb Fibre-Channel
      * Software iSCSI and Fibre-Channel under KVM

- Target Interconnects: 
   
      * 8Gb FC SAN
      * 10Gb iSCSI CNA/NIC
      

- 3PAR InForm OS Version: 3.1.3 MU1 
   
     
## Hardware Requirements<a name="baremetal"></a>

You must have the following hardware configuration:

- At least 8 and no more than 100 baremetal systems meeting the requirements as listed below.

Additional requirements are as follows:

- For systems with multiple NICs, the NICs must not be connected to the same Layer 2 network or VLAN.
- Capable of hosting VMs
- The boot order configured with Network/PXE boot as the first option:
	- For example, to set the boot order for a HP SL390, from the iLO prompt enter `set system1/bootconfig1/bootsource5 bootorder=1`.
	- To unset, enter `set system1/bootconfig1/bootsource5 bootorder=5`.

- The BIOS configured: 
	- to the correct date and time
	- with only one network interface enabled for PXE/network boot and any additional interfaces should have PXE/network boot disabled

- The latest firmware recommended by the system vendor for all system components, including the BIOS, BMC firmware, disk controller firmware, drive firmware, network adapter firmware, and so on.
- For Compute nodes, Intel or AMD hardware virtualization 
- support required. The CPU cores and memory requirements must be sized based on the VM instances hosted by the Compute node.

	**Important:** Since the installer currently uses only the first available disk, all servers must have RAID controllers pre-configured to present their storage as a single, logical disk. RAID across multiple physical discs is strongly recommended for both  performance and resilience.

	On the controller and compute nodes, make sure the RAID array is congifured to reflect a total size of less than 4TB.

The following table lists the minimum requirements required for installation of each type of node. The maximum of 2TB for the undercloud and overcloud nodes is mandatory for installation. 

<table style="text-align: left; vertical-align: top;">

<tr style="background-color: #C8C8C8; text-align: left; vertical-align: top;">
<th>Node Type</th>
<th>Minimum Number</th>
<th>Server Hardware</th>
<th>Minimum Requirements and Recommendations</th>
</tr>


<tr style="background-color: white; color: black; text-align: left; vertical-align: top;">
<td rowspan="4"> Seed Cloud Host </td>
<td rowspan="4">1</td>
<td>Disk </td>
<td> 1TB - This host will store the downloaded images as well as act as a host where backup data is preserved.</td>
</tr>
<tr style="background-color: white; color: black; text-align: left; vertical-align: top;">
<td>Memory </td>
<td colspan=2>16GB</td>
</tr>
<tr style="background-color: white; color: black; text-align: left; vertical-align: top;">
<td>Network </td>
<td> 1 x 10GB NIC</td>
</tr>
<tr style="background-color: white; color: black; text-align: left; vertical-align: top;">
<td>CPU </td>
<td> 4 CPU cores</td>
</tr>

<tr style="background-color: white; color: black; text-align: left; vertical-align: top;">
<td rowspan="4"> Undercloud Controller</td>
<td rowspan="4">1</td>
<td>Disk </td>
<td>512GB - 2TB</td>
</tr>
<tr style="background-color: white; color: black; text-align: left; vertical-align: top;">
<td>Memory </td>
<td> 32GB </td>
</tr>
<tr style="background-color: white; color: black; text-align: left; vertical-align: top;">
<td>Network </td>
<td> 1 x 10GB NIC with PXE support</td>
</tr>
<tr style="background-color: white; color: black; text-align: left; vertical-align: top;">
<td>CPU </td>
<td>8 CPU cores - Intel or AMD 64-bit processor </td>
</tr>

<tr style="background-color: white; color: black; text-align: left; vertical-align: top;">
<td rowspan="4"> Overcloud Controller </td>
<td rowspan="4">3</td>
<td>Disk </td>
<td> 512GB - 2TB
 </td>
</tr>
<tr style="background-color: white; color: black; text-align: left; vertical-align: top;">
<td>Memory </td>
<td>32GB </td>
</tr>
<tr style="background-color: white; color: black; text-align: left; vertical-align: top;">
<td>Network </td>
<td> 1 x 10GB NIC with PXE support</td>
</tr>
<tr style="background-color: white; color: black; text-align: left; vertical-align: top;">
<td>CPU </td>
<td>8 CPU cores - Intel or AMD 64-bit processor </td>
</tr>

<tr style="background-color: white; color: black; text-align: left; vertical-align: top;">
<td rowspan="4"> Overcloud Compute Server </td>
<td rowspan="4">1</td>
<td>Disk </td>
<td> 512GB - 2TB</td>
</tr>
<tr style="background-color: white; color: black; text-align: left; vertical-align: top;">
<td>Memory </td>
<td>32GB - Memory must be sized based on the VM instances hosted by the Compute node.</td>
</tr>
<tr style="background-color: white; color: black;">
<td>Network </td>
<td> 1 x 10GB NIC with PXE support</td>
</tr>
<tr style="background-color: white; color: black; text-align: left; vertical-align: top;">
<td>CPU </td>
<td>8 CPU cores - Intel or AMD 64-bit processor with hardware virtualization support. The CPU cores must be sized based on the VM instances hosted by the Compute node. </td>
</tr>

<tr style="background-color: white; color: black; text-align: left; vertical-align: top;">
<td rowspan="4"> Overcloud Swift server </td>
<td rowspan="4">2</td>
<td>Disk </td>
<td> 512GB - 2TB
</td>
</tr>
<tr style="background-color: white; color: black; text-align: left; vertical-align: top;">
<td>Memory </td>
<td>32GB </td>
</tr>
<tr style="background-color: white; color: black;">
<td>Network </td>
<td> 1 x 10 GB NIC with PXE support</td>
</tr>
<tr style="background-color: white; color: black; text-align: left; vertical-align: top;">
<td>CPU </td>
<td> 8 CPU cores - Intel or AMD 64-bit processor</td>
</tr>
</table>

**Notes:** 

- For installations with KVM hypervisor support, one or more additional nodes are required for VSA block storage.

- After the installation is complete, you can use the Block Storage and Object Operation services to add further storage capacity as allowed by your hardware.


<!--
## Usable Capacity<a name="usable_capacity"></a>

The following table maps the minimum server configuration into usable capacity of the overcloud.


<table style="text-align: left; vertical-align: top;">

<tr style="background-color: #C8C8C8; text-align: left; vertical-align: top;">
<th>Service</th>
<th>Usable capacity</th>
<th>Notes</th>
</tr>

<tr style="background-color: white; color: black; text-align: left; vertical-align: top;">
<td> VMs </td>
<td> 6 standard.medium (4GB memory, 80GB disk) </td>
<td> Assumes 8GB of memory and 200GB of disk overhead. Capacity increases linearly with Compute nodes.</td>
</tr>

<tr style="background-color: white; color: black; text-align: left; vertical-align: top;">
<td> Volumes </td>
<td> 1800GB</td>
<td> Capacity is fixed</td>
</tr>		

<tr style="background-color: white; color: black; text-align: left; vertical-align: top;">
<td> Object storage</td>
<td> 400GB; equivalent to:
<ul><li>160 images, based on 2.5GB images</li>
or
<li>40 volume backups, based on 10GB volumes</li>
</li> </td>
<td> In addition to your objects, object storage is used for images and volume backups. With 640 GB per server (after subtracting 60 GB for the OS) this leaves about 400 usable GB (1280/3.2). This is assuming an average Linux image/snapshot of 2.5 GB (the 2.5 GB is the average size of images in the swift public cloud in US-East) and a 10 GB Cinder volume backup.

<p>Note: These are the maximum figures assuming the storage is used exclusively for that type of object.</p>  </td>
</tr>			
</table>
-->


## Software Requirements <a name="software-requirements"></a>

Software requirements for the Seed Cloud Host:

Ubuntu 14.04 with the following packages.

- xrdp 
- xfce4 
- qemu-kvm 
- libvirt-bin 
- openvswitch-switch 
- openvswitch-common 
- python-libvirt 
- libssl-dev 
- libffi-dev 
- virt-manager 
- chromium-browser
- openjdk‐7‐jdk:i386


There are no software requirements for the Undercloud and Overcloud controllers.


### Other seed cloud host requirements and recommendations ## {#otherseed}

Other requirements and recommendations for the seed cloud host are as follows:

- The Ubuntu 14.04 operating system must be installed
- A browser to access the undercloud or overcloud
- A desktop emulator, such as [Virtual Machine Manager](http://virt-manager.org/), to monitor and access cloud nodes
- A simple command line tool installed, such as [IPMItool](http://sourceforge.net/projects/ipmitool/), to determine the state of cloud nodes.

	**Important:** This system might be reconfigured during the installation process so a dedicated system is recommended. Reconfiguration might include installing additional software packages, and changes to the network or visualization configuration.


## Next Steps<a name="next"></a>

Review the [HP Helion OpenStack&#174; Technical Overview](/helion/openstack/ga/technical-overview/).

Prepare your environment for the installation, see [HP Helion OpenStack&#174; Installation: Prerequisites](/helion/openstack/ga/install/prereqs/).



<a href="#top" style="padding:14px 0px 14px 0px; text-decoration: none;"> Return to Top &#8593; </a>

----
####OpenStack trademark attribution
*The OpenStack Word Mark and OpenStack Logo are either registered trademarks/service marks or trademarks/service marks of the OpenStack Foundation, in the United States and other countries and are used with the OpenStack Foundation's permission. We are not affiliated with, endorsed or sponsored by the OpenStack Foundation, or the OpenStack community.*