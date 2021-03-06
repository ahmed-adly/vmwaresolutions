---

copyright:

  years:  2016, 2017

lastupdated: "2017-05-25"

---

# Multi-site configuration for Cloud Foundation instances

{{site.data.keyword.vmwaresolutions_full}} allows instances to be deployed across different locations and have them up and running in a short time. Review the topology and components of the Cloud Foundation deployment for multi-site configuration.

## Multi-site deployment components

A multi-site deployment consists of the following components.

* **Primary instance**: The primary VMware Cloud Foundation instance has the following configuration:
  *  AD (Active Directory) and DNS (Domain Name System) root domain
  *  Cloud Foundation subdomain
  *  SSO (Single Sign-On) domain
  *  SSO site name
* **Secondary instance or instances**: One or more secondary Cloud Foundation instances, linked to the primary instance, with the following configuration:
   *  SSO site name
   *  DNS subdomain that is linked to the root domain on the primary instance
   *  DNS and AD replication set-up between the AD virtual machines on the primary and secondary instances.
   *  PSC (Platform Services Controller) deployed and configured to replicate with the PSC on the primary instance.
   *  VMware vCenter on the secondary instances are set up with Enhanced Link Mode to the vCenter on the primary instance.
   *  The NSX Managers on the secondary instances are set up as secondary NSX Managers linked to the NSX Manager on the primary instance.

## Cloud Foundation multi-site deployment

The multi-site configuration feature uses a hub and spoke topology with a primary site and a maximum of seven secondary sites. A single layer of sites is supported, that is, you cannot have subsequent sites that are linked to other secondary sites. As with single (stand-alone) Cloud Foundation instances, you can have a total of 31 ESXi servers in a multi-site configuration across all instances.

**Note**: If your configuration requires a multi-site deployment with more than 31 nodes, contact IBM Support for assistance. For more information, see [Contacting IBM Support](../vmonic/trbl_support.html).

The following graphic depicts the overall view of the Cloud Foundation multi-site deployment.

Figure 1. Cloud Foundation multi-site deployment

![Cloud Foundation multi-site deployment](multisite-hub-spoke.png)

The model contains the following layers:

* **Primary instance**: In a multi-site configuration, to deploy the first instance, you define that instance as primary during the instance order process.
* **Secondary instances**: In a multi-site configuration, you define the instances that are attached to the primary instance as secondary instances during the order process.

You can assign only one secondary instance to a primary instance at a time. You cannot assign multiple secondary instances to a primary instance at the same time. To do that, you must go through the order process again and select the previously defined primary instance as a primary instance for the secondary instance. You must repeat the process for all secondary instances that you want to create.

You can have a maximum of 8 (1 primary and 7 secondary) instances that are deployed in a multi-site configuration.

**Note**: Deleting Cloud Foundation instances that are part of a multi-site configuration requires special planning. For more information, see [Deleting Cloud Foundation instances in a multi-site configuration](sd_deletinginstance_multi.html).

## Related links

* [Assign Primary Role to NSX Manager](https://pubs.vmware.com/NSX-62/topic/com.vmware.nsx-cross-vcenter-install.doc/GUID-44E8AE16-BA3F-4DD9-B582-FC1E137E6CFC.html){:new_window}
* [Configuring Secondary NSX Managers](https://pubs.vmware.com/NSX-62/topic/com.vmware.nsx-cross-vcenter-install.doc/GUID-9E48BC57-15E3-49C7-8BC5-F94ED8918BBE.html){:new_window}
* [AD trusts supported with vCenter Single Sign-On](https://kb.vmware.com/kb/2064250){:new_window}
