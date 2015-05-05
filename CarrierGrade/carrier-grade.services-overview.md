---
layout: default
title: "HP Helion OpenStack&#174; Carrier Grade (Alpha): Services Overview"
permalink: /helion/openstack/carrier/services/overview/
product: carrier-grade
product-version1: HP Helion OpenStack
product-version2: HP Helion OpenStack 1.1
role1: Systems Administrator 
role2: Cloud Architect 
role3: Storage Administrator 
role4: Network Administrator 
role5: Service Developer 
role6: Cloud Administrator 
role7: Application Developer 
role8: Network Engineer 
authors: Paul F

---
<!--UNDER REVISION-->

<script>

function PageRefresh {
onLoad="window.refresh"
}

PageRefresh();

</script>


<p style="font-size: small;"> <a href=" /helion/openstack/services/overview/">&#9664; PREV</a> | <a href="/helion/openstack/">&#9650; UP</a> | <a href="/helion/openstack/support-matrix/"> NEXT &#9654</a> </p>  


# HP Helion OpenStack&#174; Carrier Grade (Alpha): Services Overview

OpenStack is comprised of several integrated services. Each service works through an API (application programming interface) that allows services to work together and allows users to interact with the services.


## HP Helion OpenStack services

HP Helion OpenStack includes a number of additional services to work with your cloud. 

