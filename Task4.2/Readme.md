# TASK 4.2
🔷According to popular articles, Hadoop uses the concept of parallelism to
upload the split data while fulfilling Velocity problem.

👉🏻 Research with your teams and conclude this statement with proper proof

✴️Hint: tcpdump

---------------------------------------------------------------------------

Here we can snip up the network packets for incoming and outgoing traffic for slaves.

##### Using hdfs client or Master Node:

Upload some random file over the cluster:

Command :  `hadoop fs -put <userfile> <dir>`

![pic1](https://github.com/Hubcodee/Hadoop-Analysis/blob/main/Task4.2/Screenshot%20(1327).png)
 
 ---------------------------------------------------------------------------
 
Command to be used on both of the slave nodes for packet sniffing:

`tcpdump -i <networkcard> protocol -n`

Here protocol on which hdfs cluster works is #### TCP

![pic2](https://github.com/Hubcodee/Hadoop-Analysis/blob/main/Task4.2/Screenshot%20(1325).png)

`Here in above image you can see 65.1.1.75 has contacted to Slave Node 1 for data blocks transfer`

Similarly in below image:

![pic3](https://github.com/Hubcodee/Hadoop-Analysis/blob/main/Task4.2/Screenshot%20(1326).png)

 `Master node : 43.205.130.230 has connected with slave node 2 for storing data blocks`
 
 ### Thus we can conclude above problem statement.
