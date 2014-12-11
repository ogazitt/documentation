---
layout: default
title: "HP Helion OpenStack&#174; HP Helion OpenStack Commercial Manage Flavors"
permalink: /helion/commercial/dashboard/managing/flavors/
product: commercial.ga

---
<!--UNDER REVISION-->

<script>

function PageRefresh {
onLoad="window.refresh"
}

PageRefresh();

</script>

<!--
<p style="font-size: small;"> <a href="/helion/commercial/ga1/install/">&#9664; PREV</a> | <a href="/helion/commercial/ga1/install-overview/">&#9650; UP</a> | <a href="/helion/commercial/ga1/">NEXT &#9654;</a> 
-->

# HP Helion OpenStack&#174; Managing Compute Flavors</h1>

Compute flavors are machine configurations that describe the amount of memory, number of CPUs, and storage capacity of instances. The moment you register a chassis, a flavor is created by default. You can use the default flavor or create a flavor of your choice.

An admin user can create, edit, and delete instances as needed. 

* [Create a flavor](#createflavor)
* [Edit a flavor](#editflavor")
* [Delete a flavor](#deleteflavor)

### Create a flavor ### {#createflavor}

To create a flavor:

1. [Launch the HP Helion OpenStack Helion Dashboard](/helion/openstack/dashboard/login/).

2 Click the **Flavors** link on the **Admin** dashboard **System** panel.
	The flavors in the domain are listed. 

3. Click **Create Flavor**. 

4. In the **Create Flavor** screen, click the **Flavor Info** tab (should be active).

5. Enter the name that you want to assign to the flavor.</li>
	* In the **ID** field, enter a unique string that identifies this flavor.</li>
	* In the **VCPUs** field, enter the required number of virtual CPUs to be included in the flavor.</li>
	* In the **RAM MB** field, enter the virtual machine memory in megabytes to be included in the flavor.</li>
	* In the **Root Disk GB** field, enter the size for the virtual root disk size in gigabytes.</li>
	* From the **Ephemeral disk GB** field, enter the size of a secondary ephemeral data disk in gigabytes. This is an empty, unformatted disk and exists only for the life of the instance.</li>
	* From the **Swap Disk MB** field, enter the amount of swap space allocation for the flavor.</li>

6. Click the **Flavor Access** tab.

7. Add the flavor to a project by clicking the **+** icon next to each project in the **All Projects** column.

	By default, no project is specified as having access the flavor. If none is specified, all projects can access the flavor.

8. Click **Create Flavor** to create a new the flavor.<br>
A message is displayed on successful creation.

### Edit a flavor ### {#editflavor}</h3>

To edit a flavor:

1. [Launch the HP Helion OpenStack Helion Dashboard](/helion/openstack/dashboard/login/).

2. Click the **Flavors** link on the **Admin** dashboard **System** panel.

	The flavors in the domain are listed. 

3. For the flavor you want to modify, click **Edit Flavor**. 

4. In the **Edit Flavor** screen, click the **Flavor Info** tab (should be active).

5. Use the **Flavor Info** and **Flavor Access** tabs to modify the flavor as needed. See <a href="#createflavor">Create a flavor</a> for a description of each field.

6. When done editing, click **Save**.

A message is displayed on successful edit.

### Delete a flavor ### {#deleteflavor}</h3>

Instances that use the flavor are not affected when a flavor is deleted.

To delete a flavor:

1. [Launch the HP Helion OpenStack Helion Dashboard](/helion/openstack/dashboard/login/).

2. Click the **Flavors** link on the **Admin** dashboard **System** panel.

	The flavors in the domain are listed. 

3. For the flavor you want to modify, click **More &gt; Delete Flavor**. 

4. In the confirmation screen, click **Delete Flavor**.
<p>A message is displayed on successful delete. 

<a href="#top" style="padding:14px 0px 14px 0px; text-decoration: none;"> Return to Top &#8593; </a>


----
####OpenStack trademark attribution
*The OpenStack Word Mark and OpenStack Logo are either registered trademarks/service marks or trademarks/service marks of the OpenStack Foundation, in the United States and other countries and are used with the OpenStack Foundation's permission. We are not affiliated with, endorsed or sponsored by the OpenStack Foundation, or the OpenStack community.*