# Local Podman registry 

We provide a registry for basic deep learning images that should be compatible with the cluster's nvidia/cuda versions. This could be helpful if you need to rebuild a container but the original image has been taken down from its hosting site.


## Using the local registry

The endpoint for the registry is located at `intelpa-ops:5000`. Should you want to pull an image  called `image-name` from there to your workspace:
```bash
podman image pull intelpa-ops:5000/image-name:latest

```
Please note that the registry is read-only -- you are not allowed to push your own images to it.