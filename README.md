# Sample Stack

This repository serves as a very simple example of a Crossplane Stack.
Stacks enable the ability to extend Crossplane with new functionality, for example new CRDs and controllers to manage them.
More details about the design and functionality of Stacks can be found in the [design document](https://github.com/crossplaneio/crossplane/blob/master/design/design-doc-stacks.md).

## Stack Package

The contents of this repository have been built, packaged, and published to the `crossplane/sample-stack` repository on [Docker Hub](https://cloud.docker.com/u/crossplane/repository/docker/crossplane/sample-stack).

## Install

You will need to [install and have Crossplane running](https://crossplane.io/docs/master/quick-start.html) in a Kubernetes cluster before installing this Stack.

To install this Stack with `kubectl` from the published Docker Hub image:

```console
cat <<EOF | kubectl apply -f -
apiVersion: stacks.crossplane.io/v1alpha1
kind: StackInstall
metadata:
  name: sample-stack-from-package
spec:
  source: registry.hub.docker.com
  package: crossplane/sample-stack
EOF
```
