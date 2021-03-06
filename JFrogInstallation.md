## JFrog Installation Steps:

To get started with installing JFrog Artifactory, follow the steps below:

### Step 1: Prepare Ubuntu
Before installing packages on Ubuntu, you must first update the server. To do that, run the commands below:

```
sudo apt update
sudo apt dist-upgrade
sudo apt autoremove
```
Running the commands above will update the remove obsolete packages from your system. It’s also a good to reboot the server after running the above commands.

### Step 2: Install OpenJDK 8

To properly use JFrog Artifactory, you will need Java installed. First, download the Java 8 Development Kit: either the official Oracle JDK or Open JDK

For this tutorial, we’re going to be install OpenJDK.

To do that, run the commands below:
```
sudo apt update
sudo apt-get install openjdk-8-jdk openjdk-8-doc
```
After installing Java, you can verify it by running the commands below:
```
java -version
```

It should output something similar as shown below:

Output:
```
openjdk version "1.8.0_242"
OpenJDK Runtime Environment (build 1.8.0_242-8u242-b08-0ubuntu3~18.04-b08)
OpenJDK 64-Bit Server VM (build 25.242-b08, mixed mode)
```
Now that you have updated and installed Java, continue below to installing JFrog.

### Step 3: Download and Install JFrog Artifactory
The quickest and easiest way to get JFrog installed is via a APT repository. Installing JFrog from the repository will allow you to always get the latest updates as they’re released.

To install, follow the steps below:

First, install wget and other packages if you don’t already have them installed.
```
sudo apt install wget software-properties-common
```

Then run the commands below to add the repository key and file to Ubuntu.
```
wget -qO - https://api.bintray.com/orgs/jfrog/keys/gpg/public.key | apt-key add -
sudo add-apt-repository "deb [arch=amd64] https://jfrog.bintray.com/artifactory-debs $(lsb_release -cs) main"
```
When you’re done, run the commands below to update Ubuntu and install JFrog Artifactory.
```
sudo apt update
sudo apt install jfrog-artifactory-oss
```
After installing, the commands below can be used to stop, start and enable JFrog’s services.
```
systemctl stop artifactory.service
systemctl start artifactory.service
systemctl enable artifactory.service
```
To check the service status, run the commands below:
```
systemctl status artifactory.service
```

It should output similar lines as shown below:
<image src="images/Jfrog.jpg"/>

Step 4: Access Artifactory Portal
When you’re done installing, open your web browser and browser to the server’s hostname or IP address as shown below:

http://localhost:8081/artifactory/

You should see the login portal similar to the one below:

<image src="images/JfrogLogin.jpg"/>

Login with Username:  admin and Password: password

You’ll be prompted to change the temporary password above. When you do, you’ll able to start setting up your environment.

Login to Jfrog Dashboard->Administration->Repositories->Add Repositories->Local Repositories->Maven->

<image src="images/JFrogRepo.jpg"/>
