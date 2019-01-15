## Debian Stretch

Made for [netPI](https://www.netiot.com/netpi/), the Raspberry Pi 3B Architecture based industrial suited Open Edge Connectivity Ecosystem

### Debian Stretch with SSH and user root

The image provided hereunder deploys a container with installed plain Debian Stretch.

Base of this image builds a tagged version of [debian:stretch](https://hub.docker.com/r/resin/armv7hf-debian/tags/) with enabled [SSH](https://en.wikipedia.org/wiki/Secure_Shell) and created user 'root'.

#### Container prerequisites

##### Port mapping

For remote login to the container across SSH the container's SSH port `22` needs to be mapped to any free netPI host port.

#### Getting started

STEP 1. Open netPI's landing page under `https://<netpi's ip address>`.

STEP 2. Click the Docker tile to open the [Portainer.io](http://portainer.io/) Docker management user interface.

STEP 3. Enter the following parameters under **Containers > Add Container**

* **Image**: `hilschernetpi/netpi-debian-stretch`

* **Port mapping**: `Host "22" (any unused one) -> Container "22"` 

* **Restart policy"** : `always`

STEP 4. Press the button **Actions > Start/Deploy container**

Pulling the image may take a while (5-10mins). Sometimes it takes so long that a time out is indicated. In this case repeat the **Actions > Start/Deploy container** action.

#### Accessing

The container starts the SSH service automatically when started.

Login to it with an SSH client such as [putty](http://www.putty.org/) using netPI's IP address at your mapped port. Use the credentials `root` as user and `root` as password when asked and you are logged in as root user `root`.

Use Debian shell commands as usual.

#### Automated build

The project complies with the scripting based [Dockerfile](https://docs.docker.com/engine/reference/builder/) method to build the image output file. Using this method is a precondition for an [automated](https://docs.docker.com/docker-hub/builds/) web based build process on DockerHub platform.

DockerHub web platform is x86 CPU based, but an ARM CPU coded output file is needed for Raspberry systems. This is why the Dockerfile includes the [balena.io](https://balena.io/blog/building-arm-containers-on-any-x86-machine-even-dockerhub/) steps.

#### License

View the license information for the software in the project. As with all Docker images, these likely also contain other software which may be under other licenses (such as Bash, etc from the base distribution, along with any direct or indirect dependencies of the primary software being contained).
As for any pre-built image usage, it is the image user's responsibility to ensure that any use of this image complies with any relevant licenses for all software contained within.

[![N|Solid](http://www.hilscher.com/fileadmin/templates/doctima_2013/resources/Images/logo_hilscher.png)](http://www.hilscher.com)  Hilscher Gesellschaft fuer Systemautomation mbH  www.hilscher.com
