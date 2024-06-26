
---
oep-number: draft Auto Snapshot deletion 20190715
title: Jiva auto snapshot deletion
authors:
  - "@utkarshmani1997"
owners:
  - "@vishnuitta"
  - "@payes"
  - "@utkarshmani1997"
editor: "@utkarshmani1997"
creation-date: 2019-07-15
last-updated: 2019-09-03
status: provisional
see-also:
  - NA
replaces:
  - NA
superseded-by:
  - NA
---

 # Jiva automatic snapshot deletion

 ## Table of Contents

- [Jiva automatic snapshot deletion](#jiva-automatic-snapshot-deletion)
  - [Table of Contents](#table-of-contents)
  - [Summary](#summary)
  - [Motivation](#motivation)
    - [Goals](#goals)
  - [Proposal](#proposal)
    - [Implementation Details](#implementation-details)
  - [Performance impact](#performance-impact)
  - [Alternatives](#alternatives)

 ## Summary

 This proposal is aimed for the users who experience very frequent network glitch
 at there cluster, due to which replica get restarted and autogenerated snapshots
 files are created. A max of 512 snapshots can be created. Once 512 snapshots are
 created, the replica won't be able to connect again automatically and requires
 manual cleanup of snapshot.

 ## Motivation

 The motivation behind this approach is to remove/reduce the efforts of the user
 for managing the storage layer

 ### Goals

 - Ability to remove autogenerated snapshots automatically in background without
   any manual intervention from the user.

 ## Proposal

 Though there is a working flow of deletion of snapshot via REST Api/ jivactl cli
 but this requires manual intervention from user i.e, user needs to list the snap
 shots and delete it one by one via given approaches but if number of snapshots have
 been grown significantly it will take too much time to cleanup those snapshots.

 The proposed design is to have a background job in jiva controller that keeps
 autogenerated snapshots in check.

 ### Implementation Details

 Jiva controller will start a goroutine for the cleanup of snapshots.
 Cleanup goroutine will start the cleanup process as follows.

 * Cleanup goroutine will verify the rebuild, check if the replication factor is
   met and other prerequisites, and then snapshot deletion will be triggered in the
   background.

 * Verify that snapshot count is not reached at threshold, if the snapshot
   count is below the threshold, exit the cleanup job.

 ## Performance impact

 - Deletion of snapshot is time taking process since data needs to be merged to
   its siblings, so larger the data in snapshot, time taken for this will grow
   significantly and may impact the current IO's.

 - There are some cases where we may have stale snapshot entries if replica is
   restarted while snapshot deletion was in progress.

 ## Alternatives

 There are following approaches which can be used to implement this feature:

 a) **Manual deletion**:

 - Delete snapshots via cli tool jivactl
     - `jivactl snapshot ls` to list snapshots
     - `jivactl snapshot rm <snap_name>` from above output

    *cons*:
       - User needs to delete the snapshots one by one by specifying snapshot name
       - Requires manual cleanup of snapshots if replicas are restarted while
         snapshot deletion is in progress by validating the chain and restart is
         required to rebuild the replica to be on the safer side.

 b) **Cleanup in background by picking the snapshots with smallest size**:

 - Run a goroutine which will pick up snapshots based on its size and start
   cleaning up the snapshots which has size less then any given size (for
   exp < 2-5G).

 NOTE: This approach will help in reducing the performance imapact and can be
 implemented in future.

  
