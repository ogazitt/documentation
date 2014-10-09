---
layout: default
title: "HP Helion OpenStack&#174; Object Operations Service Overview"
permalink: /helion/openstack/ga/services/object/overview/scale-out-swift/
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
<p style="font-size: small;"> <a href="/helion/openstack/ga/services/object/overview/">&#9664; PREV</a> | <a href="/helion/openstack/services/overview/">&#9650; UP</a> | <a href="/helion/openstack/ga/services/swift/deployment-scale-out/"> NEXT &#9654</a> </p>
-->

# HP Helion OpenStack&reg;: About Scale-out Swift #

HP Helion OpenStack includes two starter Swift All-in-One servers that are deployed by the initial installation. The installer auto-configures a portion of the first device recognized by the operating system and assigns it to the Swift entities (account, container and object rings).

We recommend you use these Starter servers as Swift Proxy Servers for the scaled out Swift cluster. To do this, you can use the *ringos* utility to add additional drives on that server to the Swift Account and Container rings. For more details, see the [ringos](/helion/openstack/GA1/services/object/pyringos/) manual.

- [Step by step instructions for deploying additional Scale-out Swift Nodes with HP Helion OpenStack](/helion/openstack/ga/services/swift/deployment-scale-out/)

##Diagrams 

The HP Helion OpenStack scale-out Swift architecture.

<a href="javascript:window.open('/content/documentation/media/swift_deployment-architecture-different-object-without-overcloud-controller-nodes.png','_blank','toolbar=no,menubar=no,resizable=yes,scrollbars=yes')">HP Helion OpenStack Scale-out (opens in a new window)</a>

The HP Helion OpenStack life-cycle diagram.

<a href="javascript:window.open('/content/documentation/media/swift-cluster-lifecycle.png','_blank','toolbar=no,menubar=no,resizable=yes,scrollbars=yes')">Swift cluster lifecycle(opens in a new window) </a> 

##Storage Policies and Policy Zero

All containers must have a storage policy. If a policy is not explicitly specified, the default policy is applied.

For legacy containers created prior to the implementation of storage policies, you can use *Policy-0*.

- **Policy- 0.** Each policy has both a friendly, configurable ***name*** as well as an ***index*** or number. The policy with index number zero (0) maps to the Ring-0, which is present by default in all installations, is Policy-0. 

	**Note:** You can change the name of Policy-0, but do not change the index, as there must always be a Policy-0. 

- **Default policy.** The ***default*** policy can be any policy defined in the cluster. The default policy is automatically chosen when a container is created without a storage policy specified. 

In other words, default means *create the container using this policy if no policy was specified* and Policy-0 means *apply the legacy policy to an existing container that doesn’t have a specified policy*. Note that in the unique case where no other policies are defined, Policy-0 is also the default.







<a href="#top" style="padding:14px 0px 14px 0px; text-decoration: none;"> Return to Top &#8593; </a>

----
####OpenStack trademark attribution
*The OpenStack Word Mark and OpenStack Logo are either registered trademarks/service marks or trademarks/service marks of the OpenStack Foundation, in the United States and other countries and are used with the OpenStack Foundation's permission. We are not affiliated with, endorsed or sponsored by the OpenStack Foundation, or the OpenStack community.*