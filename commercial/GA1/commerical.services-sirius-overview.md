---
layout: default
title: "HP Helion OpenStack&#174; Sirius Service Overview"
permalink: /helion/openstack/ga/services/sirius/overview/
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
<p style="font-size: small;"> <a href="/helion/openstack/services/tripleo/overview/">&#9664; PREV</a> | <a href="/helion/openstack/services/overview/">&#9650; UP</a> | <a href="/helion/openstack/services/identity/overview/"> NEXT &#9654</a> </p>
-->

# HP Helion OpenStack&#174; Sirius Service Overview #

The HP Helion OpenStack Sirius Service is a REST-based web service for storage device  management. It is used to configure of storage services such as Cinder and Swift that run in the overcloud and manage various storage devices. It also provides REST-based automated deployment and management of certain sets of storage devices such as HP StoreServ FC, HP StoreServ iSCSI, and HP StoreVirtual. 

The Cloud Administrator is the primary user. Like the other HP Helion OpenStack services, the HP Helion OpenStack Sirius Service is compliant with the Keystone authentication service.

All the devices managed by Sirius are consumed by the overcloud to realize a cloud storage offered to cloud users. The service runs in the Undercloud to realize all its operation.


## Working with the Sirius Service ##

To perform tasks using the Sirius service, you can use the Horizon dashboards or CLI.

### Using the dashboards<a name=UI""></a>

You can use the [HP Helion OpenStack Dashboard](/helion/openstack/dashboard/how-works/) to work with the Sirius service.

###Using the CLI<a name="cli"></a>

You can use the command-line interface to access HP Sirius service. See [Configuring Your Storage Using Sirius](/helion/openstack/ga/sirius-cli/)

For more information on installing the CLI, see [Install the OpenStack command-line clients](http://docs.openstack.org/user-guide/content/install_clients.html).

## For more information ##

For more general information on how to operate your cloud, reference the [OpenStack Operations Guide](http://docs.openstack.org/ops/). The *Architecture* section contains useful information about how an OpenStack Cloud is put together. However, the HP Helion OpenStack takes care of these details for you. The *Operations* section contains information on how to manage the system.

 <a href="#top" style="padding:14px 0px 14px 0px; text-decoration: none;"> Return to Top &#8593; </a>

----
####OpenStack trademark attribution
*The OpenStack Word Mark and OpenStack Logo are either registered trademarks/service marks or trademarks/service marks of the OpenStack Foundation, in the United States and other countries and are used with the OpenStack Foundation's permission. We are not affiliated with, endorsed or sponsored by the OpenStack Foundation, or the OpenStack community.*