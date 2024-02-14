<a href="https://jenkins.io">
    <img width="400" src="https://www.jenkins.io/images/jenkins-logo-title-dark.svg" alt="Jenkins logo"> 
</a>

# About

[![Jenkins Regular Release](https://img.shields.io/endpoint?url=https%3A%2F%2Fwww.jenkins.io%2Fchangelog%2Fbadge.json)](https://www.jenkins.io/changelog)
[![Jenkins LTS Release](https://img.shields.io/endpoint?url=https%3A%2F%2Fwww.jenkins.io%2Fchangelog-stable%2Fbadge.json)](https://www.jenkins.io/changelog-stable)
[![Docker Pulls](https://img.shields.io/docker/pulls/jenkins/jenkins.svg)](https://hub.docker.com/r/jenkins/jenkins/)
[![CII Best Practices](https://bestpractices.coreinfrastructure.org/projects/3538/badge)](https://bestpractices.coreinfrastructure.org/projects/3538)
[![Gitter](https://img.shields.io/gitter/room/jenkinsci/jenkins)](https://app.gitter.im/#/room/#jenkinsci_jenkins:gitter.im)

In a nutshell, Jenkins is the leading open-source automation server.
Built with Java, it provides over 1,800 [plugins](https://plugins.jenkins.io/) to support automating virtually anything,
so that humans can spend their time doing things machines cannot.

# What to Use Jenkins for and When to Use It

Use Jenkins to automate your development workflow, so you can focus on work that matters most. Jenkins is commonly used for:

- Building projects
- Running tests to detect bugs and other issues as soon as they are introduced
- Static code analysis
- Deployment

Execute repetitive tasks, save time, and optimize your development process with Jenkins.

# Backup and Restore Date of Old Version
By default, all data would be stored in `/var/lib/jenkins`

### Create Backup folder and Copy to it
```
sudo mkdir /backups-jenkins2.346.3 && sudo cp /var/lib/jenkins /backups-jenkins2.346.3
```

Another way, we can use Jenkins Plugin called "ThinBackup" to backup and restore Jenkins. See here: https://plugins.jenkins.io/thinBackup/

# Upgrading-Jenkins
Step-to-upgrade-jenkins.
See upgrade documentation: https://www.jenkins.io/doc/upgrade-guide/

*Currently. We're using version 2.346.3, openjdk version 11.0.21*. 

## Step to upgrade
- From 2.346.3 to 2.361.1 (Minor version)
  
  ▶ Jenkins requires Java 11 or newer
  
  ▶ Use `Versions Node Monitors` plugin to verify that agents are running a compatible version of Java.
  
  ▶ Update Jetty version to support OpenSSL

  ▶ Updated minimum supported remoting version

  ▶ New plugins will be automatically installed

- From 2.361.1 to 2.361.4 (Patch Version)

  *No notable changes requiring upgrade notes.*

  
  
