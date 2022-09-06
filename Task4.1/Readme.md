# TASK 4.1

🔷In a Hadoop cluster, find how to contribute limited/specific amount of storage as slave to the cluster?

1.Attaching external ssd to Slave 1 (Redhat Instance on EC2)

![pic1](https://github.com/Hubcodee/Hadoop-Analysis/blob/main/Task4.1/Screenshot%20(1304).png)

![pic1](https://github.com/Hubcodee/Hadoop-Analysis/blob/main/Task4.1/Screenshot%20(1308).png)

2.Storage is attached to Slave1 - /sdf

![pic3](https://github.com/Hubcodee/Hadoop-Analysis/blob/main/Task4.1/Screenshot%20(1309).png)

3.`#fdisk -l` to check if device is attached or not?

![pic4](https://github.com/Hubcodee/Hadoop-Analysis/blob/main/Task4.1/Screenshot%20(1310).png)

4.Creating partition : `#fdisk /dev/xvdf`

![pic5](https://github.com/Hubcodee/Hadoop-Analysis/blob/main/Task4.1/Screenshot%20(1311).png)

![pic6](https://github.com/Hubcodee/Hadoop-Analysis/blob/main/Task4.1/Screenshot%20(1312).png)

5.Formatting the partition and mounting to datanode directory.

`#mkfs.ext4 /dev/xvdf1`
`#mount /dev/xvdf1 /datanode`

![pic7](https://github.com/Hubcodee/Hadoop-Analysis/blob/main/Task4.1/Screenshot%20(1313).png)

6.Partition is mounted:

![pic8](https://github.com/Hubcodee/Hadoop-Analysis/blob/main/Task4.1/Screenshot%20(1315).png)

7.Slave1 has datadir mounted with specified partition of 4GB:

`hadoop dfsadmin -report`

![pic9](https://github.com/Hubcodee/Hadoop-Analysis/blob/main/Task4.1/Screenshot%20(1316).png)

-----------------------------------------------------

Similarly we can follow above steps for slave node 2:

Thus,we can see, 2 data nodes are available with specified size.

![pic10](https://github.com/Hubcodee/Hadoop-Analysis/blob/main/Task4.1/Screenshot%20(1324).png)


