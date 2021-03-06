---

copyright:

  years:  2016, 2017

lastupdated: "2017-03-30"

---

# Release notes for V1.5 (Mar 20, 2017)

This release includes new features, usability enhancements, and bug fixes. For a list of fixed issues in different releases, known issues with the product, and additional tips to use {{site.data.keyword.vmwaresolutions_full}}, see [{{site.data.keyword.vmwaresolutions_full}} dW Answers](https://developer.ibm.com/answers/topics/cloudvmw/){:new_window}.

## VRF versus classic SoftLayer account requirements (Updated Mar 30, 2017)

For classic SoftLayer® accounts, VLAN spanning is a setting that can be enabled at the account level. {{site.data.keyword.vmwaresolutions_short}} requires that VLAN spanning is enabled.

For VRF (Virtual Routing and Forwarding) SoftLayer accounts, the equivalent of VLAN spanning is a permanent setting that cannot be changed. No user configuration is required for VRF accounts.

Before you place an instance order, ensure that your SoftLayer account is either a VRF account or a classic (non-VRF) account with VLAN spanning enabled. Otherwise, the order might fail.

To confirm if your SoftLayer account is a VRF account, verify with IBM Bluemix Support. For classic accounts, you must enable VLAN spanning by following the instructions from [Enable or Disable VLAN Spanning](https://knowledgelayer.softlayer.com/procedure/enable-or-disable-vlan-spanning){:new_window}.

## Service charge model updates

For Cloud Foundation instances, a new _SDDC Manager_ license is introduced, which is a monthly fee that is applied to each node. For more information, see _Cloud Foundation components_ in [Cloud Foundation overview](../sddc/sd_cloudfoundationoverview.html).

## Usability enhancements

Improvements are made throughout the user interface:

* The availability of various data centers and whether they have sufficient inventory to fulfill the order is clearly indicated on the user interface so you can make an informed decision about the data center to select during instance ordering. For more information, see [Requirements and planning for Cloud Foundation instances](../sddc/sd_planning.html) and [Requirements and planning for vCenter Server instances](../vcenter/vc_planning.html).
* For Cloud Foundation instances, information such as the instance name, domain and subdomain name, and data center location, is automatically displayed in graphical format while you are entering the required information in the input fields. For more information, see [Ordering Cloud Foundation instances](../sddc/sd_orderinginstance.html).
