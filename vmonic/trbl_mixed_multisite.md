---

copyright:

  years:  2016, 2017

lastupdated: "2017-06-29"

---

# A V1.7 secondary instance cannot be added to a V1.5 primary instance

## Problem
In a multi-site Cloud Foundation configuration, you cannot add a V1.7 secondary instance to a V1.5 primary instance because of a discrepancy between the operating system versions on the Windows AD (Active Directory) server. 

## Resolution
Complete the following steps on the V1.5 primary instance to add the permissions for the primary automation user to be part of the **Enterprise Admins** and **Schema Admins** groups.

1. Log in to the Windows AD server with the **Administrator** password.
2. Open **Server Manager** and click **Tools -> Active Directory Users and Computers**. 
4. On the **Active Directory Users and Computers** window, click the **Users** section under your root domain. 
5. Right-click the Automation user to open the **Properties** window. 
6. Click the **Member Of** tab. 
7. Click **Add** and enter the **Enterprise Admins** and **Schema Admins** groups as object names to the list.  

After completing these steps, you can add a V1.7 secondary instance to a V1.5 primary instance. 
