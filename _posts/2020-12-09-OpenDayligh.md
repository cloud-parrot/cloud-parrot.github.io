---
layout: post
section-type: post
title: Install OpenDaylight as a service on Ubuntu 18.04LTS
category: tech
tags: [ 'tutorial' ]
---

## Know OpenDaylight

As written on the OpenDaylight website, OpenDaylight is the largest Open Source Controller. OpenDaylight (ODL) is a modular open platform for customizing 
and automating networks of any size and scale. The OpenDaylight project arose out of the SDN movement, with clear 
focus on network programmability.

OpenDaylight allows cloud engineers to programmatically deploy, configure and control virtual network services.

Following are the necessary steps to Install OpenDaylight on Ubuntu LTS 18.04

1. Ubuntu LTS 18.04 OS
2. Install JAVA JRE
3. Download OpenDaylight
4. Install OpenDaylight
5. Create configuration file - #systemd
6. Install and enable OpenDaylight Service - #systemd

## Prepare OS 

<pre><code data-trim class="yaml">
# Prepare your OS
$ sudo apt-get update

# Now install the required packages
$ sudo apt-get -y install unzip vim wget
</code></pre>

## Install JAVA JRE

Installation of OpenDaylight requires JAVA 8 Run Time environment

<pre><code data-trim class="yaml">
# Run the following command to install the JRE
$ sudo apt-get -y install openjdk-8-jre
</code></pre>

Ensure that your OS points to JAVA 8. If not make sure to select version 8 from the list.

<pre><code data-trim class="yaml">
# Run the following command to make sure
$ sudo update-alternatives --config java 
There is only one alternative in link group java (providing /usr/bin/java): /usr/lib/jvm/java-8-openjdk-amd64/jre/bin/java
Nothing to configure.
</code></pre>

Copy the information as you are going to need it in next step.

"In my case JAVA 8 binary resides in # /usr/lib/jvm/java-8-openjdk-amd64/jre/bin/java"

Now you know the path, run the following command to update your BASHRC file

<pre><code data-trim class="yaml">
$ echo 'export JAVA_HOME=/usr/lib/jvm/java-8-openjdk-amd64/jre' >> ~/.bashrc 
</code></pre>

*source* your *BASHRC* file again and ensure #JAVA_HOME is there in the environment

<pre><code data-trim class="yaml">
$ source ~/.bashrc 
# Make sure $JAVA_HOME ends with /jre
$ echo $JAVA_HOME
/usr/lib/jvm/java-8-openjdk-amd64/jre
</code></pre>

## Download the OpenDaylight ZIP or TAR Archive

Use the following link to exxplore the files you'd like to download

