---
layout: post
section-type: post
title: Configuring Linux on Windows 10
category: tech
tags: [ 'tutorial']
---

# Everyone needs to learn Linux

Especially If you are in IT, it doesn't matter either you in heldesk, Network Engineering, System Engineering, Programming or a Hacking, it has become essential to know the Linux!
#RequiredSkill Linux is everywhere! YouTube, Netlflix, Tesla runs on Linux and according to the research Top 1M websites in the world (96% of them) runs on Linux. #BigDeal 

**Few Options I'm aware of from where you can learn the Linux**

<p style='text-align: left;'> 1. Cloud Platforms - AWS, GCP, Azure, Linode (Most of these cloud platforms provides free accounts where you can deploy Ubuntu Server) </p>
<p style='text-align: left;'> 2. Installing WSL (Windows Subsystem for Linux) which allows to install Linux on any version of Windows 10. </p>

Please Note: Bash on Ubuntu on Windows 10 does not work on the 32 bit version of Windows 10, because it requires Hyper-V

In this blog I'll be showing you the steps required in second option.

**Step 1:** Enable the Windows Subsystem for Linux using the following command

Open the PowerShell as Admin and Run the command

![PS!](/img/winl_1.png)

After running the command If you haven't Enabled the developer mode in Windows 10 then you will face the error.

To Enable the Developer mode in Windows 10 follow the below steps.

  Go to Start> Settings > Update & Security > For Developer

![PS6!](/img/winl_6.png)

  Then Go to the Run and Type: optionalfeatures.exe hit ↩

  Scroll down to check off **Windows Subsystem ofr Linux** then press OK

![PS7!](/img/winl_7.png)

Now you can Restart your machine and move on to the next step.

**Step 2:** Then Go to the App store and search for Linux

You will see the options for Linux flavors

![PS1!](/img/winl_2.png)

Select the Linux Flavor you want to Install

![PS2!](/img/winl_3.png)

After finishing the download you can just Launch it.

![PS2!](/img/winl_4.png)

**Step 3:** Final Step

Setup the Username and Password for your Ubuntu Machine

![PS3!](/img/winl_5.png)

Bingo! You're inside of the Linux

![PS4!](/img/winu.png)


# Conclusion

You've learned and successfully installed and set up a Linux distribution that is completely integrated with your Windows operating system!

---
