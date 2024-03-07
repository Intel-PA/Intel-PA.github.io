---
layout: page
title: gpu-driver-installation
permalink: /static/docs/gpu-driver-installation/
---

[**<-back**](/static/docs)  

# 1. To install nvidia container runtime:
```bash
export distribution=$(. /etc/os-release;echo $ID$VERSION_ID)
curl -s -L https://nvidia.github.io/nvidia-docker/gpgkey | sudo apt-key add -
curl -s -L https://nvidia.github.io/nvidia-docker/$distribution/nvidia-docker.list | sudo tee /etc/apt/sources.list.d/nvidia-docker.listsudo apt-get update
sudo apt update
sudo apt install nvidia-container-runtime
```

# 2. To upgrade nvidia drivers:
```bash
sudo apt-get remove --purge nvidia-* -y
sudo apt autoremove
sudo reboot
```

# 3. To install the nvidia-driver-xxx package from ppa:graphics-drivers/ppa:
```bash
sudo apt update && sudo apt upgrade -y
sudo add-apt-repository ppa:graphics-drivers/ppa -y
sudo apt update 
sudo apt install nvidia-driver-xxx -y  
sudo reboot
```

# 4. To install nvidia container toolkit:
Follow all steps in [https://docs.nvidia.com/datacenter/cloud-native/container-toolkit/latest/install-guide.html](https://docs.nvidia.com/datacenter/cloud-native/container-toolkit/latest/cdi-support.html)

# 5. To configure podman:
Follow all steps in [https://docs.nvidia.com/datacenter/cloud-native/container-toolkit/latest/cdi-support.html](https://docs.nvidia.com/datacenter/cloud-native/container-toolkit/latest/cdi-support.html)

Add the following to  `/etc/nvidia-container-runtime/config.toml`:
```bash
[nvidia-container-cli]
no-cgroups = true
```

Add the following to `/usr/share/containers/containers.conf`:
```bash
[engine.runtimes]
nvidia = ["/usr/bin/nvidia-container-runtime"]
```