- [Service User Accounts](#service)
- [OpenStack Services](#OpenStack)
- [Dashboard services](#dash)
- [For more information](#info)


In addition to the APIs, you can interact with the most services through a graphic user interface (dashboard or console) or a command line interface (CLI).

### Service User Accounts {#service}
The HP Helion OpenStack installation process creates a **service** **user** account for each installed service. Service user accounts require elevated privileges to validate end user tokens. It is therefore strongly recommended that you do ***not*** add these service user accounts to any project because this could allow project users to access services they should not have permission to access. 

The service user accounts include, but are not limited to, the following:

- Swift
- Nova
- Neutron
- Sherpa
- Glance
- Cinder
- Heat
- Keystone
- Ceilometer
- Ceph

### OpenStack Services {#OpenStack}

The following services are foundation technologies used by the HP Helion OpenStack. Based on OpenStack technology, HP Helion OpenStack comprises of a set of services and architecture that defines a data-center-level operating system (DCOS).

For information on enabling and maintaining each of these OpenStack services, see [Network Administrator Notes](/helion/openstack/carrier/network/administrator/notes/).

**Compute Operations (Nova)**. The Compute service manages the hypervisors and virtual machines in your environment. 

See [Overview of the Compute service](/helion/openstack/carrier/services/compute/overview/).
<!-- Hiding for Alpha
**Identity Management (Keystone)**. The Identity Management service enables you to create and administer users and security groups, and control access to your cloud environment. 

See [Overview of the Identity Management service](/helion/openstack/carrier/services/identity/overview/).
-->
<!-- Hiding for Alpha
**Image Operations (Glance)**. The Image Operations service enables you to create and maintain server images, which you can use to launch virtual machines across the cloud. Also known as **Glance**.

See [Overview of the Image service](/helion/openstack/carrier/services/imaging/overview/).
-->
**Networking Operations (Neutron)**. The Networking service enables you to create and manage virtual networks. 
See [Overview of the Networking service](/helion/openstack/carrier/services/networking/overview/).

<!-- Hiding for Alpha
**Object Operations (Swift)**. The Object Operations service enables you to store and retrieve data. Object Storage is a distributed storage system for static data such as virtual machine images, photo storage, email storage, backups and archives. 

See [Overview of the Object Operations service](/helion/openstack/carrier/services/object/overview/).

**Orchestration (Heat)**. The Orchestration service provides a template-based orchestration for describing a cloud application. A Heat template is a [YAML](http://www.yaml.org/) file that describes the infrastructure for a cloud application. Templates contain vendor-independent specifications for launching a particular service or application.  

See [Overview of the Orchestration service](/helion/openstack/carrier/services/orchestration/overview/).
-->

**Volume Operations (Cinder)**. The Volume Operations service enables you to attach storage volumes to the virtual instances in your cloud environment. The service provides persistent block level storage devices for use with your Compute instances. 

See [Overview of the Volume Operations Service](/helion/openstack/carrier/services/volume/overview/).

<!-- Hiding for Alpha
**Metering (Ceilometer)**. The Metering service enables a single infrastructure to collect measurements throughout your cloud environment. 

See [Overview of the Metering Service](/helion/openstack/carrier/services/reporting/overview/).


**Ceph**. Ceph is an Open Source, scalable, software defined storage running on HP Servers which provides block and object storage with unified management. 

See [Overview of the Ceph Service]( /helion/openstack/carrier/services/ceph/)


**Loom**. The Loom service facilitates the comprehension and manipulation of complex systems using the Unity dashboard.

See [Overview of the Loom Service](/helion/openstack/carrier/services/loom/overview/).
-->

<!-- Hiding for Alpha
### HP Services ### {#hp}

The following services have been developed by HP for use with the HP Helion OpenStack.

**Sirius**. HP Helion OpenStack Sirius service assists the Cloud Administrator in the configuration of storage services (like Cinder and Swift) which run in the Overcloud on various storage devices.

See [Overview of Sirius Service](/helion/openstack/carrier/services/sirius/overview/)

**EON**. ESX on border (EON) service is an inventory which interacts with the VMware vCenter server and collects the information available at the datacenters and clusters. These information is used for deployment and configuration of ESX Proxy Compute node. EON service is deployed in undercloud controller node.

See [Overview of EON Service](/helion/openstack/carrier/services/eon/overview/)

**Sherpa**. The Sherpa service provides a link to the remote web catalog. The catalog provides a repository of software that can be purchased and downloaded into the Cloud OS environment.  

See [Overview of Sherpa Service](/helion/openstack/carrier/services/sherpa/overview/).
-->

## Dashboard services ## {#dash}

HP Helion OpenStack uses the following services or software to present user interfaces to aspects of HP Helion OpenStack.

**Horizon** The Horizon service is the basis of the [HP Helion OpenStack dashboards](/helion/openstack/carrier/dashboard/how-works/) for creating and managing HP Helion OpenStack resources. The Horizon dashboard is developed by HP for use with HP Helion OpenStack. 

You can use the HP Helion OpenStack dashboard to view, allocate, and manage all virtual resources within a cloud. 
See [Overview of the Horizon Service](/helion/openstack/services/horizon/overview/).

<!-- Hiding for Alpha
**Icinga** The Icinga service, which runs in the undercloud, helps cloud admins monitor the disk usage of Swift storage node(s). Icinga is an open-source software project.

See [Overview of the Icinga Service](/helion/commercial/carrier/services/icinga/).

**Kibana**. The Kibana service, which runs in the undercloud, is the user interface into the [centralized logging service](/helion/openstack/carrier/services/logging/overview/) that helps view logging data across the HP Helion OpenStack cloud. Kibana is an open-source software project.

See [Overview of the Icinga Service](/helion/commercial/carrier/services/kibana/).
-->

<!-- Hiding for Alpha
## Other services and features {#Other}

The following services and features can be used with HP Helion OpenStack.

**Centralized Logging**. The HP Helion OpenStack Centralized Logging uses a number of services and systems to collect logs throughout the cloud into a central system. The administrator can use a single graphic interface to view log information in charts, graphs, tables, histograms, and other forms. 

See [Centralized Logging Overview](/helion/openstack/carrier/services/logging/overview/).

**DNSaaS**. The HP Helion OpenStack DNSaaS (Domain Name System as a Service) provides a way to display, create, modify, and delete DNS records on the assigned DNS server network. 

See [Overview of the DNS as a Service](/helion/openstack/carrier/install/dnsaas/).
-->

## For more information {#info}
For information on how to operate your cloud we suggest you read the [OpenStack Operations Guide](http://docs.openstack.org/ops/). The **Architecture** section contains useful information about how an OpenStack Cloud is put together. However, HP Helion OpenStack takes care of these details for you. The **Operations** section contains information on how to manage the system.

For more information on installing the command-line interface for interacting with services, see [installing the OpenStack command-line clients](http://docs.openstack.org/user-guide/content/install_clients.html).


 <a href="#top" style="padding:14px 0px 14px 0px; text-decoration: none;"> Return to Top &#8593; </a>

----