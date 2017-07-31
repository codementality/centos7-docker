# centos7-docker
## CentOS/7 with Docker, Git, VIM and Docker Compose

The attached Vagrantfile builds a Centos/7 image for Virtualbox.  This image starts with the base Centos/7 image and adds:

* git
* vim
* wget
* Docker Community Edition, with prerequisites
* Docker Compose, version 1.15

The three last lines compress the size of the image, removes the bash history, reclaims disk space and exits the VM.

To generate a box, execute the following after the provisioning script exits the VM:

```
vagrant package --output mynew.box
```
A prebuilt image from this Vagrantfile for Virtualbox can be found at:

```
https://app.vagrantup.com/codementality/boxes/centos7-docker
```

To use the prebuilt image, add the following to your Vagrantfile:
```
Vagrant.configure("2") do |config|
  config.vm.box = "codementality/centos7-docker"
  config.vm.box_version = "1.2"
end
```
