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

```console
myhadoop@charons-MBP ~ % echo $(/usr/libexec/java_home)
/Library/Java/JavaVirtualMachines/jdk-16.0.1.jdk/Contents/Home
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
