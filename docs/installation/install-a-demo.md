# Docker Demo

To test Islandora, there is [a starter-site based demo available in Google Drive](https://drive.google.com/file/d/1LrIe12eYAZjD4A8_cqf61RXv7mtMJRHH/view?usp=share_link). Both are loaded with the same sample content to demonstrate
features of Islandora and provide a starting point for exploration. 

Download your emo and use the instructions below to install.It is recommended that you have a minimum of 4GB of space available on your machine before getting started. It will take some time to build the image. Thanks, and happy building!

Requirements
==============================================================

Before you can set up your demonstration locally you must first install a few
software packages.

Docker Desktop
--------------------------------------------------------------

[Docker Desktop](https://www.docker.com/products/docker-desktop) provides a
graphical user interface for all major platforms.

<https://www.docker.com/products/docker-desktop>

Follow the link above and select the appropriate system and follow the
installation instructions.

For Windows 10, you may receive the "Docker Failed to Start" Error message. To resolve this:
    
* Download WSL 2 from Step 4 in [these instructions](https://learn.microsoft.com/en-ca/windows/wsl/install-manual#step-4---download-the-linux-kernel-update-package)--do not do any other steps in these instructions
* Under Windows ‘Firewall & Network Protection’, ‘Allow an app through the firewall’, and ‘Change settings’ to select the ‘Private’ box for ‘Virtual Machine Monitoring’
* Restart computer for all changes to take effect


**If you already have Docker Desktop installed,** make sure that the **Extensions** 
feature is listed in the left sidebar. If it is not, you need to update to the newest 
version of Docker Desktop. This is required to add the Portainer extension.

Portainer Extension
--------------------------------------------------------------

Once you have worker [Docker Desktop](#dockerdesktop) installation, you can add
the [Portainer](https://portainer.io/) extension:

1. Open Docker Desktop.
2. From the Dashboard, select Add Extensions in the menu bar.
3. The Extensions Marketplace opens.
4. Browse the available extensions.
5. Select **Portainer**
6. Click Install.

For more information on Portainer refer to its
[documentation](https://docs.portainer.io/).

Setup
==============================================================

Assuming you have all the [Requirements](#requirements) installed
and running. You can now setup your demo. 

Get a Yaml file
--------------------------------------------------------------
 [Download this .zip file](https://drive.google.com/file/d/1LrIe12eYAZjD4A8_cqf61RXv7mtMJRHH/view?usp=share_link) and use the yaml file provided inside.


Create Stack
--------------------------------------------------------------
Once you have downloaded the pre-made yaml file, you can open **Portainer** via the Docker
Desktop Dashboard. 

1. Open Docker Desktop.
2. Click on Portainer.
3. If you see the Quick Setup Environment Wizard, click “Get Started". Otherwise, select your local environment under "Environments".
4. Open the sidebar.
5. Click on **Stacks**.
6. Click **Add Stack**.
7. Type in the name **sandbox** (_lowercase_).
8. Select **Upload from your Computer**.
9. Upload the **docker-compose.yml** file you generated via the setup script.
10. Click on **Deploy the Stack**. The button will then display _Deployment in progress_  - do not click away while this message is shown.

This may take a **very long** time if this is the first time setting up
the demo as it must download all the Docker Images from the
internet. 


Wait for Install
--------------------------------------------------------------

Demo still needs to install and configure `Drupal`, which may
take upwards of _10-15 minutes_. You can check on the install process by doing
the following.

1. Open Docker Desktop.
2. Click on Portainer.
3. Open the sidebar.
4. Click on **Stacks**.
5. Click on **sandbox**.
6. Click on the Logs icon for **Drupal**.
7. Examine the log output waiting for the message below.

When completed you should see the following output at the end of the log.

```
#####################
# Install Completed #
#####################
```

You can now visit your local demo in your browser of choice at:

older demo: <https://sandbox.islandora.dev>
newer demo: <http://islandora.io/>


The login credentials 
older demo: https://github.com/Islandora/documentation/wiki/Sandbox.Islandora.ca-online-credentials
newer demo: un:admin/pw:password


Reinstall
==============================================================

If you want to re-install your demo and restore it to its original
state., please perform the following steps:

1. Open Docker Desktop.
2. Click on Portainer.
3. Open the sidebar.
4. Click on **Stacks**.
5. Click on **sandbox**.
6. Click on **Stop this Stack**.
7. Click on **Volumes** in the sidebar.
8. Search for **sandbox**.
9. Ensure that all items are listed.
10. Select all items.
11. Click on **Remove**.
12. Click on **Stacks** in the sidebar.
13. Click on **sandbox**.
14. Click on **Start this Stack**.
15. Wait for the installation to complete like in the [Wait for Install Section](#waitforinstall)


Uninstall
==============================================================

If you want to completely uninstall your demo, please perform the
following steps:

1. Open Docker Desktop.
2. Click on Portainer.
3. Open the sidebar.
4. Click on **Stacks**.
5. Click on **sandbox**.
6. Click on **Delete this Stack**.
7. Click on **Volumes** in the sidebar.
8. Search for **sandbox**.
9. Ensure that all items are listed.
10. Select all items.
11. Click on **Remove**.

