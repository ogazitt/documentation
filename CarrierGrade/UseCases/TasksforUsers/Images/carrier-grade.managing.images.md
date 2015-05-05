---
layout: default
title: "HP Helion OpenStack&#174; Carrier Grade (Alpha): Managing Images"
permalink: /helion/commercial/carrier/dashboard/managing/images/
product: carrier-grade

---
<!--UNDER REVISION-->

<script>

function PageRefresh {
onLoad="window.refresh"
}

PageRefresh();

</script>

<!-- <p style="font-size: small;"> <a href="/helion/commercial/carrier/ga1/install/">&#9664; PREV</a> | <a href="/helion/commercial/carrier/ga1/install-overview/">&#9650; UP</a> | <a href="/helion/commercial/carrier/ga1/">NEXT &#9654;</a></p> -->

# HP Helion OpenStack&#174; Carrier Grade (Alpha): Managing Images

A virtual machine image is a single file that contains a virtual disk with a bootable operating system installed on it. You can use images to create virtual machine instances within the cloud. 

To create an image, you upload an ISO image file. After you upload an image, it is considered golden and you cannot change it.

You can use the dashboards to create and configure private virtual machine images, which can be used to create instances.

**Note:** You can also [create an image based on an instance](/helion/commercial/carrier/dashboard/managing/images/public/), which is called a *snapshot*.

How you interact with these images depends upon your user type, either an administrative user (admin) or a non-administrative user (user). 

To work with images [launch the HP Helion OpenStack Helion Dashboard](/helion/openstack/carrier/dashboard/login/).

* For non-admin users, click **Project** > **Compute** > **Images**. The volumes in the current project are listed.
* For admin users, click **Admin** > **Images**. The volumes in the current domain are listed.

The **Images** panel looks similar to the following. Click the image to view in a new window: 

<img src="media/CGH-Helion-Images.png"/>

<a href="javascript:window.open('/content/documentation/media/media/CGH-Helion-Images.png','_blank','toolbar=no,menubar=no,resizable=yes,scrollbars=yes')">Click here to view a larger image in a new window.</a>

For details on an image, click the image name. 


## Managing images as a user ##

As a user, you can work with any *private* images associated with the active project.

Access the image commands using the Compute panel on the Project dashboard. 

Click **Images** to perform the following tasks:

* [Create an image](/helion/commercial/carrier/dashboard/managing/images/create/)
* [Modify an image](/helion/commercial/carrier/dashboard/managing/images/modify/)
* [Delete an image](/helion/commercial/carrier/dashboard/managing/images/delete/)
* [View image details](/helion/commercial/carrier/dashboard/managing/images/details/)
* [Protect an image or snapshot from being edited](/helion/commercial/carrier/dashboard/managing/images/protect/)

**Note:** The admin can perform all of the user tasks in addition to the admin tasks.



## Managing images as an admin ##

As an admin user, you can work on all of the images in your domain, regardless of which project the image is associated with. 

Access the admin image commands using the System Panel  on the Admin dashboard.

As an admin, you can determine if the snapshot is available only in the current project or to all projects in the domain.

* [Make an image or snapshot public](/helion/commercial/carrier/dashboard/managing/images/public/)

<a href="#top" style="padding:14px 0px 14px 0px; text-decoration: none;"> Return to Top &#8593; </a>


----