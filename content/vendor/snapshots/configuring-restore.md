---
date: 2019-01-23
linktitle: "Configuring Restore"
title: Configuring Restore
isBeta: true
weight: 4
---

When restoring a Snapshot, the Admin Console will first "undeploy" the correct application. 
During this process, all existing application manifests will be removed from the cluster, and all PersistentVolumeClaims will be deleted. This is not reversible.

The restore process will then re-deploy all application manifests to the namespace, and all pods will have an extra `initContainer` and an extra directory named `.velero`. This is used for restore hooks.

For more information about the actual restore process, [refer to the Velero documentation](https://velero.io/docs/v1.2.0/restic/#how-backup-and-restore-work-with-restic).
