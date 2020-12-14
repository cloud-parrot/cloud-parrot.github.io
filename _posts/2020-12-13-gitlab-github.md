---
layout: post
section-type: post
title: "GITLAB VS GITHUB"
excerpt: ""
category: tech
tags: [ 'tutorial' ]
---

If you are willing to work on any IT project, then there might be chances of you coming across repository management services like version controlling tools useful for managing your codebase workflow in an organized way. You already must have heard about git repositories (it's place where you and your teammates store, share, test and collaborate on code). 

Uniqueness of git falls unders its distributed approach, it permits users to have their own local repositories and can work on their code without having the internet access. Once the changes are done in the local repository, then those changes can be pushed to the master repository and then waits for the approval. Once its approved then the process repeats until users achieve their development objective. Both Github and Gitlab are web-based repositories. And in this blog we will be talking about some of the key differences between Github and Gitlab [2020].


## Gitlab - What I think and How do I use it!


Basically GitLab is a repository mangement platform with lots of tools which allows IT teams to collaborate on code. Gitlab is mainly written in Ruby and Go. GitLab is designed with the purpose of serving with a Web IDE. The cool part is, the GitLab’s Web IDE is integrated with built-in CI/CD framework which offers Auto DevOps which automatically runs CI/CD merge requests without a user being involved setting it up which has ultimately speed up your GitLab workflow. From the release of 10.0 version Gitlab has announced an integraton between development and DevOps toolchains which has united the development and operations in on user experice. Since Gitlab offers its built in CI then users dont need to us any external CI service and in case if a user is already using an external CI tool then still Gitlab allows to integrate with tools like Jenkins, Codeship, etc. GitLab is a very useful platform for issue tracking and project management for the DevOps operations because it provides a dashboard that lets you understand the dependencies of your development and DevOps efforts. Additional feature with GitLab is, it basically allows user to provide access to the issue tracker (without giving permission to the source code) and this is a great feature for teams with lot of contributors as well as role-based contributors with enterprises. GitLab also offers detailed documentation on how to import your data from other vendors – such as GitHub, Bitbucket – to GitLab. So in my opinion GitLab is the most feature-rich git platform currently available in market.

**Some of the DevOps features I am aware of:**

1. Testing and deploying of your application on Kubernetes environment can be done with Gitlab. 
2. Gitlab offers WAF(The Web Application Firewall) to managed Kubernetes clusters to detect and block web based attacks using the OWASP core ruleset.
3. GitLab offers monitoring and logging of running pods in connected Kubernetes clusters.

## Github - What I think and How do I use it!

GitHub is also a Git-based repository hosting platform and it's the largest source code globally. GitHub repositories can be made public and every publicly shared code in the repository is freely open to everyone, this publicly shared repositories are often used to share open source software. With Github you can create private repositories as well, as per Github's recent official announcement If you're using GitHub Free, you can add unlimited collaborators on public and private repositories. However, besides the code repository, GitHub can also be used for issue tracking, documentation, and wikis. Similar to Gitlab, in GitHub as well user can decide if someone gets a read or write access to a repository. Github doesn’t provide detailed documentation on on how to import/export your data from other vendors – such as  Bitbucket – to Github, which might be considered as a disadvantage for smaller dev teams when it comes to your Github workflow. However, GitHub offers to use GitHub Importer if you have your source code in Subversion, Mercurial, TFS and others. Github has also launched it's build-in CI/CD framework that means users don't need to integrate a 3rd party CI/CD tool to Github in order to automate testing and speeding up the development process. However users can still use the 3rd party tools like Jenkins or CircleCI. I still do use Github just for browsing through the big ocean of OpenSource Projects and I kinda got used to with its userinterface.

**If we picturize these two platform this is how it looks like to me!!!**

![GLB!](/img/glb.png "GLB")


LMK in comments which one you guys like to use!

---

