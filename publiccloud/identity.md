---
layout: public-cloud
title: "HP Helion Public Cloud Identity Service Overview"
permalink: /publiccloud/identity/
product: public-cloud 

---
<!--PUBLISHED-->
# HP Helion Public Cloud Identity Service Overview

<!--This is a comment. Comments are not displayed in the browser-->

<img src="media/identity_service_overview_0.png" width="580" height="436" alt="" />

Based on [Keystone, the OpenStack Identity Service](http://keystone.openstack.org/), the HP Helion Public Cloud Identity Service provides one-stop authentication for all HP Helion Public Cloud offerings.  Key terms include:

[**User**](/publiccloud/glossary#User)
:  A digital representation of a person, system, or service who uses HP Helion Public Cloud. The Identity Service validates that incoming requests are being made by the user who claims to be making the call. Users have a login and may be assigned tokens to access resources. Users can scope their authentication to a tenant which then limits where and how their tokens can be used to interact with services. Users are associated with tenants based on roles assigned to them with that tenant.

[**Credentials**](/publiccloud/glossary#Credentials)
: Data that belongs to, is owned by, and generally only known by a user that the user can present to prove they are who they are (since nobody else should know that data).

[**Authentication**](/publiccloud/glossary#Authentication)
: In the context of the Identity Service, the act of confirming the identity of a user or the truth of a claim. The Identity Service will confirm that incoming request are being made by the user who claims to be making the call by validating a set of claims that the user is making. These claims are initially in the form of a set of credentials (username & password, or user access keys). After initial confirmation, the Identity Service will issue the user a token which the user can then provide to demonstrate that their identity has been authenticated when making subsequent requests.

[**Token**](/publiccloud/glossary#Token)
: An arbitrary bit of text that is used to access resources. Each token has a scope which describes which resources are accessible with it.  While the Identity Service supports token-based authentication in this release, the intention is for it to support additional protocols in the future.

[**Tenant**](/publiccloud/glossary#Tenant)
: A collection of HP service subscriptions and/or resources (Compute, Object Storage, etc).

[**Endpoint**](/publiccloud/glossary#Endpoint)
: A network-accessible address, usually described by URL, where a service may be accessed.

[**Role**](/publiccloud/glossary#Role)
: A personality that a user assumes when performing a specific set of operations. A role includes a set of rights and privileges. A user assuming that role inherits those rights and privileges.  A token that is issued to a user includes the list of roles that user can assume. Services that are being called by that user determine how they interpret the set of roles a user has and which operations or resources each roles grants access to.

To jump right in and start using the service yourself, go to the [HP Helion Public Cloud Console](https://horizon.hpcloud.com/).  If you have any questions, try our [Forums](https://community.hpcloud.com) where you can learn from our own internal experts as well as other users in the HP Helion Public Cloud community.

<!-- To help you get started with the service, we've got some introductory getting started material at our [Introduction to the HP Helion Public Cloud Identity Service page](https://community.hpcloud.com/article/identity-service-introduction), and we've also provided you with a use case for [Migrating to the HP Helion Public Cloud Identity Service](https://community.hpcloud.com/article/identity-service-change-guide).  And of course, if you want to jump right and start using the service yourself, you should go to the [Manage Console](https://console.hpcloud.com).  If you have any questions, try our [Forums](https://community.hpcloud.com) where you can learn from our own internal experts as well as other users in the HP Helion Public Cloud community.-->

## API
Do you need low level, raw REST API access to HP Identity Services?  Take a look at our Compute API page for the version of HP Helion Public Cloud you are using: 

* [**Identity Service v2 API page**](/publiccloud/api/v2identity/)
* [**Identity Service v3 API page**](/publiccloud/api/identity/)

## Bindings
If you are looking for an easier to use, language-specific way of using HP Identity Services, check out our [Bindings section](/publiccloud/bindings).

## CLI
Want scriptable access you can put in a cron job or something similar?  Go on over to our [CLI documentation](/publiccloud/cli).