Download the *karaf-0.13.1.zip*  or *karaf-0.13.1.tar.gz* from [here] (https://nexus.opendaylight.org/content/repositories/opendaylight.release/org/opendaylight/integration/karaf/0.13.1/).

<pre><code data-trim class="yaml">
# The command you need to execute to download
$ wget https://nexus.opendaylight.org/content/repositories/opendaylight.release/org/opendaylight/integration/karaf/0.13.1/karaf-0.13.1.zip 
</code></pre>

## Install OpenDaylight

<pre><code data-trim class="yaml">
# Install the OpenDaylight into your OS
# make a directory install the files
$ sudo mkdir /usr/local/karaf 
# make sure to use the correct version. I downloade kraf-0.13.1 and yours may be different
$ sudo mv karaf-0.13.1.zip /usr/local/karaf
$ sudo unzip /usr/local/karaf/karaf-0.13.1.zip -d /usr/local/karaf/
</code></pre>

Now install **karaf** into user space

<pre><code data-trim class="yaml">
$ sudo update-alternatives --install /usr/bin/karaf karaf /usr/local/karaf/karaf-0.13.1/bin/karaf 1
update-alternatives: using /usr/local/karaf/karaf-0.13.1/bin/karaf to provide /usr/bin/karaf (karaf) in auto mode
$ sudo update-alternatives --config karaf
There is only one alternative in link group karaf (providing /usr/bin/karaf): /usr/local/karaf/karaf-0.13.1/bin/karaf
Nothing to configure.
$ which karaf
/usr/bin/karaf
</code></pre>

Now perform the test run. So OpenDaylight needs to write a PID file at /usr/bin/karaf and it requires **sudo** privileges.

<pre><code data-trim class="yaml">
$ sudo -E karaf
  link: /etc/alternatives/karaf
  link: /usr/local/karaf/karaf-0.13.1/bin/karaf
  Apache Karaf starting up. Press Enter to open the shell now...
  100% [========================================================================]
  Karaf started in 1s. Bundle stats: 54 active, 55 total
</code></pre>

![ODL!](/img/ODL_splash.png "ODL")

Now from **karf** cli, install the DELUX GUI 

<pre><code data-trim class="yaml">
opendaylight-user@root>feature:install odl-l2switch-switch-ui
opendaylight-user@root>
</code></pre>

You can validate **karaf** runs using **netstat** 

<pre><code data-trim class="yaml">
$ sudo netstat -an | grep 8181 
  tcp6       0      0 :::8181                 :::*                    LISTEN
  tcp6       0      0 172.31.18.10:8181       9.20.16.23:44955     ESTABLISHED
  tcp6       0      0 172.31.18.10:8181       9.20.16.23:10126     ESTABLISHED
</code></pre>

If you want to try the GUI, you can go to your URL and log into the DELUX console.
Use the credentials **admin/admin**. Make sure to inseret your IP address in the following URL
(Use port as 8181)

http://3.4.8.5:8181/index.html#/login

![ODL DELUX!](/img/ODL_delux_login.png "ODL DELUX")

You will see the DELUX Console, Once you login with **admin/admin**

![ODL DELUX!](/img/ODL_delux_con.png "ODL DELUX")

<pre><code data-trim class="yaml">
#If you want to shut down the service then type the following
opendaylight-user@root>system:shutdown
Confirm: halt instance root (yes/no): yes
opendaylight-user@root>
$
</code></pre>

## Installing the ODL STOP Script

ODL service requires a **stop** script in order to shutdown **karaf**

<pre><code data-trim class="yaml">
$ sudo update-alternatives --install /usr/bin/stop stop /usr/local/karaf/karaf-0.13.1/bin/stop 1
update-alternatives: using /usr/local/karaf/karaf-0.13.1/bin/stop to provide /usr/bin/stop (stop) in auto mode
$ sudo update-alternatives --config stop
There is only one alternative in link group stop (providing /usr/bin/stop): /usr/local/karaf/karaf-0.13.1/bin/stop
Nothing to configure.
$ which stop
/usr/bin/stop
</code></pre>

## Creating **systemd** service configuration file

<pre><code data-trim class="yaml">
$ sudo vim /etc/systemd/system/opendaylight.service
</code></pre>

<pre><code data-trim class="yaml">
[Unit]
Description=OpenDaylight Controller
After=network.target

[Service]
Type=simple
User=root
Group=root
Environment="JAVA_HOME=/usr/lib/jvm/java-8-openjdk-amd64/jre"
ExecStart=/usr/bin/karaf server
ExecStop=/usr/bin/stop
Restart=on-failure
RestartSec=60s

[Install]
WantedBy=multi-user.target

</code></pre>

To stop and start services we used **karaf** and **stop** binaries in **/usr/bin**
This will help to upgrade OpenDaylight via **update-alternatives**

<pre><code data-trim class="yaml">
# Now change the permissions of the service config file
$ sudo chmod 0644 /etc/systemd/system/opendaylight.service
</code></pre>

<pre><code data-trim class="yaml">
# Now load the opendaylight service
$ systemctl daemon-reload
</code></pre>

<pre><code data-trim class="yaml">
# to start the service at bootup
$ sudo systemctl enable opendaylight.service
Created symlink /etc/systemd/system/multi-user.target.wants/opendaylight.service → /etc/systemd/system/opendaylight.service.
</code></pre>

<pre><code data-trim class="yaml">
# sometimes status command states this
$ sudo systemctl status opendaylight
● opendaylight.service - OpenDaylight Controller
   Loaded: loaded (/etc/systemd/system/opendaylight.service; enabled; vendor preset: enabled)
   Active: inactive (dead)
</code></pre>

<pre><code data-trim class="yaml">
# if you have reboot try the alternative way
$ sudo systemctl start opendaylight

$ps -ef | grep karaf
root     21686     1  0 17:44 ?        00:00:00 /bin/sh /usr/bin/karaf server
root     21770 21686 99 17:44 ?        00:00:40 /usr/lib/jvm/java-8-openjdk-amd64/jre/bin/java -Djava.security.properties=/usr/local/karaf/karaf-0.13.1/etc/odl.java.security -Xms128M -Xmx2048m -XX:+UnlockDiagnosticVMOptions -XX:+HeapDumpOnOutOfMemoryError -Dcom.sun.management.jmxremote -Djava.security.egd=file:/dev/./urandom -Djava.endorsed.dirs=/usr/lib/jvm/java-8-openjdk-amd64/jre/jre/lib/endorsed:/usr/lib/jvm/java-8-openjdk-amd64/jre/lib/endorsed:/usr/local/karaf/karaf-0.13.1/lib/endorsed -Djava.ext.dirs=/usr/lib/jvm/java-8-openjdk-amd64/jre/jre/lib/ext:/usr/lib/jvm/java-8-openjdk-amd64/jre/lib/ext:/usr/local/karaf/karaf-0.13.1/lib/ext -Dkaraf.instances=/usr/local/karaf/karaf-0.13.1/instances -Dkaraf.home=/usr/local/karaf/karaf-0.13.1 -Dkaraf.base=/usr/local/karaf/karaf-0.13.1 -Dkaraf.data=/usr/local/karaf/karaf-0.13.1/data -Dkaraf.etc=/usr/local/karaf/karaf-0.13.1/etc -Dkaraf.restart.jvm.supported=true -Djava.io.tmpdir=/usr/local/karaf/karaf-0.13.1/data/tmp -Djava.util.logging.config.file=/usr/local/karaf/karaf-0.13.1/etc/java.util.logging.properties -Dkaraf.startLocalConsole=false -Dkara .startRemoteShell=true -classpath /usr/local/karaf/karaf-0.13.1/lib/boot/org.apache.karaf.diagnostic.boot-4.1.6.jar:/usr/local/karaf/karaf-0.13.1/lib/boot/org.apache.karaf.jaas.boot-4.1.6.jar:/usr/local/karaf/karaf-0.13.1/lib/boot/org.apache.karaf.main-4.1.6.jar:/usr/local/karaf/karaf-0.8.4/lib/boot/org.osgi.core-6.0.0.jar org.apache.karaf.main.Main
ubuntu   21906 19962  0 17:45 pts/1    00:00:00 grep --color=auto karaf
</code></pre>

<pre><code data-trim class="yaml">
# systemctl provides a status command

$ sudo systemctl status opendaylight
● opendaylight.service - OpenDaylight Controller
   Loaded: loaded (/etc/systemd/system/opendaylight.service; enabled; vendor preset: enabled)
   Active: active (running) since Sat 2018-12-29 17:44:39 UTC; 15min ago
 Main PID: 21686 (karaf)
    Tasks: 129 (limit: 4915)
   CGroup: /system.slice/opendaylight.service
           ├─21686 /bin/sh /usr/bin/karaf server
           └─21770 /usr/lib/jvm/java-8-openjdk-amd64/jre/bin/java -Djava.security.properties=/usr/local/karaf/karaf-0.13.1/etc/

Dec 9 17:44:39 ip-172-31-18-10 systemd[1]: Started OpenDaylight Controller.
Dec 9 17:44:39 ip-172-31-18-10 karaf[21686]: link: /etc/alternatives/karaf
Dec 9 17:44:39 ip-172-31-18-10 karaf[21686]: link: /usr/local/karaf/karaf-0.13.1/bin/karaf
Dec 9 17:44:40 ip-172-31-18-10 karaf[21686]: Apache Karaf starting up. Press Enter to open the shell now...
Dec 9 17:45:01 ip-172-31-18-10 karaf[21686]: [7.8K blob data]
Dec 9 17:45:01 ip-172-31-18-10 karaf[21686]: Karaf started in 20s. Bundle stats: 419 active, 420 total
</code></pre>

<pre><code data-trim class="yaml">
# stop odl
$ sudo systemctl stop opendaylight
</code></pre>

### Conclusion

That's it! You have learned the Installation of OpenDaylight as a service on Ubuntu LTS 18.04.

Thank you!

