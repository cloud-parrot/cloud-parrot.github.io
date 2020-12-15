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

 1. Go to Start> Settings > Update & Security > For Developer

![PS6!](/img/winl_6.png)

 2. Then Go to the Run and Type: **optionalfeatures.exe** hit **↩**

 3. Scroll down to check off **Windows Subsystem ofr Linux** then press OK

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

**If you want to learn more about linux then following are the useful websites for self-learners** 
<style>
pre {
  white-space: pre !important;
  overflow-y: scroll !important;
  height: 50vh !important;
}
</style>
<pre><code data-trim class="yaml">

1. Useful for self learning (https://linuxjourney.com/)
2. Best one liners for linux command line (https://www.commandlinefu.com/commands/browse)
3. Find files in linux from command line (https://linuxize.com/post/how-to-find-files-in-linux-using-the-command-line/)
4. Improve your typing speed on the command line with this awesome tool! (https://github.com/balzss/cli-typer)
5. An interactive cheatsheet tool for the command-line (https://github.com/denisidoro/navi)
6. Customize your shell environment to next level (https://github.com/alebcay/awesome-shell)
7. I find it useful to learn new things with the self learning courses offered by github (https://lab.github.com/)
8. A static analysis tool for shell scripts (https://github.com/koalaman/shellcheck)
9. A good collection of bash snippets if you are starting to learn about shell scripts in linux (https://github.com/alexanderepstein/Bash-Snippets)

</code></pre>



---
