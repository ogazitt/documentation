---
layout: default
title: "HP Helion OpenStack Managing Access to a Flavor"
permalink: /helion/commercial/dashboard/managing/flavors/access/
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

# HP Helion OpenStack&#174; Managing access to a flavor #

Compute flavors are machine configurations that describe the amount of memory, number of CPUs, and storage capacity of instances. 

As an admin, you can [allow specific projects to have access to a flavor](#add) or [prevent a project from accessing a flavor](#remove).

### Allowing a project to access a flavor ### {#add}

1. [Launch the HP Helion OpenStack Helion Dashboard](/helion/openstack/dashboard/login/).

2. Click the **Flavors** link on the **Admin** dashboard **System** panel.

	The flavors for in the domain are listed. 

3. For the flavor you want to modify, click **More &gt; Modify Access**.

4. Click the **+** icon next to a project in the **All Projects** column to allow the project to access the flavor.

	By default, no project is specified as having access the flavor. If none is specified, all projects can access the flavor.

5. Click **Save** to create a new the flavor.<br>

	A message is displayed on successful change.

### Preventing a project from accessing a flavor ### {#remove}

1. [Launch the HP Helion OpenStack Helion Dashboard](/helion/openstack/dashboard/login/).

2. Click the **Flavors** link on the **Admin** dashboard **System** panel.

	The flavors for in the domain are listed. 

3. For the flavor you want to modify, click **More &gt; Modify Access**.

4. Click the **-** icon next to a project in the **Selected projects** column to remove the flavor from the project.

	By default, no project is specified as having access the flavor. If none is specified, all projects can access the flavor.

5. Click **Save** to create a new the flavor.<br>
<p>A message is displayed on successful change.

<a href="#top" style="padding:14px 0px 14px 0px; text-decoration: none;"> Return to Top &#8593; </a>


----
####OpenStack trademark attribution
*The OpenStack Word Mark and OpenStack Logo are either registered trademarks/service marks or trademarks/service marks of the OpenStack Foundation, in the United States and other countries and are used with the OpenStack Foundation's permission. We are not affiliated with, endorsed or sponsored by the OpenStack Foundation, or the OpenStack community.*