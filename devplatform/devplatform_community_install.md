---
layout: default-devplatform
title: "HP Helion OpenStack Development Platform Community Installation"
permalink: /helion/devplatform/install/community/
product: devplatform

---
<!--PUBLISHED-->


<script>

function PageRefresh {
onLoad="window.refresh"
}

PageRefresh();

</script>
<!--
<p style="font-size: small;"> <a href="/helion/openstack/install/esx/">&#9664; PREV</a> | <a href="/helion/openstack/install-overview/">&#	9650; UP</a> | <a href="/helion/openstack/install/dnsaas/">NEXT &#9654;</a> </p>
-->

# HP Helion Development Community Installation and Configuration

The HP Helion Development Platform currently contains four products: [Application Lifecycle Service (ALS), Marketplace Service, Messaging Service and Database Service](/helion/devplatform/).

The following topics explain how to install and configure the HP Helion Development Platform.

* [Prerequisites](#prerequisites)
* [Installing the HP Helion Development Platform](#installing-the-hp-helion-development-platform)
* [Install the Messaging Service](#messaging-install)
* [Install the Application Lifecycle Service](#als-install)
* [Install the Database Service](#database-install)
* [Install the Marketplace Service](#marketplace-install)
* [Troubleshooting](#troubleshooting)

## Prerequisites {#prerequisites}

The HP Helion Development Platform is installed in the overcloud of HP Helion OpenStack Community Edition.  The HP Helion Development Platform has the same [prerequisites as HP Helion OpenStack Community Edition](/helion/community/hwsw-requirements/).

The system running the installer needs to have Python 2.7. Most modern operating systems include this as part of their base toolkit. This document is geared toward a Linux operating system but this does not preclude the installer from running on other operating systems with some minor modifications to the command-line statements used in this document.
 
The installer requires the following packages. If they are not found, it will prompt you to install them.

* python-dev 
* libffi-dev 
* libssl-dev 
* python-virtualenv
* python-pip

Use the following command:

	sudo apt-get install -y python-dev libffi-dev libssl-dev python-virtualenv python-pip
    
## Installing the HP Helion Development Platform {#installing-the-hp-helion-development-platform}

This section describes how to download and install the HP Helion Development Platform.

* [Downloading and unpacking the installation file](#download)
* [Preparing to run the installer](#prepare)

### Downloading and unpacking the installation file {#download}

The installation of the HP Helion Development Platform for the HP Helion OpenStack Community Edition is provided as a small compressed TAR file.  The images for the actual services will be downloaded by the installer.

You can register and download the package from the following URL:

[HP Helion Development Platform](https://helion.hpwsportal.com/#/Product/%7B%22productId%22%3A%221245%22%7D/Show)

To begin the installation, unpack the TAR file:

	tar -zxvf hp_helion_devplatform_community.tar.gz.csu

This creates and populates a `dev-platform-installer` directory.

	cd dev-platform-installer

### Preparing to run the installer {#prepare}

If your network uses a proxy, it might be necessary to set the proxy shell variable.

	export https_proxy=<ip address or url of http proxy> 

Run this command to prepare the installer and verify the prerequisites are met. 

	./DevelopmentPlatform_Setup.sh -p {admin_user_password} -a {auth_host_ip_address}

Optionally, you can run the command using the user name, tenant (project) and region. By default, the user name is `admin`, the tenant name is `admin`, and the region is `regionOne`.
    
	./DevelopmentPlatform_Setup.sh -p {admin_user_password} -a {auth_host_ip_address} -u {username} -t {tenant_name} -r {region_name}

If you need help with this script, use the help feature:

	./DevelopmentPlatform_Setup.sh -h

After the install command completes, the following output is displayed:

	2014-06-17 16:53:19.765       INFO Install Complete

## Install the Messaging Service {#messaging-install}

This section provides details on installing the HP Helion Development Platform Messaging service.

* [Connect to the Download Service](#marketplace-connect)
* [Download and Configure the Messaging Service](#messaging-download)

### Connect to the Download Service {#marketplace-connect}

1. Open Horizon and login as the *Admin* user. Then click on the **Admin** panel in Horizon and select **Development Platform**. Finally, click **Configure Services**.

2. Click the **Connect** button on the **Configure Services** panel and enter your username and password for the HP Cloud OS Content Delivery Network. 

	If you do not have an account, click the **Sign-up** button.

### Download and Configure the Messaging Service {#messaging-download}

1. Open Horizon and login as the *Admin* user. Then click on the **Admin** panel in Horizon and select **Development Platform**. Finally, click **Configure Services**.

2. In the **Configure Services** panel locate the **Messaging (Beta)** item in the **Configure Services** table and select **Download Service**. 

	It might take several minutes for the download to complete.

2. After the download is complete, click the **Configure Service** button to configure the Messaging service and wait for the configuration step to complete.

3. Log out of the Horizon dashboard. 

4. Log back into the Horizon dashboard as a non-admin user and click on the **Messaging** panel under the current project to begin using the Messaging Service.

## Install the Application Lifecycle Service (ALS) {#als-install}
This section provides details on installing the HP Helion Development Platform Application Lifecycle service.

* [Prerequisites](#als-pre)
* [Connect to the Download Service](#als-connect)
* [Download and Configure the Application Lifecycle Service](#als-download)

### Prerequisites {#als-pre}

For the Application Lifecycle service to install dependencies for deployed applications, you must provide Application Lifecycle Service with outbound Internet connectivity. 

This process is documented in Step 7 of ["Starting the seed and building your cloud"](http://docs.hpcloud.com/helion/community/install/#startseed) in the baremetal installation instructions.  If an HTTP Proxy is required for Internet downloads, follow the instructions in the [Administration Guide](http://docs.hpcloud.com/als/v1/admin/server/configuration/#http-proxy).

### Connect to the Download Service {#als-connect}

1. Open Horizon and login as the *Admin* user. Then click on the **Admin** panel in Horizon and select **Development Platform**. Finally, click the **Configure Services** sub-panel.

2. Click the **Connect** button on the **Configure Services** panel and enter your user name and password for the HP Cloud OS Content Delivery Network. 

	If you do not have an account, click the **Sign-up** button.

### Download and Configure the Application Lifecycle Service {#als-download}

1. In the **Configure Services** panel locate the Application Lifecycle Service item in the Configure Services table and select **Download Service** and wait for the download to complete.

2. Once the download is complete, click **Configure Service** to configure the Application Lifecycle Service and wait for the configuration step to complete.

3. Log out from the Horizon dashboard. Log back into the Horizon dashboard as a non-admin user and click the **Application Lifecycle Service** panel under the current project to being using Application Lifecycle Services.

## Install the Database Service {#databse-install}

This section provides details on installing the Database Service from the Development Platform.

* [Prerequisites](#database-pre)
* [Connect to the Download Service](#database-connect)
* [Download and Configure the Database Service](#database-connect)

### Prerequisites {#database-pre}

Before installing, make sure the following prerequisites are met:

* [Configure the Service Network](#databse-service)
* [Check Project Quotas](#database-quota)
* [Connect to the Download Service](#database-connect)

#### Configure the Service Network {#databse-service}

To configure the Database Service it needs an additional network for administrative purposes. This network is currently not used in Community Edition but must exist in order for Database Service to properly install.

1. Open Horizon and login as the *Admin* user.

2. Click **Project**.

3. Click **Network** and then the **Networks** tab.

4. Click **Create Network**.

5. In **Network Name** field, enter `SVC` for the name of the network.

6. Click **Next**.

7. In the **Network Address** field, enter a CIDR that does not conflict with other services (e.g. 172.10.0.0/24).

6. Click **Next**.

7. Click **Create**.

#### Check Project Quotas {#database-quota}

The Database Service will be installed into the **Admin**project of the Helion OpenStack overcloud. The **Admin** project must have sufficient quota available and unused resources for the service to use. To check existing quota availability, log-in to Horizon as the **admin** user and open the **Overview** panel under the **Compute** tab.

For Community Edition, the Database service requires that the Admin project have the following quota available:

<table>
  <thead>
    <tr><th>Resource</th>
  <th align="right">Usage</th>
</tr>
  </thead>
  <tbody>
    <tr><td>Floating IPs</td>
  <td align="right">6</td>
</tr>
    <tr><td>Instances</td>
  <td align="right">6</td>
</tr>
    <tr><td>Networks</td>
  <td align="right">2</td>
</tr>
    <tr><td>RAM (GB)</td>
  <td align="right">24</td>
</tr>
    <tr><td>Routers</td>
  <td align="right">2</td>
</tr>
    <tr><td>Security Groups</td>
  <td align="right">6</td>
</tr>
    <tr><td>Volumes</td>
  <td align="right">4</td>
</tr>
    <tr><td>Volume Storage (GB)</td>
  <td align="right">160</td>
</tr>
  </tbody>
</table>
	
In addition to the quotas mentioned above, for every database instance that is created by a user, the necessary resources to create that instance will be deducted from the admin project quota. The users Database service quota will also be affected.

### Connect to the Download Service {#database-connect}

1. Open Horizon and login as the *Admin* user. Then click on the **Admin** panel in Horizon and select the **Development Platform** panel under Admin. Then click the **Configure Services** sub-panel.

2. Click the **Connect** button on the **Configure Services** panel and enter your username and password for the HP Cloud OS Content Delivery Network. 

	If you do not have an account, click **Sign-up**.

### Download and Configure the Database Service {#database-connect}

In the **Configure Services** panel locate the **Database Service** item in the **Configure Services** table and select **Download Service** and wait for the download to complete.

#### Configuring the Database Service {#database-configure}

1. Once the download is complete, click the **Configure Service** button to begin configuration of the service. In the configuration dialog, specify the following configuration options:

	**Key Pair (Required)** - Enter the name of the key pair to install on all instances created as part of the Database service. The public key can be used by an admin to get SSH access to all instances.

	**External Network (Required)** - Enter the name of the network of the network that has external network access. For HP Helion OpenStack Community edition this network is named 'ext-net'

	**NTP Server IP** - Enter the IP Address to an NTP server to use if instances will not have outbound access to the internet. 

	**Service User Password (Required)** - Enter the password for the Admin user that is currently logged in. This password **MUST** match the password used to login to Horizon.

	**Icinga User Password (Required)** - Icinga is not available in HP Helion Development Platform Community Edition. However, a value must be specified. Enter any value.

	**Volume Type (Required)** - Enter the volume type to use when creating database instances.

	**Service Network (Required)** - Select the 'SVC' network created in [Configure the Service Network](#databse-service).
	
	**RabbitMQ IP Address (Required)** - Enter '127.0.0.1' for this parameter.

2. After all configuration options have been provided, select the **Configure** button to complete the configuration step. Wait for the configuration step to complete and the status to change to **Configured**.

3. Attach a Floating IP to API Service

	a. Open Horizon and login as the *Admin* user. Then click on **Compute**.

	b. Click **Instances**.

	c. Click **More/Associate Floating IP** for the `trove-trove0_api...` Instance.

	d. Select an available IP or allocate a new one from the `ext-net` Network.

	e. Select the port for `trove-trove0_api...` on the `trove_mgmt_network`

	f. Click **Associate**
	
4. Recreate the service endpoint for Database service. This step should be performed from the command line on the controller management node or the base node.  You will need the admin credentials and network connectivity to the overcloud.
	
	Delete the old service endpoint and create a new service endpoint with a floating IP address from above using the following command:

		floating_ip=replace_with_floating_ip_allocated_above; service_id=`keystone service-get database | grep id | awk '{print $4}'`; endpoint_id=`keystone endpoint-list | grep $service_id | awk '{print $2}'`;keystone endpoint-delete $endpoint_id; keystone endpoint-create --service-id $service_id --region regionOne --publicurl "http://$floating_ip:8779/v1.0/\$(tenant_id)s" --adminurl "http://$floating_ip:8779/v1.0/\$(tenant_id)s" --internalurl "http://$floating_ip:8779/v1.0/\$(tenant_id)s"

6. Log out from the Horizon dashboard. 

7. Log back into the Horizon dashboard as a non-admin user and click on the **Database** panel under the current Project to being using Database Service.

## Install the Marketplace Service {#marketplace-install}

This section provides details on installing the HP Helion Development Platform Marketplace service.

* [Prerequisites](#marketplace-install)
* [Connect to the Download Service](#marketplace-download-c)
* [Configuring the Marketplace Service](#marketplace-config)

### Prerequisites {#marketplace-install}

Before installing, make sure the following prerequisites are met:

#### Check Project Quotas {#database-quota}

The Marketplace service will be installed into the Admin project of the Helion OpenStack overcloud. The Admin project must have sufficient quota available and unused for the resources the service uses. 

To check existing quota availability: 

1. Log in to Horizon as the **admin** user. 

2. Open the **Overview** panel under the **Compute** tab.

	The quotas should meet or exceed the following:
	<table>
  <thead>
    <tr><th>Resource</th>
  <th align="right">Usage</th>
</tr>
  </thead>
  <tbody>
    <tr><td>Floating IPs</td>
  <td align="right">16</td>
</tr>
    <tr><td>Instances</td>
  <td align="right">4</td>
</tr>
    <tr><td>Networks</td>
  <td align="right">1</td>
</tr>
    <tr><td>RAM (GB)</td>
  <td align="right">8</td>
</tr>
    <tr><td>Routers</td>
  <td align="right">2</td>
</tr>
    <tr><td>Security Groups</td>
  <td align="right">4</td>
</tr>
  </tbody>
</table>

### Connect to the Download Service {#marketplace-download-c}

1. Open Horizon and login as the "admin" user. Then click on the admin panel in Horizon and select the **Development Platform** Panel under **Admin**. Then click on the **Configure Services** sub-panel.

2. Click the **Connect** button on the **Configure Services** panel and enter your username and password for the HP Cloud OS Content Delivery Network. Select the Sign-up button if you do not have an account.

### Download and Configure the Marketplace Service {#marketplace-download}

In the **Configure Services** panel locate the Marketplace item in the Configure Services table and select **Download Service** and wait for the download to complete.

#### Configuring the Marketplace Service {#marketplace-config}

1. Once the download is complete, click the **Configure Service** button to begin configuration of the service. In the configuration dialog, specify the following configuration options:

	**Key Pair (Required)** - Enter the name of the key pair to install on all instances created as part of the marketplace service. The public key can be used by an admin to get SSH access to all instances.

	**External Network (Required)** - Enter the name of the network of the network that has external network access. For HP Helion OpenStack Community Edition this network is named 'ext-net'.

	**NTP Server IP** - Enter the IP Address to an NTP server to use if instances will not have outbound access to the internet. 

	**Service User Password (Required)** - Enter the password for the Admin user that is currently logged in. This password **MUST** match the password used to login to Horizon.

	**Subnet Range** - Enter the subnet to use for Marketplace.
	
## Troubleshooting {#troubleshooting}

Refer to the following topics if you experience problems with the installation.


### Service is stuck in download {#troubleshooting-service}

There are situations in which a download will not complete.  One cause which is documented, is because the `tmp` directory ran out of space. There is a prerequisite to mount the `tmp` directory to a larger partition.  If you have completed this and it is still failing to download then we will need to reset the download. In the current release, this requires a manual process.

As the *admin* user, in the Admin project, click on **Project**, then **Object Store**. Open the `sherpa-cache` folder and delete the `wscatalog.<id>` folder which contains the cached download. The service should now be available to download again.



<a href="#top" style="padding:14px 0px 14px 0px; text-decoration: none;"> Return to Top &#8593; </a>


----
####OpenStack trademark attribution
*The OpenStack Word Mark and OpenStack Logo are either registered trademarks/service marks or trademarks/service marks of the OpenStack Foundation, in the United States and other countries and are used with the OpenStack Foundation's permission. We are not affiliated with, endorsed or sponsored by the OpenStack Foundation, or the OpenStack community.*