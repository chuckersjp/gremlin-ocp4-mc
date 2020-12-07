# gremlin-ocp4-mc
OpenShift 4 Machine Config for Gremlin Chaos Engineering Platform

# What is this
Gremlin Chaos Engineering Platform (https://www.gremlin.com/) is a way to help
test your Kubernetes cluster to determine its resiliance by doing nasty things
to it.

Red Hat® OpenShift® is a hybrid cloud, enterprise Kubernetes
application platform.  The current release is OpenShift Container Platform 4.x (OCP 4.x)

Gremlin requires adding a few SELinux modules to each of your cluster nodes
as detailed here: https://www.gremlin.com/docs/infrastructure-layer/install-openshift4/
Doing this by hand is a bit onerous for any reasonably large clusters.
Additionally, OCP 4.x recommends using Machine Configs to make node changes
https://docs.openshift.com/container-platform/4.6/post_installation_configuration/machine-configuration-tasks.html

This project is to create a usuable Machine Config based on the required settings.

# How it does it
This repo contains a templated machine config.  This template is modified in the designated location
by taking the base64 encoded SELinux modules required found at 

https://github.com/gremlin/selinux-policies/blob/master/policies/gremlin-openshift4.cil

This is done as a straight cut and paste of the results of the following commands:

`curl https://github.com/gremlin/selinux-policies/blob/master/policies/gremlin-openshift4.cil | base64 -w0`

# Support
None.  ;-)

This isn't officially supported by Red Hat nor Gremlin (unless either wants to take it over.)  Use at
your own risk.
