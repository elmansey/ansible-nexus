# nexus-ansible
## Overview
Install Latest Sonatype Nexus 3 on Ubuntu 22 using ansible \
[Sonatype Nexus](https://www.sonatype.com/products/nexus-repository) is one of the best open-source artifact management tools. It is some tool that you cannot avoid in your CI/CD pipeline. It effectively manages deployable artifacts.

---

## Sonatype Nexus System Requirements
* Minimum 1 VCPU & 2 GB Memory
* Server firewall opened for port 22 & 8081
* OpenJDK 8
* All Nexus processes should run as a non-root nexus user.

 ---
 
 ## Steps
 * Update the `apt` packages
 * Install  `java` 8
 * allow firewall ports `22 and 8081`
 * Download the latest nexus in /opt directory
 * Untar the downloaded file 
 * Rename the untared file to `nexus`
 * create nexus group and user
 * Create a service named `nexus`
 * Change the ownership of nexus files to `nexus` user
 * Create a nexus systemd unit file `/etc/systemd/system/nexus.service`
 * Start and enable nexus service

---
## Validation 
* run `ansible-playbook  nexus.yaml`
* Visit `http://<node ip>:8081`
* Log in using default username `admin ` and password found in `app/sonatype-work/nexus3/admin.password` 
#### Now you will be able to see the nexus homepage 
![image](https://user-images.githubusercontent.com/89076648/232769141-ecf36280-461f-4763-bb53-fe9d80820a9f.png)