**==> picture [598 x 186] intentionally omitted <==**

## Rocket MultiValue DevOps Experience 

## Installation and User Guide 

_Version 0.1.0_ 

**==> picture [598 x 21] intentionally omitted <==**

December 2019 MVX-010-UG-01 

## Notices 

## Edition 

**Publication date** : December 2019 **Book number** : MVX-010-UG-01 **Product version** : Version 0.1.0 

## Copyright 

© Rocket Software, Inc. or its affiliates 1996-2019. All Rights Reserved. 

## Trademarks 

Rocket is a registered trademark of Rocket Software, Inc. For a list of Rocket registered trademarks go to: www.rocketsoftware.com/about/legal. All other products or services mentioned in this document may be covered by the trademarks, service marks, or product names of their respective owners. 

## Examples 

This information might contain examples of data and reports. The examples include the names of individuals, companies, brands, and products. All of these names are fictitious and any similarity to the names and addresses used by an actual business enterprise is entirely coincidental. 

## License agreement 

This software and the associated documentation are proprietary and confidential to Rocket Software, Inc. or its affiliates, are furnished under license, and may be used and copied only in accordance with the terms of such license. 

**Note:** This product may contain encryption technology. Many countries prohibit or restrict the use, import, or export of encryption technologies, and current use, import, and export regulations should be followed when exporting this product. 

2 

## Corporate information 

Rocket Software, Inc. develops enterprise infrastructure products in four key areas: storage, networks, and compliance; database servers and tools; business information and analytics; and application development, integration, and modernization. 

Website: www.rocketsoftware.com 

Rocket Global Headquarters 77 4[th] Avenue, Suite 100 Waltham, MA 02451-1468 USA 

To contact Rocket Software by telephone for any reason, including obtaining pre-sales information and technical support, use one of the following telephone numbers. 

|**Country**|**Toll-free telephone number**|
|---|---|
|United States|1-855-577-4323|
|Australia|1-800-823-405|
|Belgium|0800-266-65|
|Canada|1-855-577-4323|
|China|400-120-9242|
|France|08-05-08-05-62|
|Germany|0800-180-0882|
|Italy|800-878-295|
|Japan|0800-170-5464|
|Netherlands|0-800-022-2961|
|New Zealand|0800-003210|
|South Africa|0-800-980-818|
|United Kingdom|0800-520-0439|



## Contacting Technical Support 

The Rocket Community is the primary method of obtaining support. If you have current support and maintenance agreements with Rocket Software, you can access the Rocket Community and report a problem, download an update, or read answers to FAQs. To log in to the Rocket Community or to request a Rocket Community account, go to www.rocketsoftware.com/support. 

In addition to using the Rocket Community to obtain support, you can use one of the telephone numbers that are listed above or send an email to support@rocketsoftware.com. 

3 

## Contents 

Notices...................................................................................................................................................................................2 Corporate information......................................................................................................................................................... 3 Chapter 1: MVX DevOps Overview....................................................................................................................................... 5 MVX DevOps System Requirements........................................................................................................................ 5 Chapter 2: MVX DevOps Installation Guide.........................................................................................................................6 Installing the Docker Desktop and the MVX DevOps docker image...................................................................... 6 Security......................................................................................................................................................................7 Recommended Architecture........................................................................................................................ 7 SSL................................................................................................................................................................. 8 Uninstalling the MVX DevOps container................................................................................................................. 9 Chapter 3: MVX DevOps User Guide.................................................................................................................................. 10 Signing-in.................................................................................................................................................................10 Changing the container's MVX user password......................................................................................... 10 Account Setup.........................................................................................................................................................11 Adding your Amazon Web Services account............................................................................................ 11 Adding your Rocket Business Connect account.......................................................................................12 Provisioning.............................................................................................................................................................12 Provisioning the MultiValue Application Platform – Developer Edition..................................................13 Deprovisioning the MultiValue Application Platform – Developer Edition............................................. 14 

4 

## Chapter 1: MVX DevOps Overview 

Rocket MultiValue Experience DevOps (MVX DevOps) is a browser-based tool that facilitates the development, operations and management of MV Application Servers. 

This minimal viable product offering of MVX DevOps provides self-service provisioning of the MultiValue Application Platform – Developer Edition, specifically within the Amazon Web Services (AWS) environment. MVX DevOps also connects to Rocket Business Connect (RBC) to automatically manage entitlement of the provisioned instances. 

