# HDFS config for the Bigstep Datalake

This configuration enables the use of the standad hadoop commands without any additonal library. This is usefull when the setup does not involve a full hadoop environment but only an isolated hdfs client library. 
See (https://github.com/bigstepinc/hadoop-bigstep) for the official alternative that enables the use of the Kerberised datalake in tandem with a secure or unsecure hadoop cluster.

To use, make sure you have a hadoop binary distribution installed from (http://hadoop.apache.org/releases.html). Get the *krb5.conf* file and the *kxxx* and *dlxxx* ids from the Bigstep Control panel.
```bash
#clone this repo
git clone git@github.com:bigstepinc/hdfs-config-for-datalake.git

#log into kerberos
kinit kxxx@bigstep.io

#change the default hadoop conf dir. Note that this might affect the regular behaviour of the hadoop environment.
export HADOOP_CONF_DIR=/root/hdfs-config-for-datalake

#issue commands that interact with the DataLake cluster.
hadoop ls -fs hdfs://namenodes-data-lake01-uk-reading.bigstep.io/data_lake/dlxxx/
