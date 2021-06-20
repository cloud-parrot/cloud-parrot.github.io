---
layout: post
section-type: post
title: Hadoop installation guide on MAC-OS
category: tech
tags: [ 'tutorial']
---

### What is Hadoop?

The Apache™ Hadoop® project develops open-source software for reliable, scalable, distributed computing.

The Apache Hadoop software library is a framework that allows for the distributed processing of large data sets across clusters of computers using simple programming models. It is designed to scale up from single servers to thousands of machines, each offering local computation and storage. Rather than rely on hardware to deliver high-availability, the library itself is designed to detect and handle failures at the application layer, so delivering a highly-available service on top of a cluster of computers, each of which may be prone to failures.

[Read more..](https://hadoop.apache.org/)

### What is Hive?

The Apache Hive ™ data warehouse software facilitates reading, writing, and managing large datasets residing in distributed storage using SQL. Structure can be projected onto data already in storage. A command line tool and JDBC driver are provided to connect users to Hive.

[Read more..](https://hive.apache.org/)

### What is HPL/SQL?

Hive Hybrid Procedural SQL On Hadoop (HPL/SQL) is a tool that implements procedural SQL for Hive. HPL/SQL is an open source tool (Apache License 2.0) that implements procedural SQL language for Apache Hive, SparkSQL, Impala as well as any other SQL-on-Hadoop implementation, any NoSQL and any RDBMS. HPL/SQL language is compatible to a large extent with Oracle PL/SQL, ANSI/ISO SQL/PSM (IBM DB2, MySQL, Teradata), PostgreSQL PL/pgSQL (PostgreSQL, Netezza) and Transact-SQL (Microsoft SQL Server and Sybase) that facilitates migration of existing business logic to Hadoop.

[Read more..](https://cwiki.apache.org/confluence/pages/viewpage.action?pageId=59690156)


**This blog will help you how to install Hadoop framework on MAC-OS without using any VM**

<p style='text-align: left;'> 1. Installing JDK </p>
<p style='text-align: left;'> 2. Setting up user account for Hadoop </p>
<p style='text-align: left;'> 3. Terminal commands to setup Hadoop Environment </p>
<p style='text-align: left;'> 4. Downloading Hadoop  </p>
<p style='text-align: left;'> 5. How Hadoop being used in IT? </p>

Let's begin

### 1. Make dure you have JDK installed in your machine

**Step 1.** Type "java -version" in terminal to find if the java is installed or not. If not then download java from [here](https://www.oracle.com/java/technologies/javase-downloads.html).  
The installer *jdk-16.0.1_osx-x64_bin.dmg* will be downloaded to your system.

```console
myhadoop@charons-MBP ~ % java -version
java version "16.0.1" 2021-04-20
Java(TM) SE Runtime Environment (build 16.0.1+9-24)
Java HotSpot(TM) 64-Bit Server VM (build 16.0.1+9-24, mixed mode, sharing)
```

**Step 2.** The installer will automatically setup the default path for your jdk environment

```console
myhadoop@charons-MBP ~ % echo $(/usr/libexec/java_home)
/Library/Java/JavaVirtualMachines/jdk-16.0.1.jdk/Contents/Home
```
Now, you can check the installation by typing "java -version" in the terminal.

### 2. Setup new user account for Hadoop

**Step 1.** While already logged in into Admin account, Go to *System Preferences* and open *Users & Groups* and click on *+* to add a New User

![PS!](/img/h1.png)

![PS!](/img/linode22_dh.png)

**Step 2.** After that you need to give access to *Remote LogIn* 

![PS!](/img/linode22_dh.png)

Now go to the terminal and fire following commands.

### Terminal commands to setup Hadoop Environment

Beofore establising localhost connection you need to geneate a key

```console
myhadoop@charons-MBP ~ % ssh-keygen -t rsa -P ""
```
![PS!](/img/linode22_dh.png)

After the key generation you will be getting two files,
*id_rsa
*id_rsa.pub
To verify, use the following command.

```console
myhadoop@charons-MBP ~ % cd .ssh
myhadoop@charons-MBP .ssh % ls -lrt 
```
Now you need to move this two files into your Authorized Key folder

```console
myhadoop@charons-MBP .ssh % cat /Users/myhadoop/.ssh/id_rsa.pub >> /Users/myhadoop/.ssh/authprized_keys 
```
Now try to establish localhost connection typing the following command.

```console
myhadoop@charons-MBP ~ % ssh localhost 
Last login: Sat June 19 14:47:45 2021
myhadoop@charons-MBP ~ % exit
Connection to localhost closed.
```

# Now you can download the Hadoop from [here](http://mirrors.estointernet.in/apache/hadoop/common/hadoop-3.2.2/)
The file *hadoop-3.2.2.tar.gz* will be downloaded to your system.

If you prefert to use terminal to unzip the file use the following command

```console
myhadoop@charons-MBP ~ % hadoop$tar -xzvf hadoop-*
```

After downloading the Hadoop you need to configure it,

```console
myhadoop@charons-MBP ~ % cd hadoop-3.2.2
myhadoop@charons-MBP hadoop-3.2.2 % ls
```
Now change the Hadoop configuration files,

```console
myhadoop@charons-MBP ~ % cd etc/hadoop/
myhadoop@charons-MBP ~ % ls
myhadoop@charons-MBP ~ % open hadoop-env.sh
```

In hadoop-env.sh file add,
```console
export JAVA_HOME=/Library/Java/JavaVirtualMachines/jdk-16.0.1.jdk/Contents/Home
```

In core-site.xml add following between configuration tabs,
```console
<configuration>  
    <property>  
        <name>fs.defaultFS</name>  
        <value>hdfs://localhost:9000</value>  
    </property>  
</configuration>  
```

In hdfs-site.xml add the following between configuration tabs,
```console
<configuration>  
    <property>  
        <name>dfs.replication</name>  
        <value>1</value>  
    </property>  
</configuration>
```

In mapred-site.xml add the following between configuration tabs,
```console
<configuration>
    <property>
        <name>mapreduce.framework.name</name>
        <value>yarn</value>
    </property>
    <property>
        <name>mapreduce.application.classpath</name>
        <value>$HADOOP_MAPRED_HOME/share/hadoop/mapreduce/*:$HADOOP_MAPRED_HOME/share/hadoop/mapreduce/lib/*</value>
    </property>
</configuration>
```

In yarn-site.xml add the following between configuration tabs,
```console
<configuration>
    <property>
        <name>yarn.nodemanager.aux-services</name>
        <value>mapreduce_shuffle</value>
    </property>
    <property>
        <name>yarn.nodemanager.env-whitelist</name>
        <value>JAVA_HOME,HADOOP_COMMON_HOME,HADOOP_HDFS_HOME,HADOOP_CONF_DIR,CLASSPATH_PREPEND_DISTCACHE,HADOOP_YARN_HOME,HADOOP_MAPRED_HOME</value>
    </property>
</configuration>
```














java -version
ssh localhost
ssh-keygen -t rsa -P “”
cd .ssh
ls -lrt
cat /Users/hadoop/.ssh/id_rsa.pub >> /Users/hadoop/.ssh/authorized_keys
cd
ssh localhost
exit
Download .tar.gz file http://mirrors.estointernet.in/apache/hadoop/common/hadoop-3.2.1/
hadoop$tar -xzvf hadoop-*
cd hadoop-3.2.1
cd etc/hadoop
ls



![PS!](/img/linode22_dh.png)

![PS!](/img/linode23_docker_stats.png)



### How docker being used in IT?

**Important Links**

<pre><code data-trim class="yaml">
#useful link for docker images
https://hub.docker.com/

#know more about docker on
https://www.docker.com/
</code></pre>

---
