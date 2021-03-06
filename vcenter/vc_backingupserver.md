---

copyright:

  years:  2016, 2017

lastupdated: "2017-06-30"

---

# Backing up management components for vCenter Server instances

The VMware vCenter Server instance automatically backs up the management components daily. You can also back up components manually as you 
need.

Only the management server configurations are backed up. The configurations on the ESXi servers are not backed up.  You can
back up a maximum of 8 management VMs.

You can perform a manual backup before you change the configuration of your VMware virtual environment. An instance can have a maximum of 
14 backups. When the number of backups reaches the limit, the oldest backup is removed to make space for the new backup.

## Procedure

1. Click **Deployed Instances** from the left navigation pane. Click the **vCenter Server** tab.
2. Click the instance to back up.
3. Click the **Backup and Restore** tab.
4. Click **Back up now** to create a new backup.

## Results

A record appears in the restore points list. To retrieve the most recent status for a backup, click the refresh icon, which is in the upper 
right of the **Restore Points** section. See the following list for the details of the backup statuses:

* **In progress**: The backup job is initiated but not finished yet. You cannot start another backup when this
backup is in progress.
* **Available**: The backup job is completed and ready for use. When a backup is available, you can select this
backup to restore the management components to this backup image.
* **Failed**: The backup job failed. The console reports an error notification after a backup failure. Review
the error notification and fix the reported issue before you attempt to back up again.

## Related links

* [Restoring management components for vCenter Server instances](vc_restoringserver.html)
