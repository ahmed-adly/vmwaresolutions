---

copyright:

  years:  2016, 2017

lastupdated: "2017-06-14"

---

# Impacts of changing components for vCenter Server instances

Changing resources or subnets that are reserved for {{site.data.keyword.vmwaresolutions_full}} can impact management operations.

## Changing vCenter Server resources and their impact on the system

The following table lists the operations that might be impacted if the SSO administrator changes VMware vCenter Server resources outside of the {{site.data.keyword.vmwaresolutions_short}} console. If a solution to recover is available, it is provided as well.

Table 1. Operations that are impacted by changing VMware resources

| Attempted change  | Impacted operations  | Severity  | Recovery method  |
|:------------- |:------------- |:--------------|:--------------|
| Change the VMware virtual datacenter name. | Adding a VMware datacenter might fail because the new ESXi server cannot join the changed datacenter. | Important | Change the VMware virtual datacenter name back to the original name. |
| Change any port group names.    | Adding an ESXi server might fail. | Important | Change the port group name back to the original name. | 
| Change the cluster name. | Adding an ESXi server might fail. | Important | Change the cluster name back to the original name.
| Change the public or private Distributed Virtual Switch (DVS) name. | Adding an ESXi server might fail. | Important | Change the public or private Distributed Virtual Switch (DVS) name to the original name.
| Change any Network File System (NFS) data store names. | Adding an ESXi server might fail. | Important | Remount the NFS data store as read-only on the ESXi server. The NFS data store name must match the one provisioned when the system started.

The following table lists the operations that might be impacted if the VC/PSC root user changes vCenter Server resources outside of the {{site.data.keyword.vmwaresolutions_short}} console.

Table 2. Operations that are impacted by for the VC/PSC root access (local)

| Attempted change  | Impacted operations  | Severity  | Recovery method  |
|:------------- |:------------- |:--------------|:--------------|
| Enable or disable shell access.    | Patching and updating for PSC and vCenter Server might fail.    | Important    | N/A    |

## Management subnets and their impact on the system

The following information discusses the subnets that are ordered by {{site.data.keyword.vmwaresolutions_short}} and it provides options for you to order extra subnets for your own use.

**CAUTION**: Do not use these components for other purposes, or the stability of your environment is severely compromised.

With each IBM Cloud bare metal server order, the following ranges of IP addresses are ordered by default:
*  A primary public range of 32 IP addresses
*  A primary private range of 64 IP addresses

In addition, the following management subnets are also reserved for {{site.data.keyword.vmwaresolutions_short}}:
*  Two portable private subnets of 64 IP addresses on the first VLAN: one for management and the other one for VTEPS
*  Two portable private subnets of 64 IP addresses on the second VLAN: one for VMotion and one for vSAN
*  A public portable subnet of 16 IP addresses on the public VLAN

If you need more subnets to use, you can obtain IP addresses to use in one of the following ways:
*  **Option 1 (recommended)**: Use VMware NSX virtual network overlays. A sample VXLAN template is provided upon order. This VXLAN can be used as a starting point for building SDN.
*  **Option 2**: Order your own portable public or private subnets to obtain IP addresses. To distinguish the subnets that you order from the management subnets, you can add notes to all the subnets that you are ordering.