## **Licensing** 

Please review the EULAs, which are in the following directories in the container image: 

- /opt/rocketsoft/MVX_DevOps_010.txt 

- /opt/rocketsoft/Embedded License MVX_DevOps_010.docx 

These sections provide instructions for information on preparing your system for, installing, configuring, and using the MVX DevOps experience: 

- MVX DevOps System Requirements 

- MVX DevOps Installation Guide 

- MVX DevOps User Guide 

## MVX DevOps System Requirements 

Before you install and configure MVX DevOps, ensure that your environment meets the following minimum hardware and software requirements. 

## Hardware Requirements 

The hardware requirements for MVX DevOps are: 

- At least 16 GB of available hard disk space 

## Software Requirements 

The software requirements for MVX DevOps are: 

- MVX DevOps 0.1.0 is delivered as a Docker image built on a CentOS 7 base image. Both the Docker Community edition and the Docker Enterprise edition are supported. 

- Docker must be run on one of several supported platforms (for example, Windows, Linux and MacOS). For the complete list of supported platforms, go to http://www.docker.com. 

## Browser Recommendation 

When logging on to the Rocket MVX DevOps Experience console, it is recommended that you use the Google Chrome browser. 

5 

## Chapter 2: MVX DevOps Installation Guide 

MVX DevOps can be installed on your local machine or in your AWS account. 

The following topics provide instructions and information on installing and uninstalling MVX DevOps using a Docker container, installing MVX DevOps as an Amazon Machine Image in your AWS account and setting up security for your MVX DevOps implementation. 

- Installing the Docker Desktop and the MVX DevOps docker image Complete these instructions to install the Docker Desktop and the MVX DevOps docker image. 

- Security It is important to understand and follow the recommended network architecture. 

- Uninstalling the MVX DevOps container 

Complete these instructions to uninstall the MVX DevOps container. 

## Installing the Docker Desktop and the MVX DevOps docker image 

Complete these instructions to install the Docker Desktop and the MVX DevOps docker image. 

Review the MVX DevOps System Requirements before installing the image. 

Docker is a container platform provider. Containers allow an application or its services and configurations to be packaged as a container image. This containerized application can then be tested as a unit and deployed as an image instance to the OS. 

## Procedure 

1. Download the Docker Desktop installer from https://www.docker.com/ and then run the downloaded file to install the Docker Desktop. When the installation completes, start the Docker Desktop. 

2. Download the MVX DevOps docker image ( `mvx-docker.tar.gz` ) file from RBC to a temporary location (for example, `C:\temp` or `/tmp` ). 

3. Open a command window and navigate to the temporary directory where you downloaded the Docker image. 

4. Run the `docker load -i mvx-docker.tar.gz` command to load the MVX DevOps docker image into Docker. 

5. Run the `docker run -id -p 8544 --name mvx-mvp rocketsoft/mvx:0.1.0` command to start an MVX DevOps container. 

6. Run the `docker container port mvx-mvp` command to return the mapped-to host port that you will enter in a browser to run MVX DevOps. 

The port number will be the last five digits in the returned string. For example: 

- `>docker container port mvx-mvp 8544/tcp -> 0.0.0.0:` _`nnnnn`_ 

where _nnnnn_ is the port number. 

See Signing-in for instructions logging on to the Rocket MV DevOps Experience console. 

**Parent topic:** MVX DevOps Installation Guide 

6 

Security 

## Security 

It is important to understand and follow the recommended network architecture. 

In this section we present information on proper network architecture as it applies to AWS security groups, creating MV Rocket Community Edition instances, and SSL authentication. 

- Recommended Architecture 

- The network architecture described here is the recommended network setup for MVX DevOps. 

- • SSL 

   - MVX DevOps ships with a self-signed certificate to protect traffic from the browser to the MVX DevOps UI Server. 

**Parent topic:** MVX DevOps Installation Guide 

## Recommended Architecture 

The network architecture described here is the recommended network setup for MVX DevOps. 

## Setting up AWS security groups 

