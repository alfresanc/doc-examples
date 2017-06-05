<!-- BEGIN MUNGE: GENERATED_TOC -->
### [v1.6.4](#v164) (21/05/17 21:00)
- [Change / Instalation Name](change-instalation-name)
	- [Date and Hour](#date-and-hour)
	- [Responsible Contact](#responsible-contact)
	- [Nissan Approbation](#nissan-approbation)
- [Affected Files](#affected-files)
- [Notable Changes to Existing Behavior](#notable-changes-to-existing-behavior)
	- [Code updates and Deatures](#major-updates-and-notable-features)
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

# v1.6.4

[Documentation](https://docs.k8s.io) & [Examples](https://releases.k8s.io/release-1.6.3/examples)

### Modified Files

filename | file path on this version
-------- | -------------------------
[kubernetes-client-darwin-386.tar.gz](https://dl.k8s.io/v1.6.4/kubernetes-client-darwin-386.tar.gz) | `/var/www/html/packages.json`
[kubernetes-client-darwin-amd64.tar.gz](https://dl.k8s.io/v1.6.4/kubernetes-client-darwin-amd64.tar.gz) | `/var/www/html/index.js`

## Changelog since v1.6.3

### Other notable changes

* Fix kubelet panic during disk eviction introduced in 1.6.3. ([#46049](https://github.com/kubernetes/kubernetes/pull/46049), [@enisoc](https://github.com/enisoc))
* Fix pods failing to start if they specify a file as a volume subPath to mount. ([#46046](https://github.com/kubernetes/kubernetes/pull/46046), [@enisoc](https://github.com/enisoc))

## 1. Provisioning Procedure



### Action Required

```
go build -o toc
```
## WARNING: etcd backup strongly recommended

Before updating to 1.6, you are strongly recommended to back up your etcd data.
Please consult the installation procedure you are using (kargo, kops, kube-up,
kube-aws, kubeadm etc) for specific advice.

Backups are always a good precaution, particularly around upgrades, but this
upgrade has multiple known issues where the only remedy is to restore from
backup.

Also, please note:
- using `application/vnd.kubernetes.protobuf` as the media storage type for 1.6 is default but not required
- the ability to rollback to etcd2 can be preserved by setting the storage media type flag on `kube-apiserver`

  ```
  --storage-media-type application/json
  ```

  to continue to use `application/json` as the storage media type which can be changed to
  `application/vnd.kubernetes.protobuf` at a later time.

## Major updates and release themes
d v3, which is enabled by default.
* [Role-based access control (RBAC)](https://kubernetes.io//docs/admin/authorization/rbac) has graduated to beta, and defines secure default roles for control plane, node, and controller components.
* The [`kubeadm` cluster bootstrap tool](https://kubernetes.io/docs/getting-started-guides/kubeadm/) has graduated to beta. Some highlights:
  * **WARNING:** A [known issue](https://github.com/kubernetes/kubernetes/issues/43815)
    in v1.6.0 causes `kubeadm init` to hang. Please use v1.6.1, which fixes the issue.
  * All communication is now over TLS
  * Authorization plugins can be installed by kubeadm, including the new default of RBAC
  * The bootstrap token system now allows token management and expiration
* Various scheduling features have graduated to beta:
  * You can now use [multiple schedulers](https://kubernetes.io/docs/tutorials/clusters/multiple-schedulers/)
  * [Nodes](https://kubernetes.io/docs/concepts/configuration/assign-pod-node/#node-affinity-beta-feature) and [pods](https://kubernetes.io/docs/concepts/configuration/assign-pod-node/#inter-pod-affinity-and-anti-affinity-beta-feature) now support affinity and anti-affinity
  * Advanced scheduling can be performed with [taints and tolerations](https://kubernetes.io/docs/concepts/configuration/assign-pod-node/#taints-and-tolerations-beta-feature)
* You can now specify (per pod) how long a pod should stay bound to a node, when there is a node problem.
* DaemonSets [can now be updated by a rolling update](https://kubernetes.io/docs/tasks/manage-daemon/update-daemon-set).

### Certificates API
* Users of the alpha certificates API should delete v1alpha1 CSRs from the API before upgrading and recreate them as v1beta1 CSR after upgrading. ([#39772](https://github.com/kubernetes/kubernetes/pull/39772), [@mikedanese](https://github.com/mikedanese))

### Internal Storage Layer
* upgrade to etcd3 prior to upgrading to 1.6 **OR** explicitly specify `--storage-backend=etcd2 --storage-media-type=application/json` when starting the apiserver

### Node Components
* **Kubelet with the Docker-CRI implementation**
  * It is not compatible with CNI plugins that do not conform to the
    [error handling behavior in the spec](https://github.com/containernetworking/cni/blob/master/SPEC.md#network-configuration-list-error-handling).
    The plugins are being updated to resolve this issue ([#43488](https://github.com/kubernetes/kubernetes/issues/43488)).
    You can disable CRI explicitly (`--enable-cri=false`) as a
    temporary workaround.
      * The standard `bridge` plugin have been validated to interoperate with
         the new CRI + CNI code path.
      * If you are using plugins other than `bridge`, make sure you have
        updated custom plugins to the latest version that is compatible.

## Deprecations
* Remove extensions/v1beta1 Jobs resource, and job/v1beta1 generator. ([#38614](https://github.com/kubernetes/kubernetes/pull/38614), [@soltysh](https://github.com/soltysh))
* `federation/deploy/deploy.sh` was an interim solution introduced in Kubernetes v1.4 to simplify the federation control plane deployment experience. Now that we have `kubefed`, we are deprecating `deploy.sh` scripts. ([#38902](https://github.com/kubernetes/kubernetes/pull/38902), [@madhusudancs](https://github.com/madhusudancs))

### DaemonSet
* DaemonSet now respects ControllerRef to avoid fighting over Pods. ([#42173](https://github.com/kubernetes/kubernetes/pull/42173), [@enisoc](https://github.com/enisoc))
* Make DaemonSet respect critical pods annotation when scheduling. ([#42028](https://github.com/kubernetes/kubernetes/pull/42028), [@janetkuo](https://github.com/janetkuo))
* Implement the update feature for DaemonSet. ([#41116](https://github.com/kubernetes/kubernetes/pull/41116), [@lukaszo](https://github.com/lukaszo))

#### Bug fixes
* Add image cache to fix the issue where kubelet hands when reporting the node
  status. ([#38375](https://github.com/kubernetes/kubernetes/pull/38375),
  [@Random-Liu](https://github.com/Random-Liu))
* Fix logic error in graceful deletion that caused pods not being able to
  be deleted. ([#37721](https://github.com/kubernetes/kubernetes/pull/37721),
  [@derekwaynecarr](https://github.com/derekwaynecarr))

### Previous Releases Included in v1.6.0
- [v1.6.0-rc.1](https://github.com/kubernetes/kubernetes/blob/master/CHANGELOG.md#v160-rc1)
- [v1.6.0-beta.4](https://github.com/kubernetes/kubernetes/blob/master/CHANGELOG.md#v160-beta4)

**No notable changes for this release**

  * <strong>Significant scale improvements</strong>. Increased cluster scale by 400% to 1000 nodes with 30,000 pods per cluster.
Kubelet supports 100 pods per node with 4x reduced system overhead.
  * <strong>Simplified application deployment and management. </strong>
     * Dynamic Configuration (ConfigMap API in the core API group) enables application
configuration to be stored as a Kubernetes API object and pulled dynamically on
container startup, as an alternative to baking in command-line flags when a
container is built.

<img src="docs/images/newgui.png" width="" alt="Dashboard UI screenshot showing cards that represent applications that run inside a cluster" title="Dashboard UI apps screen">
