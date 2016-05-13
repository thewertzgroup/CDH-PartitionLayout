# CDH-PartitionLayout

## Edge Nodes

Edge nodes should be configured with RAID, and use [LVM](https://en.wikipedia.org/wiki/Logical_Volume_Manager_(Linux)).

This configuration will ensure your edge node does not go down becaue of a failed drive, and enable you to resize partitions as needed.

There is no charge in CDH Enterprise licensing for edge nodes configured in a cluster and manged by Cloudera Manager.

## Master Nodes

Master nodes should be configured with RAID, and use [LVM](https://en.wikipedia.org/wiki/Logical_Volume_Manager_(Linux)).

The master nodes are critical to the functioning of the cluster.  You do not want a master node going down because of a failed drive.  Higher quality machines, redundant power supplies.  This configuration will ensure your master nodes do not go down becaue of a failed drive, and enable you to resize partitions as needed.

## Worker Nodes (Compute / Storage)

Worker nodes should have the OS partitions configured as raid and use [LVM](https://en.wikipedia.org/wiki/Logical_Volume_Manager_(Linux)).

This configuration will ensure your worker nodes do not go down because of a failed drive on an OS partition, and enable you to resize partitions as needed.

Specifcially /var/log (~200GB) and /opt should be on their own partition tend to fill up pretty rapidly.  You don't want a node to go down due to logging, or parcel download and distribution.

The *data* partitions *SHOULD NOT* be configured as RAID, and *SHOULD NOT* use LVM.  They should be configured as JBOD.  The cluster processes will handle the allocation of blocks, and replication will handle failure and data loss from a failed drive and/or node.
