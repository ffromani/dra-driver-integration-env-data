minikube ISO image with SRIOV support
=====================================

# Summary

The official minikube 1.38 image does not support SRIOV device injection.
There are non-invasive workarounds implemented in the DRA driver integration env, but
unfortunately we need changes to the minikube iso image to
- enable the intel IGB driver, necessary for SRIOV emulation
- add kernel support for SRIOV/ PCI IOV, disabled by default

[minikube fork](https://github.com/ffromani/minikube/tree/sriov-support) with changes (WIP, PR pending)
the patches against minikube @ f75080379 are available here. They are very simple and they should
apple against 1.38.

pre-built ISO image with its sha256sum is available. Use it [as documented in minikube](https://minikube.sigs.k8s.io/docs/contrib/building/iso/)
The DRA driver integration env has automation to make use of this custom image.

# Large Files

this repo uses [git LFS](https://git-lfs.com/) to track the iso content.

# License

the custom iso image provided here is released under the same license as the parent minikube iso image.
Please refer to the minikube project for details.
