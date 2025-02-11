# Certified Kubernetes Security Specialist Exam Preparation Guide

[![Check Markdown links](https://github.com/Evalle/CKS/actions/workflows/action.yml/badge.svg)](https://github.com/Evalle/CKS/actions/workflows/action.yml)

This guide is intended to be a point of knowledge for everyone who wants to pass Certified Kubernetes Security Specialist (CKS) Exam. 
The main idea is to provide links to every topic in each domain. Preference will always be the official documentation but feel free to add other useful links.

**The Exam itself will be available in November 2020**

## Introduction (Read carefully)

A Certified Kubernetes Security Specialist is an accomplished Kubernetes practitioner (**as evidenced by holding the CKA credential**) who has demonstrated competence on a broad range of best practices for securing container-based applications and Kubernetes platforms during build, deployment and runtime.

Certified Kubernetes Security Specialist (CKS) candidates must have taken and passed the [Certified Kubernetes Administrator (CKA)](https://www.cncf.io/certification/cka/) exam prior to attempting the CKS exam. The CKS may be scheduled but not taken until CKA certification has been achieved.

## Exam Details

This exam is an online, proctored, performance-based test that requires solving multiple tasks from a command line running Kubernetes. Candidates have 2 hours to complete the tasks.

The exam is based on Kubernetes v1.20

Certified Kubernetes Security Specialist (CKS) candidates must have taken and passed the Certified Kubernetes Administrator (CKA) exam prior to attempting the CKS exam. The CKS may be scheduled but not taken until CKA certification has been achieved.


## Table of Contents

1. [Cluster Setup](https://github.com/Evalle/CKS/blob/master/README.md#Cluster-Setup)
1. [Cluster Hardening](https://github.com/Evalle/CKS/blob/master/README.md#Cluster-Hardening)
1. [System Hardening](https://github.com/Evalle/CKS/blob/master/README.md#System-Hardening)
1. [Minimize Microservice Vulerabilities](https://github.com/Evalle/CKS/blob/master/README.md#Minimize-Microservice-Vulnerabilities)
1. [Supply Chain Security](https://github.com/Evalle/CKS/blob/master/README.md#Supply-Chain-Security)
1. [Monitoring, Logging and Runtime Security](https://github.com/Evalle/CKS/blob/master/README.md#Monitoring-Logging-and-Runtime-Security)
1. [Useful Links](https://github.com/Evalle/CKS/blob/master/README.md#useful-links)

## Cluster Setup

- [Use Network security policies to restrict cluster level access](https://kubernetes.io/docs/concepts/services-networking/network-policies/)
- [Use CIS benchmark to review the security configuration of Kubernetes components (etcd, kubelet, kubedns, kubeapi)](https://github.com/aquasecurity/kube-bench)
- [Properly set up Ingress objects with security control](https://kubernetes.io/docs/concepts/services-networking/ingress/#tls)
- [Protect node metadata and endpoints](https://kubernetes.io/docs/tasks/administer-cluster/securing-a-cluster/#restricting-cloud-metadata-api-access)
- [Minimize use of, and access to, GUI elements](https://github.com/kubernetes/dashboard#getting-started)
- Verify platform binaries before deploying, use [md5 checks](https://www.tecmint.com/generate-verify-check-files-md5-checksum-linux/) against [official binaries](https://github.com/kubernetes/kubernetes/releases)

## Cluster Hardening

- [Restrict access to Kubernetes API](https://kubernetes.io/docs/reference/access-authn-authz/controlling-access/)
- [Use Role Based Access Controls to minimize exposure](https://kubernetes.io/docs/reference/access-authn-authz/rbac/)
- [Exercise caution in using service accounts e.g. disable defaults, minimize permissions on newly created ones](https://kubernetes.io/docs/reference/access-authn-authz/service-accounts-admin/)
- [Update Kubernetes frequently](https://kubernetes.io/docs/tasks/administer-cluster/kubeadm/kubeadm-upgrade/)

## System Hardening

- [Minimize host OS footprint (reduce attack surface)](https://blog.sonatype.com/kubesecops-kubernetes-security-practices-you-should-follow#:~:text=Reduce%20Kubernetes%20Attack%20Surfaces)
- Minimize IAM roles - [AWS](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles.html), [GCloud](https://cloud.google.com/storage/docs/access-control/iam-roles)
- [Minimize external access to the network](https://kubernetes.io/docs/concepts/services-networking/network-policies/)
- Appropriately use kernel hardening tools such as [AppArmor](https://gitlab.com/apparmor), [seccomp](https://kubernetes.io/docs/tutorials/clusters/seccomp/)

## Minimize Microservice Vulnerabilities

- Setup appropriate OS level security domains e.g. using [PSP](https://kubernetes.io/docs/concepts/policy/pod-security-policy/), [OPA](https://www.openpolicyagent.org/), [security contexts](https://kubernetes.io/docs/tasks/configure-pod-container/security-context/)
- [Manage Kubernetes secrets](https://kubernetes.io/docs/concepts/configuration/secret/)
- [Use container runtime sandboxes in multi-tenant environments](https://kubernetes.io/docs/concepts/containers/runtime-class/) (e.g. [gvisor](https://gvisor.dev/), [kata containers](https://katacontainers.io/))
- [Implement pod to pod encryption by use of mTLS](https://thenewstack.io/mutual-tls-microservices-encryption-for-service-mesh/)

## Supply Chain Security

- [Minimize base image footprint](https://docs.docker.com/develop/develop-images/dockerfile_best-practices/)
- [Secure your supply chain: whitelist allowed registries, sign and validate images](https://kubernetes.io/docs/reference/access-authn-authz/admission-controllers/#imagepolicywebhook)
- Use static analysis of user workloads (e.g.Kubernetes resources, Docker files) - [kubesec](https://kubesec.io/), [conftest](https://github.com/open-policy-agent/conftest)
- Scan images for known vulnerabilities ([clair](https://coreos.com/clair/docs/latest/), [trivy](https://github.com/aquasecurity/trivy))

## Monitoring Logging and Runtime Security 

- Perform behavioral analytics of syscall process and file activities at the host and container level to detect malicious activities - ([strace](https://strace.io/))
- Detect threats within physical infrastructure, apps, networks, data, users and workloads
- Detect all phases of attack regardless where it occurs and how it spreads
- Perform deep analytical investigation and identification of bad actors within environment
- [Ensure immutability of containers at runtime](https://gianarb.it/blog/container-security-immutability)
- [Use Audit Logs to monitor access](https://kubernetes.io/docs/tasks/debug-application-cluster/audit/)

## Useful Links

### Courses

- [Configuring and Managing Kubernetes Security](https://app.pluralsight.com/library/courses/configuring-managing-kubernetes-security/table-of-contents)
- [Kubernetes CKS 2020 Complete Course + Simulator (UDEMY)](https://www.udemy.com/course/certified-kubernetes-security-specialist/)

### Info

- [Exam info](https://training.linuxfoundation.org/certification/certified-kubernetes-security-specialist/?utm_source=lftraining&utm_medium=pr&utm_campaign=cks0720)
- [Exam Curriculum (v1.20)](https://github.com/cncf/curriculum/blob/master/CKS_Curriculum_%20v1.20.pdf)
