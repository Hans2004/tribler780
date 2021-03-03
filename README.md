# tribler780

This repository contains a yaml file that can be used to build tribler version 7.8.0 for snapcraft.

Here is how to build the snap on your own machine:

Create a KVM virtual machine with Ubuntu 18.04 install.

Ubuntu comes with the snap deamon installed as standard. But we need the snapcraft utility to create our own snaps from yaml files.

Install snapcraft on the virtual machine: sudo snap install snapcraft --classic

Install LXD: sudo snap install lxd sudo lxd init sudo usermod -a -G lxd ${USER} newgrp lxd

Create a directory for the source of the app to be snapped. Inside this directory create a snapcraft.yaml file Then type: snapcraft --use-lxd

If snapcraft succeeds, you can install the snap as follows: snap install --devmode --dangerous ./test-tribler_7.7.1_amd64.snap

And then you can run the snap with the command: test-tribler.tribler

NOTE: If the snapcraft command proceeds slowly or ends with an error concerning memory, you must delete old LXC containers: lxc list lxc delete [name of container]