MVX DevOps is distributed as a docker container and can be deployed on machines that reside inside your Amazon Virtual Private Cloud (VPC) (https://aws.amazon.com/vpc/), or from within your onpremise network. 

MVX DevOps provisions MV Data Server instances to your Amazon VPC. Each provisioned MV Data Server instance listens for administrative commands from MVX DevOps on an MV Admin port (port 8383). You should restrict the MV Admin API of the provisioned MV Data Server instance to communicate only with the MVX DevOps server. AWS Security Groups provide one avenue for accomplishing this (https://docs.aws.amazon.com/vpc/latest/userguide/VPC_SecurityGroups.html). 

The recommended setup for running MVX DevOps is to run it within the same Amazon VPC and subnet as the provisioned MV Data server instances, the MV Developer Edition in the case of the MVP. This makes it easy to limit communication to the MV Admin port of deployed instances to only the MVX DevOps server. 

**==> picture [409 x 210] intentionally omitted <==**

7 

Chapter 2: MVX DevOps Installation Guide 

The AWS Security group for the AWS instance that has the MVX DevOps container installed inside a user's AWS account should have a rule that opens a port that is mapped to the https 8544 port of the container to IP addresses that will run the MVX DevOps console. This communication channel is secured by SSL via a self-signed certificate that ships with MVX DevOps. The MVX DevOps container should be protected by a security group that allows traffic to the Web server that serves the MVX DevOps user interface. This port is mapped by the Docker runtime, and can be found by running the `docker container port` command as described in Signing-in. 

In order to use an instance created by MVX DevOps and to try using the MVoovies application, a user must create a security group in the same subnet where the instance is located and specify that Security Group when provisioning the instance through the MVX DevOps browser-based console. 

The security group should have the following ports opened: 

|**Port**|**Description**|
|---|---|
|22 SSH port|This port is secured. It is protected by an SSH<br>key and can be opened to any IP that has an SSH<br>client intended to connect to the instance. The<br>SSH key should be loaded on all SSH clients,<br>either in`.pem`format,`.ppk`format or both<br>(depending on the type of SSH client).|
|8383 MV Database Administration port|This port is not secured. It should be opened<br>only to the machine running the MVX DevOps<br>container.|
|7870 MV BASIC Subroutine call port|This port is not secured. It should be opened to<br>any IP that could contain middleware through<br>which BASIC subroutines could be called.|
|7171 MVIS Rest port|This port is not secured. It should be opened<br>to any IP that could contain any client web<br>application that uses MVIS REST.|
|7077 MVIS Admin port|This port is not secured. It should be opened to<br>any IP that could run the MVIS Web Admin UI.|



Other ports can be opened to client IP addresses as needed. For example, if a user employs direct UO, port 31438 should be opened on a created instance. For telnet, port 23 should be opened. 

## Creating MV Developer Edition instances 

Provisioned MV Developer Edition instances can optionally be assigned public IP addresses. Doing so will allow IP addresses from outside AWS to access to the instance. You should use AWS Security Groups to limit access to the instance’s ports (described above) to trusted IP addresses. 

## **Parent topic:** Security 

## SSL 

MVX DevOps ships with a self-signed certificate to protect traffic from the browser to the MVX DevOps UI Server. 

Note that because it is a self-signed certificate, the browser will display a warning when first connecting to the MVX DevOps UI Server. 

## **Parent topic:** Security 

8 

Uninstalling the MVX DevOps container 

## Uninstalling the MVX DevOps container 

Complete these instructions to uninstall the MVX DevOps container. 

## Procedure 

1. Open a command window and navigate to the directory where you installed the image. 

2. Run the `docker stop mvx-mvp` command to stop the running MVX DevOps image in Docker. 

3. Run the `docker rm mvx-mvp` command to remove the MVX DevOps container from Docker. 

4. Run the `docker images -a` command to return the MVX DevOps image ID. 

5. Run the `docker rmi` _`image`_ command where _image_ is the image ID returned in the step above to remove the MVX DevOps image. 

**Parent topic:** MVX DevOps Installation Guide 

9 

## Chapter 3: MVX DevOps User Guide 

This user guide discusses all the information you need to provision a new instance of the Rocket MultiValue Application Platform – Developer Edition. 

Use this section to learn how to sign into the MVX DevOps Experience console, change your container's MVX password, add your AWS and RBC accounts and provision and deprovision an instance of the Rocket MultiValue Application Platform – Developer Edition. 

- Signing-in 

   - Local operating system users can log into the Rocket MV DevOps Experience console when running in a container with the default username of _mvx_ and the default password of _mvx_ . 

- Account Setup 

   - This section presents instructions for setting up your AWS and RBC accounts in the MVX DevOps Experience console. 

- Provisioning This section describes how to provision and deprovision an instance of the Rocket MultiValue Application Platform – Developer Edition. 

## Signing-in 

Local operating system users can log into the Rocket MV DevOps Experience console when running in a container with the default username of _mvx_ and the default password of _mvx_ . 

## Procedure 

1. From the command line, run the `docker container port mvx-mvp` command to return the mvx-mvp port number. 

The port number will be the last five digits in the returned string. For example: 

`>docker container port mvx-mvp 8544/tcp -> 0.0.0.0:` _`nnnnn`_ where _nnnnn_ is the port number. 

2. Open a browser and type https://localhost: _nnnnn_ in the address bar where _nnnnn_ is the port number returned in the step above. This will open the log on screen. 

**Note:** A security warning will display in your browser because MVX by default uses a selfsigned certificate. 

3. Enter the default username (mvx) and password (mvx). 

**Tip:** You can change the container's MVX user password. See Changing the container's MVX user password for more information. 

**Parent topic:** MVX DevOps User Guide 

## Changing the container's MVX user password 

You can change the container's MVX user password. 

10 

Account Setup 

The default MVX user password for the container is _mvx_ . 

## Procedure 

1. Run the `docker run -id -p 8544 --name mvx-mvp rocketsoft/mvx:0.1.0` command to start the mvx-mvp container if it is not already running. 

2. Run the `docker ps` command to confirm that the container is running. 

3. Run the `docker exec -it mvx-mvp /bin/bash` command to start an interactive shell into the mvx-mvp container. 

4. Run the `passwd mvx` command to change the password for the mxv user. 

**Tip:** Use the `useradd` and `userdel` commands to add or delete users. 

5. Run the `exit` command to exit the interactive shell to the container (however leaving the container itself running). 

6. From the host (outside of the interactive shell), run the `docker commit mvx-mvp` _`my-mvx`_ command, where _my-mvx_ is the name of your new image with the password change in place. 

7. Run the `docker images` _`my-mvx`_ command to verify that the new docker image has been created. 

8. Run the `docker stop mvx-mvp` command to stop the running container. 

9. Run the `docker run -id -p 8544 --name` _`my-mvx-mvp my-mvx`_ command where _mymvx-mvp_ is the new name of the for the running container and _my-mvx_ is the new name for the saved image to run the new container image. 

10. Run the `docker ps` command to verify that the new container is running. 

11. Log into the Rocket MV DevOps Experience console with your new password. 

**Note:** The port for MVX may have changed for the new container, so be sure to follow the procedure in Signing-in to get the port number where MVX is running. 

## Account Setup 

This section presents instructions for setting up your AWS and RBC accounts in the MVX DevOps Experience console. 

Both setups are required before you can provision an instance of the MultiValue Application Platform – Developer Edition. 

- Adding your Amazon Web Services account Complete these instructions to add your Amazon Web Services (AWS) account. 

- Adding your Rocket Business Connect account 

Complete these instructions to add your Rocket Business Connect (RBC) account. 

**Parent topic:** MVX DevOps User Guide 

## Adding your Amazon Web Services account 

Complete these instructions to add your Amazon Web Services (AWS) account. 

11 

Chapter 3: MVX DevOps User Guide 

To add your AWS account, you will need to provide your Access and Secret keys. If you don't have access to these keys, you will need to obtain them from your AWS system administrator. 

## Procedure 

1. Select **Account Settings** from the Rocket MV DevOps Experience console. 

2. Select **Amazon Web Services** from the **Add account** drop-down. 

3. Type your **Account ID or alias** , your **IAM user name** , your **Access key** and your **Secret key** in the Amazon Web Services account screen and then click the **Authenticate** button. 

**Note:** If you don't know your Access or Secret keys, contact the AWS administrator at your organization for assistance. 

4. Click **Save** . 

Your AWS account is added and its tile displays in the Account Settings screen. 

**Parent topic:** Account Setup 

## Adding your Rocket Business Connect account 

Complete these instructions to add your Rocket Business Connect (RBC) account. 

An RBC account is required to provision an instance of the MultiValue Application Platform – Developer Edition. Contact your Rocket representative to obtain your RBC account and the required credentials to add your account to the Rocket MVX DevOps Experience. 

## Procedure 

1. Select **Account Settings** from the Rocket MV DevOps Experience console. 

2. Select **Rocket Business Connect** from the **Add account** drop-down. 

3. Type your **RBC ID** (your email address associated to your RBC account) and your **Password** in the Add Rocket Business Connect account screen and then click the **Authenticate** button. 

4. Select the licensed customer ID from the **Licensed customer ID** drop-down. 

5. Click **Save** . 

Your RBC account is added and its tile displays in the Account Settings screen. 

**Parent topic:** Account Setup 

## Provisioning 

This section describes how to provision and deprovision an instance of the Rocket MultiValue Application Platform – Developer Edition. 

Before you can provision an instance of MultiValue Application Platform – Developer Edition, you must add your AWS and RBC accounts to the MVX DevOps Experience console. See Account Setup for more information. 

- Provisioning the MultiValue Application Platform – Developer Edition Complete these instructions to provision a new instance of the MultiValue Application Platform – Developer Edition. 

- Deprovisioning the MultiValue Application Platform – Developer Edition 

12 

Provisioning the MultiValue Application Platform – Developer Edition 

Complete these instructions to deprovision a new instance of the MultiValue Application Platform – Developer Edition. 

**Parent topic:** MVX DevOps User Guide 

## Provisioning the MultiValue Application Platform – Developer Edition 

Complete these instructions to provision a new instance of the MultiValue Application Platform – Developer Edition. 

The MV Developer Edition AMI is a full stack solution comprised of the Universe 12.1.2 Community Edition and the MVIS 1.2.1 Community Edition along with an example application, MVoovies (web and mobile application w/ RESTful services), that makes it easy to explore our latest MultiValue application server and modern tooling. While we will be including additional MV products and tools for provisioning via MVX DevOps in the GA release, the MV Developer Edition is currently the only MV product offering that can be provisioned using the MVX DevOps MVP. 

Before you can provision a new instance, you must add your RBC account and AWS account to your account settings. See Adding your Rocket Business Connect account and Adding your Amazon Web Services account for instructions. 

## Procedure 

1. Select **Instances** from the MVX DevOps Experience console. 

2. Click the **Provision a New Instance** button. 

3. From the **MV Config** tab in the Provision instance wizard, do the following: 

   - Select **MV Developer Edition** from the **Select option** drop-down. 

   - Type a name for the new instance in the **Name** text box. 

   - Select the appropriate purpose for your new instance from the **Purpose** drop-down. 

   - To grant an additional end user access to this instance, click the **Select** link, select a user from the **Select end user ID** list and then click **Continue** . 

4. Click **Next** . 

5. From the **Cloud Setup** tab, do the following: 

   - Select the size of your AWS instance for deploying your data server ( **Small** , **Medium** , **Large** or **X-Large** ) from the **Instance type** drop-down. 

   - Select the AWS region where this instance will be deployed from the **Region** drop-down. It is recommended that you select the region closest to your location. 

   - Select the Virtual Private Cloud (VPC) and the Subnet you previously configured in AWS from the **VPC** and **Subnet** drop-downs. 

   - Note that the volume is fixed and cannot be changed. 

   - Select the security group you previously configured in AWS from the **Security group** dropdown. 

   - Select the Key pair you previously configured in AWS from the **Key pair** drop-down. 

   - Select whether to generate a public IP from the **Public IP** toggle. 

6. Click **Next** . 

7. From the **Confirmation** tab, confirm your configuration settings and click **Provision** to provision the new instance. 

Your new instance is provisioned and its tile displays in the Instances screen. 

## **Parent topic:** Provisioning 

13 

Chapter 3: MVX DevOps User Guide 

## Deprovisioning the MultiValue Application Platform – Developer Edition 

Complete these instructions to deprovision a new instance of the MultiValue Application Platform – Developer Edition. 

## Procedure 

1. Select **Instances** from the MVX DevOps Experience console. 

2. Click the menu icon in the top right of the tile representing the instance you want to deprovision and select **Deprovision** . 

The specified instance is deprovisioned. 

## **Parent topic:** Provisioning 

14 

