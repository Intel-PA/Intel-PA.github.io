#Setup a single compute node in HPC

1. Install Ubuntu from USB, no proprietary drivers, complete wipe of current install
2. Login to GUI, install Nvidia drivers from update centre
3. install curl, vim-gtk3
4. Follow steps for installing [container toolkit](https://docs.nvidia.com/datacenter/cloud-native/container-toolkit/latest/install-guide.html)
5. Enable [CDI support](https://docs.nvidia.com/datacenter/cloud-native/container-toolkit/latest/cdi-support.html)
6. Install Podman
	* sudo apt update && sudo apt upgrade -y
	* . /etc/os-release
	* echo "deb https://download.opensuse.org/repositories/devel:/kubic:/libcontainers:/stable/xUbuntu_${VERSION_ID}/ /" | sudo tee /etc/apt/sources.list.d/devel:kubic:libcontainers:stable.list
	* curl -L "https://download.opensuse.org/repositories/devel:/kubic:/libcontainers:/stable/xUbuntu_${VERSION_ID}/Release.key" | sudo apt-key add -
	* sudo apt-get update
	* sudo apt-get -y upgrade
	* sudo apt-get -y install podman
	* enable insecure image pulls by editing `etc/containers/registries.conf`:
		```
		unqualified-search-registries = ["intelpa-ops", "docker.io", "quay.io"]
		[[registry]]
		location = "intelpa-ops:5000"
		insecure = true
		```
7. Add the following to `/etc/nvidia-container-runtime/config.toml` :
	[nvidia-container-cli]
	no-cgroups = true
8. Add the following to `/usr/share/containers/containers.conf` :
	[engine.runtimes]
	nvidia = ["/usr/bin/nvidia-container-runtime"]
9. Confirm podman gpu works with the following:
	* Reboot
	* podman run --rm --runtime nvidia nvidia/cuda:11.0.3-base-ubuntu20.04 nvidia-smi
10. Install timeshift and make checkpoint: nvidia-smi works with podman run
11. Install openssh-server and enable
12. [TODO] Install BU policy compliant passwords
13. [TODO] Install BU policy compliant monitoring software


