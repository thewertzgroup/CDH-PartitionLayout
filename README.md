# CDH-PartitionLayout

## Edge Nodes

Edge nodes should be configured with RAID, and use [LVM](https://en.wikipedia.org/wiki/Logical_Volume_Manager_(Linux)).

This configuration will ensure your edge node does not go down becaue of a failed drive, and enable you to resize partitions as needed.

## Master Nodes

Master nodes should be configured with RAID, and use [LVM](https://en.wikipedia.org/wiki/Logical_Volume_Manager_(Linux)).

The master nodes are critical to the functioning of the cluster.  You do not want a master node going down because of a failed drive.  Higher quality machines, redundant power supplies.  This configuration will ensure your master nodes do not go down becaue of a failed drive, and enable you to resize partitions as needed.

## Worker Nodes (Compute / Storage)
