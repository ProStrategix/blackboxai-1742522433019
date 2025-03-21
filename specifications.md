# Project Specifications

This document serves as a persistent record of project requirements and specifications.

## Requirements
### Background
    My client screwed up their server set up. Their request to us was host the site we custom built on this server. This server lacks any DNS binding capability, which makes connecting the DNR to the NS (this server) impossible given they beleive the do not need it. To overcome this obsticle, we resorted to provisioning a VM on azure. To which, we have installed NGINX and BIND. The application itself was installed on the VM via git. 

    Tech stack. Linux (Ubuntu), XGINX/BIND, EJS (express NodeJs engine), MongoDB database

### Goal
    Successfully connect to the site using public domain name under an HTTPS protocol 


## Technical Specifications
Much of this work has been started. We need to complete the following:
    1. Configure Persistent Storage:
       - Verify/Add persistent disk storage on Azure VM
       - Ensure all installations and configurations persist between VM sessions
       - Re-install necessary components (NGINX, BIND) on persistent storage
    
    2. Install an SSL Cert - can be self created or using azure. Its unclear if Azure will permit and self created cert like Let's Encrypt
    
    3. Configure NGINX and BIND to incorporate the cert and act as the NS for the public domain name.
    
    4. Configure GoDaddy (DNR) to redirect the NS traffic to our site by pointing to the NS
    
    5. Ensuring the traffic is directed to the right port 3000 via NGINX and executes app.js or node app.js launch the application.

## Notes
    - Critical: Current configuration is not persisting between VM sessions
    - Need to implement persistent storage solution before proceeding with other configurations
    - Should confirm that the current config is valid prior to adding new