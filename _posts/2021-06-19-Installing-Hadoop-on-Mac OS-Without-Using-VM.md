
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

Credits >> [Read more..](https://hadoop.apache.org/)

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

**Step 1.** Type "java -version" in terminal to find if the java is installed or not. If not then download java from [here](https://www.oracle.com/java/technologies/javase-downloads.html)  The installer *jdk-16.0.1_osx-x64_bin.dmg* will be downloaded to your system.

```console
myhadoop@charons-MBP ~ % java -version
java version "16.0.1" 2021-04-20
Java(TM) SE Runtime Environment (build 16.0.1+9-24)
Java HotSpot(TM) 64-Bit Server VM (build 16.0.1+9-24, mixed mode, sharing)
```

**Step 2.** The installer automatically setup the path

```console
myhadoop@charons-MBP ~ % echo $(/usr/libexec/java_home)
/Library/Java/JavaVirtualMachines/jdk-16.0.1.jdk/Contents/Home
```
Now, you can check the installation by typing "java -version" in the terminal.

### 2. Setup new user account for Hadoop

**Step 1.** While already logged in into Admin account, Go to *System Preferences* and open *Users & Groups* and click on *+* to add a New User
pic 1
pic 2

**Step 2.** After that you need to give access to *Remote LogIn* 
pic 3

Now go to the terminal and fire following commands.

### Terminal commands to setup Hadoop Environment



I like to think them as a crazy fast lightweight microcomputers! In this context please don't let word 'micro' fool you because they are and they can be as powerful as you want them to be and similar to a VM they would have their own OS, their own CPU processes, their own memory, their own network and the most important thing is they are quaratined, they are isolated and they are secure.

**Follow the screenshot tutorial of Linode and play with Docker and Docker Containers**

*If you don't have an account on Linode then you gonna need one. (Its free account gives you $100 credit)*

![PS!](/img/linode1.png)

*Go to the Marketplace and scrll down to Docker*

![PS!](/img/linode2.png)

![PS!](/img/linode3.png)

![PS!](/img/linode4.png)

![PS!](/img/linode5.png)

![PS!](/img/linode6.png)

*Click on Launch SSH Console*

![PS!](/img/linode7.png)

![PS!](/img/linode8.png)

![PS!](/img/linode9.png)

![PS!](/img/linode10.png)

![PS!](/img/linode11.png)

![PS!](/img/linode12.png)

![PS!](/img/linode13.png)

![PS!](/img/linode14.png)

![PS!](/img/linode15.png)

![PS!](/img/linode16.png)

![PS!](/img/linode17.png)

![PS!](/img/linode19_dh.png)

![PS!](/img/linode20_dh.png)

![PS!](/img/linode21_dh.png)

![PS!](/img/linode22_dh.png)

![PS!](/img/linode23_docker_stats.png)



### How docker being used in IT?

We have already demonstrated that we can put docker container up in the cloud - Linode. You can move the same docker container to Azure, AWS they provide the similar environment as linode for the docker. Its just like a web application which you can deploy and launch your containers! This is amazing for developers because using docker container now they can write their code and deploy it in a docker container and make sure that it will works everywhere. Before this it was a problem with developers for a long time that they write code for an app on their computer and it works fine on thier end but as soon as when the same code goes to the QA team it don't work and developers had to get into discussion they don't want "Hey it worked on my machine, idk what's you are doing 😕". So basically docker coantainer helps avoid this becuase if you deploy your app in a docker container so everything that app needs is right there in that container, and its contained and isolated from other teams. 

Comming to the microservices Its a concept which is taking IT industry by storm! As you more dive into the DevOps stuff this the concept you have to understand and work with. Microservices involved taking portions of your application or your stack and segment again into smaller bits and pieces, So traditionally you have one server where your entire application is installed with all required resources. For example, For Wordpress application, you might install your Wordpress Server and MySql database on the same server.This is what developers might have done traditionally by installing as many as compatible apps they could on one server. But now with the help of containers one particular application program, eg. Wordpress server may be installed in one container and have MySql portion installed in another container so that they both treated as a separate program and this isolated feature of containers reduces the chances for conflicting things and when a developer wants to update one portion of application then he/she only needs to update just one container without disrupting the whole cycle.


**Important Links**

<pre><code data-trim class="yaml">
#useful link for docker images
https://hub.docker.com/

#know more about docker on
https://www.docker.com/
</code></pre>

---
