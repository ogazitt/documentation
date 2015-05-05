---
layout: default-devplatform
permalink: /helion/devplatform/als/admin/server/
product: devplatform2.0
title: "HP Helion 1.2 Development Platform: Server Configuration "
product-version1: HP Helion Development Platform
product-version2: HP Helion Development Platform 1.1
role1: Application Developer
role2: ISV Developer 
role3: Service Developer
role4: Network Administrator
role5: Systems Administrator 
role6: Security Engineer
authors: Jayme P

---
<!--UNDER REVISION-->

# HP Helion 1.2 Development Platform: Server Configuration {#server-configuration}
[See the Helion 1.0 Development Platform version of this page](/als/v1/admin/server/)

This page covers the initial setup and configuration of the Application Lifecycle Service
Server in a virtual machine under control of a hypervisor running on a
virtualization host.

##Accessing Server via the Command Line {#accessing-server-via-the-command-line}

The Application Lifecycle Service server initially has one user account. The default login information is:

* Username: stackato
* Password: helion

Unless you've already created a primary admin user in the Management Console. If so, the password of the default Helion account is changed to match that of the first user created in the Management Console, and you'll need to use that password instead. 

**Security Note**: If the Application Lifecycle Service server is running on a publicly routable network, the password should be changed as soon as possible.

**Note**

 If the cluster was created using the Horizon Management Console Panel or Application Lifecycle Service Installer CLI, you must log in with your SSH key you selected during cluster creation.

Command access to the Application Lifecycle Service server is available in several ways:

-   Over the hypervisor's [tty console](/helion/devplatform/als/user/reference/glossary/#term-tty-console).

-   The [Application Lifecycle Service Client](/helion/devplatform/als/user/reference/client-ref/#command-ref-client) command, which in addition to specialized functions can provide remote shell access to the server:

        helion target helion@helion-xxxx.local
        helion ssh api

-   The familiar `ssh` command:

        ssh helion@helion-xxxx.local

**Note**
<!-- For ssh access on Windows, we recommend [MSYS](http://sourceforge.net/apps/trac/mingw-w64/wiki/MSYS).-->

On the server, the control command for Application Lifecycle Service is called
`kato`. It is used for configuration and node
management procedures such as start, stop, role specialization, and
status checks. For a complete list of options, see the [Kato Command Reference](/helion/devplatform/als/admin/reference/kato-ref/).

Common Operations[](#common-operations "Permalink to this headline")
---------------------------------------------------------------------

Instructions for common operations on the Application Lifecycle Service VM can be found here:

-   [Common Server Operations](/helion/devplatform/als/admin/server/operations/)
    -   [Server Status](/helion/devplatform/als/admin/server/operations/#server-status)
        -   [Starting and Stopping
            Roles](/helion/devplatform/als/admin/server/operations/#starting-and-stopping-roles)
        -   [System Shutdown](/helion/devplatform/als/admin/server/operations/#system-shutdown)
    -   [Setting the Time Zone](/helion/devplatform/als/admin/server/operations/#setting-the-time-zone)
    -   [Resetting the VM](/helion/devplatform/als/admin/server/operations/#resetting-the-vm)
    -   [Monitoring The Application Lifecycle Service
        Server](/helion/devplatform/als/admin/server/operations/#monitoring-the-helion-server)
        -   [Management Console](/helion/devplatform/als/admin/server/operations/#management-console)
        -   [New Relic](/helion/devplatform/als/admin/server/operations/#new-relic)
        -   [Creating an Admin User](/helion/devplatform/als/admin/server/operations/#creating-an-admin-user)
        -   [System Monitoring with Nagios](/helion/devplatform/als/admin/server/operations/#system-monitoring-with-nagios)
    -   [Server Backup, Import, and Export](/helion/devplatform/als/admin/server/operations/#server-backup-import-and-export)
-   [Upgrading Application Lifecycle Service](/helion/devplatform/als/admin/server/upgrade/)
    -   [Before an upgrade](/helion/devplatform/als/admin/server/upgrade/#before-an-upgrade)
    -   [Executing the upgrade](/helion/devplatform/als/admin/server/upgrade/#executing-the-upgrade)

Detailed Configuration[](#detailed-configuration "Permalink to this headline")
-------------------------------------------------------------------------------

To continue configuring the Application Lifecycle Service server, see:

-   [Detailed Configuration](/helion/devplatform/als/admin/server/configuration/)
    -   [General](/helion/devplatform/als/admin/server/configuration/#general)
        -   [Changing the Password](/helion/devplatform/als/admin/server/configuration/#changing-the-password)
    -   [Network Setup](/helion/devplatform/als/admin/server/configuration/#network-setup)
        -   [Changing the
            Hostname](/helion/devplatform/als/admin/server/configuration/#changing-the-hostname)
        -   [Changing IP
            Addresses](/helion/devplatform/als/admin/server/configuration/#changing-ip-addresses)
        -   [Setting a Static
            IP](/helion/devplatform/als/admin/server/configuration/#setting-a-static-ip)
        -   [Modifying
            /etc/hosts](/helion/devplatform/als/admin/server/configuration/#modifying-etc-hosts)
        -   [DNS](/helion/devplatform/als/admin/server/configuration/#dns)
        -   [Dynamic DNS](/helion/devplatform/als/admin/server/configuration/#dynamic-dns)
        -   [Alternate DNS
            Techniques](/helion/devplatform/als/admin/server/configuration/#alternate-dns-techniques)
        -   [Adding DNS
            Nameservers](/helion/devplatform/als/admin/server/configuration/#adding-dns-nameservers)
        -   [TCP/UDP Port
            Configuration](/helion/devplatform/als/admin/server/configuration/#tcp-udp-port-configuration)
        -   [HTTP Proxy](/helion/devplatform/als/admin/server/configuration/#http-proxy)
        -   [Staging Cache & App HTTP
            Proxy](/helion/devplatform/als/admin/server/configuration/#staging-cache-app-http-proxy)
    -   [VM Filesystem Setup](/helion/devplatform/als/admin/server/configuration/#vm-filesystem-setup)
    -   [Application Lifecycle Service Data Services vs. High Availability
        Databases](/helion/devplatform/als/admin/server/configuration/#helion-data-services-vs-high-availability-databases)
    -   [HTTPS & SSL](/helion/devplatform/als/admin/server/configuration/#https-ssl)
        -   [Using your own SSL
            certificate](/helion/devplatform/als/admin/server/configuration/#using-your-own-ssl-certificate)
        -   [Adding Custom SSL Certs](/helion/devplatform/als/admin/server/configuration/#adding-custom-ssl-certs-sni)
        -   [CA Certificate
            Chaining](/helion/devplatform/als/admin/server/configuration/#ca-certificate-chaining)
        -   [Generating a self-signed SSL
            certificate](/helion/devplatform/als/admin/server/configuration/#generating-a-self-signed-ssl-certificate)
    -   [Quota Definitions](/helion/devplatform/als/admin/server/configuration/#quota-definitions)
        -   [sudo](/helion/devplatform/als/admin/server/configuration/#sudo)
        -   [Allowed
            Repositories](/helion/devplatform/als/admin/server/configuration/#allowed-repositories)