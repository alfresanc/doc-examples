<!-- BEGIN MUNGE: GENERATED_TOC -->
# [v1.6.4](#v164)
- [Change / Instalation Name](#change-instalation-name)
	- [Date and Hour](#date-and-hour)
	- [Responsible Contact](#responsible-contact)
	- [Nissan Approbation](#nissan-approbation)
- [Affected Files](#affected-files)
- [Notable Changes to Existing Behavior](#notable-changes-to-existing-behavior)
	- [Code updates and Features](#major-updates-and-notable-features)
    - [Known Issues and Important Steps Before Upgrading](#known-issues-and-important-steps-before-upgrading)
	- [Deprecations](#deprecations)
	- [Experimental Features](#experimental-features-2)
	- [Required Database Modifications](#required-database-modifications)
	- [Views Modifications](#views-modifications)
- [Provisioning Procedure](#provisioning-procedure)
	- [External Dependency Version Information](#external-dependency-version-information)
	- [Rollback Procedures](#rollback-procedures)
  	- [Actions Required](#actions-required)

<!-- END MUNGE: GENERATED_TOC -->

<!-- NEW RELEASE NOTES ENTRY -->

## v1.6.4
[Documentation](https://docs.k8s.io) & [Examples](https://releases.k8s.io/release-1.6.3/examples)
### Change Description
Modificación de fuentes en Front de NRFM
### Date and Hour
21/05/17 21:00
### Responsible Contact
Eduardo Malfabon - Terán
### Nissan Approbation
Ana Migliano - NRFM
## Affected Files
filename | file path on this version
-------- | -------------------------
[kubernetes-client-darwin-386.tar.gz](https://dl.k8s.io/v1.6.4/kubernetes-client-darwin-386.tar.gz) | `/var/www/html/packages.json`
[kubernetes-client-darwin-amd64.tar.gz](https://dl.k8s.io/v1.6.4/kubernetes-client-darwin-amd64.tar.gz) | `/var/www/html/index.js`
## Notable Changes to Existing Behaviour
### Code updates and Features
* All communication is now over TLS
* Fix kubelet panic during disk eviction introduced in 1.6.3. ([#46049](https://github.com/kubernetes/kubernetes/pull/46049), [@enisoc](https://github.com/enisoc))
* Fix pods failing to start if they specify a file as a volume subPath to mount. ([#46046](https://github.com/kubernetes/kubernetes/pull/46046), [@enisoc](https://github.com/enisoc))
* [Role-based access control (RBAC)](https://kubernetes.io//docs/admin/authorization/rbac) has graduated to beta, and defines secure default roles for control plane, node, and controller components.
* The [`kubeadm` cluster bootstrap tool](https://kubernetes.io/docs/getting-started-guides/kubeadm/) has graduated to beta. Some highlights:
  * **WARNING:** A [known issue](https://github.com/kubernetes/kubernetes/issues/43815)
    in v1.6.0 causes `kubeadm init` to hang. Please use v1.6.1, which fixes the issue.
  * All communication is now over TLS
  * Authorization plugins can be installed by kubeadm, including the new default of RBAC
  * The bootstrap token system now allows token management and expiration
* Add image cache to fix the issue where kubelet hands when reporting the node
  status. ([#38375](https://github.com/kubernetes/kubernetes/pull/38375),
  [@Random-Liu](https://github.com/Random-Liu))
* Fix logic error in graceful deletion that caused pods not being able to
  be deleted. ([#37721](https://github.com/kubernetes/kubernetes/pull/37721),
  [@derekwaynecarr](https://github.com/derekwaynecarr))

### Known Issues and Important Steps Before Upgrading
Before updating to 1.6, you are strongly recommended to back up your etcd data.
Please consult the installation procedure you are using (kargo, kops, kube-up,
kube-aws, kubeadm etc) for specific advice.
### Deprecations
* The [`kubeadm` cluster bootstrap tool](https://kubernetes.io/docs/getting-started-guides/kubeadm/) has graduated to beta. Some highlights:
  * **WARNING:** A [known issue](https://github.com/kubernetes/kubernetes/issues/43815)
    in v1.6.0 causes `kubeadm init` to hang. Please use v1.6.1, which fixes the issue.

### Experimental Features
  * <strong>Significant scale improvements</strong>. Increased cluster scale by 400% to 1000 nodes with 30,000 pods per cluster.
Kubelet supports 100 pods per node with 4x reduced system overhead.
  * <strong>Simplified application deployment and management. </strong>
     * Dynamic Configuration (ConfigMap API in the core API group) enables application
configuration to be stored as a Kubernetes API object and pulled dynamically on
container startup, as an alternative to baking in command-line flags when a
container is built.

- using `application/vnd.kubernetes.protobuf` as the media storage type for 1.6 is default but not required
- the ability to rollback to etcd2 can be preserved by setting the storage media type flag on `kube-apiserver`

### Views Modifications
* DaemonSet now respects ControllerRef to avoid fighting over Pods. ([#42173](https://github.com/kubernetes/kubernetes/pull/42173), [@enisoc](https://github.com/enisoc))
* Make DaemonSet respect critical pods annotation when scheduling. ([#42028](https://github.com/kubernetes/kubernetes/pull/42028), [@janetkuo](https://github.com/janetkuo))
* Implement the update feature for DaemonSet. ([#41116](https://github.com/kubernetes/kubernetes/pull/41116), [@lukaszo](https://github.com/lukaszo))

## Provisioning Procedure
### External Dependency Version Information
**No dependencies version changes for this release**
### Rollback Procedures
**No special rollback procedures for this release**
### Actions Required
```
go build -o toc
```

  to continue to use `application/json` as the storage media type which can be changed to
  `application/vnd.kubernetes.protobuf` at a later time.

```
--storage-media-type application/json
```
<img src="docs/images/newgui.png" width="" alt="Dashboard UI screenshot showing cards that represent applications that run inside a cluster" title="Dashboard UI apps screen">

Rutas: `application/vnd.kubernetes.protobuf`
Comandos:
``` --storage-media-type application/json
```