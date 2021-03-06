---

copyright:

  years:  2016, 2017

lastupdated: "2017-06-08"

---

# Deleting Cloud Foundation instances in a multi-site configuration

There are special considerations to be aware of before you plan to delete Cloud Foundation instances that are part of a multi-site configuration.

When you delete a Cloud Foundation instance, the following components are released sequentially:
1. Support and Services fee
2. VMware product licenses
3. ESXi servers
4. Subnets
5. VLANs

Because of resource dependencies, the components in your instance are not released immediately when you delete the instance. For example, the subnets and VLANs cannot be deleted until the ESXi servers are fully reclaimed by SoftLayer®, which happens at the end of the SoftLayer billing cycle. At the end of the SoftLayer billing cycle, which is typically 30 days, the subnets and VLANs are deleted and the instance deletion is completed.

**Attention**: You are billed until the end of the SoftLayer billing cycle for the deleted instance.

## Procedure

1. Ensure that you do not have any NSX objects expanded into the secondary instance that you want to delete.
2. Delete the secondary vCenter and PSC (Platform Services Controller) from the primary SSO (Single Sign-On) domain. For more information, see [Unregister vCenter Server from Single Sign-On](https://kb.vmware.com/selfservice/microsites/search.do?language=en_US&cmd=displayKC&externalId=2106736){:new_window}.
3. Demote the local domain controller VSI (Virtual Service Instance). For more information, see [Demoting domain controllers and domains](https://technet.microsoft.com/en-us/windows-server-docs/identity/ad-ds/deploy/demoting-domain-controllers-and-domains--level-200-){:new_window}.
4. Delete the secondary Cloud Foundation instance from the {{site.data.keyword.vmwaresolutions_full}} console.
5. Repeat from steps 1 to 4 for all secondary Cloud Foundation instances in your multi-site configuration.
6. After deleting all secondary instances, you can also delete the primary instance from the {{site.data.keyword.vmwaresolutions_short}} console.

## Related links 

* [Deleting Cloud Foundation instances](sd_deletinginstance.html)
