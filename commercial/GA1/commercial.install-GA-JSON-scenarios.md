---
layout: default
title: "HP Helion OpenStack: Editing the JSON Environment Variables File for Installation"
permalink: /helion/openstack/install/envars/deploy/
product: commercial.ga
product-version1: HP Helion OpenStack 1.1
role1: Storage Administrator
role2: Storage Architect
authors: Michael B, 


---
<!--UNDER REVISION-->


<script>

function PageRefresh {
onLoad="window.refresh"
}

PageRefresh();

</script>


<p style="font-size: small;"> <a href="/helion/openstack/install/envars/"> &#9650; Editing the JSON Environment Variables File for Installation</a> </p> 

# HP Helion OpenStack&reg;: JSON Environment File Deployment Scenarios

Edit the [JSON file](/helion/openstack/install/envars/) based on the applicable scenario:

- [Environment variables file for a KVM install](#kvm)
- [Environment variables file for a ESX install](#esx)

## Environment variables file for a KVM install ## {#kvm}

Identify the environment variables required for the installation based on the deployment scenario.

If you plan to use custom IP addresses in your HP Helion OpenStack deployment, open the JSON file in the installation package named `kvm-custom-ips.json` and edit the following environment variables. Save the file on the seed cloud host (installation system). The variables are defined in [Definition of Environment variables used during install](#env).

All VLAN ID's & IP addresses given in the following procedure are examples of customized IP addresses and VLAN identifiers for external network access.

1. Log into your install system as root.

		sudo su -

2. Locate the `kvm-custom-ips.json` in the `/tripleo/config` directory. This directory is created when the installation package is extracted.

3. Optionally, make a backup copy of the JSON file in case it is needed.

		cp kvm-custom-ips.json kvm-custom-ips.json-backup

4. Open the `kvm-custom-ips.json` file and edit the environment variable listed below.  

		{
		    "cloud_type": "KVM",
		    "compute_scale": 12,
		    "vsa_scale": 3,
		    "so_swift_storage_scale": 4,
		    "so_swift_proxy_scale": 4,
		    "control_virtual_router_id": "202",
		    "virtual_interface": "eth1",
		    "fixed_range_cidr": "172.0.100.0/24",
		    "floating_ip": {
		        "start": "127.0.0.1",
		        "end": "127.0.0.255",
		        "cidr": "127.0.0.0/24"
		    },
		    "baremetal": {
		        "network_seed_ip": "1.2.3.4",
		        "network_cidr": "1.2.3.4/12",
		        "network_seed_range_start": "127.0.0.1",
		        "network_seed_range_end": "127.0.0.10",
		        "network_undercloud_range_start": "127.0.0.11",
		        "network_undercloud_range_end": "127.0.0.20"
		    },
		    "vsa": {
		        "DEFAULT": {
		            "enabled_backends": ["vsacluster_001"]
		        },
		        "vsacluster_001": {
		            "volume_driver": "cinder.volume.drivers.san.hp.hp_lefthand_iscsi.HPLeftHandISCSIDriver",
		            "volume_backend_name": "vsacluster_001",
		            "hplefthand_api_url": "https://10.10.0.141:8081/lhos",
		            "hplefthand_username": "meg",
		            "hplefthand_password": "2late2store",
		            "hplefthand_clustername": "admin_01",
		            "hplefthand_iscsi_chap_enabled": true,
		            "hplefthand_debug": true
		        }
		    },
		    "3par": {
		        "DEFAULT": {
		            "enabled_backends": ["3parcluster_001"]
		        },
		        "3parcluster_001": {
		            "CPG_ae282f7-a33e-4646-b970-c9f90329178bb": {
		                "volume_backend_name": "3par_fc",
		                "hp3par_api_url": "https://15.214.241.21:8080/api/v1",
		                "hp3par_username": "3paradm",
		                "hp3par_password": "3pardata",
		                "hp3par_cpg": "overcloud-fc-cpg-1",
		                "san_ip": "15.214.241.21",
		                "san_login": "3paradm",
		                "san_password": "3pardata",
		                "volume_driver": "cinder.volume.drivers.san.hp.hp_3par_fc.HP3PARFCDriver",
		                "hp3par_debug": false
		            }
		        },
		    },
		    "dns": {
		        "overcloud_server": "15.182.24.123:123", 
		        "undercloud_server": "15.192.24.231:123",
		        "seed_server": "15.192.24.231:123"
		    },
		    "ntp": {
		        "overcloud_server": "15.182.24.123:123", 
		        "undercloud_server": "15.192.24.231:123",
		        "seed_server": "15.192.24.231:123"
		    }, 
		    "ldap": { 
		        "directory_name": "ldap_name", 
		        "directory_server_ip": "172.16.112.182", 
		        "directory_server_port": 636, 
		        "ssl_on": true, 
		        "certificate_file": "/home/helion/identity/ldap/certs/cust_ldap_cert.pem", 
		        "user": "CN=Administrator, CN=Users, DC=vlan43, DC=domain", 
		        "password": "mydirectoryourcommand", 
		        "suffix": "DC=vlan43, DC=domain", 
		        "user_tree_dn": "CN=Users, DC=vlan43, DC=domain", 
		        "user_objectclass": "user", 
		        "group_objectclass": "group", 
		        "user_id_attribute": "cn", 
		        "user_name_attribute": "cn", 
		        "group_tree_dn": "CN=Users, DC=vlan43, DC=domain", 
		        "group_id_attribute": "cn", 
		        "group_name_attribute" : "cn", 
		        "group_dn": "USER_CN", 
		        "group_search_context": "", 
		        "ldap_user_filter": "" 
		    }, 
		    "neutron": { 
		        "overcloud_public_interface": "eth2", 
		        "undercloud_public_interface": "eth2", 
		        "vsa_public_interface": "eth2", 
		        "public_interface_default_route": "192.168.200.1", 
		        "network_type": "vlan",
		        "public_interface_raw_device": "eth1",
		        "network_vlan_ranges": "physnet1:br-ex",
		        "overcloud_dvr": false
		    }, 
		    "svc": { 
		        "interface": "vlan4083", 
		        "interface_default_route": "172.24.48.1", 
		        "allocate_start": "172.24.63.0", 
		        "allocate_end": "172.24.63.254", 
		        "allocate_cidr": "172.24.28.0/20",
		        "overcloud_bridge_mappings": "svcnet1:br-svc",
		        "overcloud_flat_networks": "svcnet1",
		        "customer_router_ip": "192.0.2.15"
		    }, 
		    "hypervisor": { 
		        "public_interface": "eth1", 
		        "physical_bridge": "br-ex" 
		    }, 
		    "bridge_mappings": "physnet:br-ex", 
		    "vcenter": { 
		        "vlan_range": "1:4094", 
		        "provider_network": "<insert provider network here>" 
		    }, 
		    "ssl": { 
		        "ca_certs": "<string-encoded certificate data>", 
		        "cluster_backend": { 
		            "key": "<string-encoded certificate data>", 
		            "certificate": "<string-encoded certificate data>" 
		        }, 
		        "public_vip": { 
		            "key": "<string-encoded certificate data>", 
		            "certificate": "<string-encoded certificate data>" 
		        } 
		    },
		    "codn": {
		        "undercloud_http_proxy": "http://16.85.175.150:8080",
		        "undercloud_https_proxy": "http://16.85.175.150:8080",
		        "overcloud_http_proxy": "http://16.85.175.150:8080",
		        "overcloud_https_proxy": "http://16.85.175.150:8080"
		    }
		}

5. Save the file on the seed cloud host.

6. [Return to HP Helion OpenStack&reg;: Installation Prerequisites](/helion/openstack/install/prereqs/#csv).

## Environment variables file for an ESX cloud type ## {#esx}

Identify the environment variables required for the installation based on the deployment scenario.

- [Deployment Scenario 1: HP Helion OpenStack Deployment with custom IP addresses](#esxone)
- [Deployment Scenario 2: HP Helion OpenStack Deployment with custom IP addresses and a VLAN provider Network for external access](#esxtwo)


### Deployment Scenario 1: HP Helion OpenStack Deployment with custom IP addresses ### {#esxone}

If you plan to use custom IP addresses in your HP Helion OpenStack deployment, open the JSON file in the installation package named `esx-custom-ips.json` and edit the following environment variables. Save the file on the seed cloud host (installation system). The variables are defined in [Definition of Environment variables used during install](#env).

All VLAN ID's & IP addresses given in the following procedure are examples of customized IP addresses and VLAN identifiers for external network access.

1. Log into your install system as root.

		sudo su -

2. Locate the `esx-custom-ips.json` in the `/tripleo/config` directory. This directory is created when the installation package is extracted.

3. Optionally, make a backup copy of the JSON file in case it is needed.

	cp kvm-custom-ips.json kvm-custom-ips.json-backup

4. Open the `esx-custom-ips.json` file and edit the environment variable listed below.  

		{
			"cloud_type": "ESX",
			"baremetal": {
				"network_seed_range_start": "172.30.100.2",
				"network_seed_range_end": "172.30.100.20",
				"network_undercloud_range_start": "172.30.100.21",
				"network_undercloud_range_end": "72.30.100.40"
			},
			"neutron": {
				"overcloud_public_interface": "eth0",
				"undercloud_public_interface": "eth0"
			},
			"ntp": {
				"overcloud_server": "19.111.135.123",
				"undercloud_server": "19.111.135.123"
			},
			"floating_ip": {
				"start": "172.30.100.41",
				"end": "172.30.100.200",
				"cidr": "172.30.100.0/24"
			},
			"vcenter": {
				"provider_network": "192.168.10.0/24",
				"vlan_range": "500:1000",
				"customer_router_ip": "172.30.100.1"
			},
			"virtual_interface": "br-ex",
			"customer_router_ip": "10.23.69.129"
		}

5. Save the file on the seed cloud host.

6. [Return to HP Helion OpenStack&reg;: Installation Prerequisites](/helion/openstack/install/prereqs/#csv).

### Deployment Scenario 2: HP Helion OpenStack Deployment with custom IP addresses and a VLAN provider Network for external access ### {#esxtwo}

If you intend to use custom IP addresses and a VLAN provider network for external access in your HP Helion OpenStack deployment, open the JSON file in the installation package named `esx-custom-ips.json` and edit the following environment variables. Save the file on the seed cloud host (installation system). The variables are defined in [Definition of Environment variables used during install](#env).

All VLAN ID's & IP addresses given in the following procedure are examples of customized IP addresses and VLAN identifiers for external network access.

1. Log into your install system as root.

		sudo su -

2. Locate the `esx-custom-ips-vlan.json` in the `/tripleo/config` directory. This directory is created when the installation package is extracted.

3. Optionally, make a backup copy of the JSON file in case it is needed.

	cp kvm-custom-ips.json kvm-custom-ips.json-backup

4. Open the `esx-custom-ips.json` file and edit the environment variable listed below.  

		{
			"cloud_type": "ESX",
			"baremetal": {
				"network_cidr": "172.30.100.0/24",
				"network_seed_ip": "172.30.100.1",
				"network_seed_range_start": "10.23.69.136",
				"network_seed_range_end": "10.23.69.141",
				"network_undercloud_range_start": "10.23.69.142",
				"network_undercloud_range_end": "10.23.69.150"
			},
			"neutron": {
				"overcloud_public_interface": "eth2",
				"undercloud_public_interface": "eth2",
				"public_interface_default_route": "15.126.52.1",
				"public_interface_raw_device": "eth2"
			},
			"ntp": {
				"overcloud_server": "10.23.69.129",
				"undercloud_server": "10.23.69.129"
			},
			"floating_ip": {
				"start": "15.126.54.20",
				"end": "15.126.54.40",
				"cidr": "15.126.52.0/22"
			},
			"vcenter": {
				"provider_network": "10.23.70.128/26",
				"vlan_range": "1701:1720",
				"customer_router_ip": "10.23.69.129",
				"external_vlan_id": 1634,
				"external_network_gateway": "15.126.52.1"
			},
			"virtual_interface": "br-ex",
			"bridge_interface": "em1",
			"customer_router_ip": "10.23.69.129"
		}

5. Save the file on the seed cloud host.

6. [Return to HP Helion OpenStack&reg;: Installation Prerequisites](/helion/openstack/install/prereqs/#csv).


----