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

# Backup and Restore Data of Old Version
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

  ▶ Available Plugin to backup Jenkins called "ThinBackup"
  
  ▶ Use `Versions Node Monitors` plugin to verify that agents are running a compatible version of Java.
  
  ▶ Update Jetty version to support OpenSSL

  ▶ Updated minimum supported remoting version

  ▶ New plugins will be automatically installed

- From 2.361.1 to 2.361.4 (Patch Version)

  *No notable changes requiring upgrade notes.*

- From 2.361.1 to 2.375.1 (Minor Version)
  
  ▶ Update some functionalities - Winstone and Jetty

  ▶ Remove flags which no longer serve a purpose with Java 11 or newer

- From 2.375.1 to 2.375.3 (Patch Version)

  *No notable changes requiring upgrade notes.*

- From 2.375.1 to 2.375.4 (Patch Version)

  ▶ Security fix for DoS vulnerability

- From 2.375.4 to 2.387.1 (Minor Version)

  ▶ De-duplicate logging implementations

  ▶ Set a default file size rotation of AsyncPeriodicWork/AsyncAperiodicWork

  ▶ Upgrade required Remoting version from 4.2.1 to 4.7

- From 2.387.1 to 2.387.2 (Patch Version)

  ▶ Repository Signing Key Update
     Debian/Ubuntu
  ```
    curl -fsSL https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key | sudo tee \
      /usr/share/keyrings/jenkins-keyring.asc > /dev/null
    echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] \
      https://pkg.jenkins.io/debian-stable binary/ | sudo tee \
      /etc/apt/sources.list.d/jenkins.list > /dev/null
  ```

- From 2.387.2 to 2.387.3 (Patch Version)

  ▶ XStream2 unable to round-trip ASCII NUL - Jenkins has switched from using KXm12Driver to StandardStaxDriver. Due to this change, Jenkins XML files can no longer save text content with the ASCII NUL character (U+0000). In particular, if you are using the <a href="https://plugins.jenkins.io/junit/">JUnit Plugin</a> to publish test results, be sure to update it to the <a href= "https://plugins.jenkins.io/junit/releases/">latest version</a> to avoid problems with new builds. Test results published with older versions of the plugin will remain unreadable.

- From 2.387.3 to 2.401.1 (Minor Version)
  
  ▶ Simplify loading of JavaScript and CSS - Jenkins JS module has been removed from Jenkins Core. <a href="https://plugins.jenkins.io/dependency-track/">OWASP Dependency Track</a> plugin must upgrade to 4.3.1 or newer. <a href="https://plugins.jenkins.io/servicenow-cicd/"> ServiceNow CI/CD</a> plugin must upgrade to 2.1 or newer.

- From 2.401.1 to 2.401.3 (Patch Version)
  
  *No notable changes requiring upgrade notes.*

- From 2.401.1 to 2.414.1 (Minor Version)
  
  ▶ Jenkins sign-in page update

  ▶ Remove dependency on jenkins-js-modules

- From 2.414.1 to 2.414.2 (Patch Version)

  ▶ Jenkins sign-in page update

- From 2.414.2 to 2.414.3 (Patch Version)
  
  *No notable changes requiring upgrade notes.*

- From 2.414.2 to 2.426.1 (Minor Version)
  
  ▶ Java OpenJDK 21 supported

  ▶ Prototype removed from Jenkins

  ▶ Appearance system configuration breaks JCasC (Custom Theme)

  ▶ Minimum required Remoting version updated to 4.13

  ▶ Treeview option removed for artifactList

  ▶ Remove System V initialization script

  ▶ End of support for Red Hat Enterprise Linux 7 and is derivatives

- From 2.426.1 to 2.426.3 (Patch Version)

  *No notable changes requiring upgrade notes.*

  
