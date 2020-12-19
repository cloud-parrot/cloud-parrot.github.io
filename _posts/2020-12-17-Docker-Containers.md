---
layout: post
section-type: post
title: A deep dive into Docker & Docker Containers
category: tech
tags: [ 'tutorial']
---

### Docker and Docker Containers

Current trends in IT indicates that software containers are the future of IT, hence According to the current trends in IT this is the high time for anyone who is in IT and wanted to learn about Docker and Docker Containers. If you are planning to learn and work in DevOps, Networking, Systems and Cloud platforms like Azure, AWS, GCP and Linode then the understanding of Docker and Docker containers will comes in very handy for you.  


**In this blog I'll be covering three things?**

<p style='text-align: left;'> 1. What docker and docker containers are replacing in terms of Virtualization? </p>
<p style='text-align: left;'> 2. What's docker doing? </p>
<p style='text-align: left;'> 3. What are containers? </p>
<p style='text-align: left;'> 4. Linode Tutorial? </p>
<p style='text-align: left;'> 5. How docker being used in IT? </p>

Before we can define what's docker and docker containers, We should know about what it's basically replacing with?

According to the current trends in IT, The Docker and Docker conatiners are decreasing the use of VM's. Traditionally, before VM, users used to install the OS on a piece of HW, i.e. Physical Server, and all of the resources of this physical server (CPU, RAM, Hard Drive etc) would be dedicated to the one OS, i.e. One Server OS. There is no issue with that at all, Unless you want another server to install for another OS, So before VM's consider if you want to learn or make use of Windows Server and Linux Server so you had to have separate physical server (HW machines), To tackle this problem Virtualization comes into the picture, So now instead of installing one OS you will only need to install something called "Hypervisor". Now Hypervisor is kind of an OS but has only one goal that is, helping to distribute your server resources into multiple servers. Now there are tons of Hypervisors available in the market but the most popular one is VMWare, which I personally prefer using on my server (VMware ESXi), because it simply distributes a portion of your server's resources untill server runs out of its resources. But when we use docker containers again it takes us back to before virtualization so similarly when the user installs one OS on the entire server and that one OS gets access to everything our Physical server has to offer. Now here comes the docker into the picture!

### What's docker doing?

So as we discussed above, Virtualization in virtual machines are basically virtualizing HW, and in case of Docker, it basically virtualizes the OS!

It means that we will always have our hardware but instead of hypervisor we are going to have one OS installed on top of the Hardware or on to the HW. For example, we have installed Ubuntu and now docker comes into the picture and makes things happen. Now docker installs like any other application you install on linux, so basically it will be a process running or deamon running and then using docker we will virtualize portions of our OS to create containers. This docker containers are doing the same thing as virtual machine installed on Hypervisors (VMware ), they have similar functions and have one of the same qualities which is why its kind of cool how they can replace virtual machines. And these containers similar to VM's can be running a different OS for example, CentOS, Ubuntu etc.

### What are Docker Containers?

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
