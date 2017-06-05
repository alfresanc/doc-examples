<!-- BEGIN MUNGE: GENERATED_TOC -->
- [v1.6.4](#v164) 13/05/17-21:00
  - [Modified files for v1.6.4](#downloads-for-v164)
  - [Changes to API / Connetions / Request](#changes-to-api-resources)
    - [Action Required](#action-required)
    - [Other notable changes](#other-notable-changes-1)
  - [Major updates and release themes](#major-updates-and-release-themes)
  - [Action Required](#action-required-3)
    - [Certificates API](#certificates-api)
    - [Cluster Autoscaler](#cluster-autoscaler)
    - [Deployment](#deployment)
  - [Notable Features](#notable-features)
    - [Autoscaling](#autoscaling)
    - [DaemonSet](#daemonset)
  - [Deprecations](#deprecations)
    - [Cluster Provisioning Scripts](#cluster-provisioning-scripts)
    - [kubeadm](#kubeadm-1)
    - [Other Deprecations](#other-deprecations)
  - [Changes to Major Components](#changes-to-major-components)
    - [API Server](#api-server)
    - [API Server Aggregator](#api-server-aggregator)
  - [Changes to Cluster Provisioning Scripts](#changes-to-cluster-provisioning-scripts)
  - [Changes to Addons](#changes-to-addons)
    - [Dashboard](#dashboard)
  - [External Dependency Version Information](#external-dependency-version-information)
  - [Changelog since v1.6.0-rc.1](#changelog-since-v160-rc1)
    - [Previous Releases Included in v1.6.0](#previous-releases-included-in-v160)
    - [Server Binaries](#server-binaries-14)
- [v1.4.0](#v140)
  - [Downloads](#downloads-8)
  - [Major Themes](#major-themes-1)
  - [Features](#features-1)
  - [Known Issues](#known-issues-1)
  - [Notable Changes to Existing Behavior](#notable-changes-to-existing-behavior-1)
    - [Deployments](#deployments)
    - [kubectl rolling-update: < v1.4.0 client vs >=v1.4.0 cluster](#kubectl-rolling-update:-<-v140-client-vs->=v140-cluster)
    - [kubectl delete: < v1.4.0 client vs >=v1.4.0 cluster](#kubectl-delete:-<-v140-client-vs->=v140-cluster)
    - [Other notable changes](#other-notable-changes-63)
  - [Downloads](#downloads-29)
  - [Highlights](#highlights)
  - [Known Issues and Important Steps before Upgrading](#known-issues-and-important-steps-before-upgrading)
      - [ThirdPartyResource](#thirdpartyresource)
      - [kubectl](#kubectl-2)
      - [kubernetes Core Known Issues](#kubernetes-core-known-issues)
      - [Docker runtime Known Issues](#docker-runtime-known-issues)
      - [Rkt runtime Known Issues](#rkt-runtime-known-issues)
  - [Provider-specific Notes](#provider-specific-notes)
    - [Experimental Features](#experimental-features-2)
<!-- END MUNGE: GENERATED_TOC -->

<!-- NEW RELEASE NOTES ENTRY -->


# v1.6.4

[Documentation](https://docs.k8s.io) & [Examples](https://releases.k8s.io/release-1.6.3/examples)

## Downloads for v1.6.4


filename | sha256 hash
-------- | -----------
[kubernetes.tar.gz](https://dl.k8s.io/v1.6.4/kubernetes.tar.gz) | `fef6a97be8195fee1108b40acbd7bea61ef5244b8be23e799d2d01ee365907dd`
[kubernetes-src.tar.gz](https://dl.k8s.io/v1.6.4/kubernetes-src.tar.gz) | `2915465e9b389c5af0fa660f6e7cbc36a416d1286094201e2a2da5b084a37cb3`

### Client Binaries

filename | sha256 hash
-------- | -----------
[kubernetes-client-darwin-386.tar.gz](https://dl.k8s.io/v1.6.4/kubernetes-client-darwin-386.tar.gz) | `e2db37a1cf3dff342e9ba25506c96edba0cbc9b65984dfe985a7ab45df64f93e`
[kubernetes-client-darwin-amd64.tar.gz](https://dl.k8s.io/v1.6.4/kubernetes-client-darwin-amd64.tar.gz) | `0d49df4b06f76b5a6e168f72ac0088194d4267cc888880f7d0f23e558cd0ee32`
[kubernetes-client-linux-386.tar.gz](https://dl.k8s.io/v1.6.4/kubernetes-client-linux-386.tar.gz) | `5e218cc7f01d6fa71d0a10a30eea2724ee111db3bbae5a03f0c560cd0d24a5df`
[kubernetes-client-linux-amd64.tar.gz](https://dl.k8s.io/v1.6.4/kubernetes-client-linux-amd64.tar.gz) | `4c8dbd03a66d871f03592e84ed98d205d2d0e0c0f6d48c7b60f3e9840ad04df8`

## Changelog since v1.6.3

### Other notable changes

* Fix kubelet panic during disk eviction introduced in 1.6.3. ([#46049](https://github.com/kubernetes/kubernetes/pull/46049), [@enisoc](https://github.com/enisoc))
* Fix pods failing to start if they specify a file as a volume subPath to mount. ([#46046](https://github.com/kubernetes/kubernetes/pull/46046), [@enisoc](https://github.com/enisoc))



# v1.7.0-alpha.4

[Documentation](https://docs.k8s.io) & [Examples](https://releases.k8s.io/master/examples)

### Action Required

## 1. Compilación

```
cd toc/app
```
```
go build -o toc
```
# v1.6.0

[Documentation](https://docs.k8s.io) & [Examples](https://releases.k8s.io/release-1.6/examples)

## Downloads for v1.6.0


filename | sha256 hash
-------- | -----------
[kubernetes.tar.gz](https://dl.k8s.io/v1.6.0/kubernetes.tar.gz) | `e89318b88ea340e68c427d0aad701e544ce2291195dc1d5901222e7bae48f03b`
[kubernetes-src.tar.gz](https://dl.k8s.io/v1.6.0/kubernetes-src.tar.gz) | `0b03d27e1c7af3be5d94ecd5f679e5f55588d801376cf1ae170d9ec0a229b1e2`

### Client Binaries

filename | sha256 hash
-------- | -----------
[kubernetes-client-darwin-386.tar.gz](https://dl.k8s.io/v1.6.0/kubernetes-client-darwin-386.tar.gz) | `274277a67a85e9081d9fee5e763ed7c3dd096acf641c31a9ccc916a3981fead2`
[kubernetes-client-linux-386.tar.gz](https://dl.k8s.io/v1.6.0/kubernetes-client-linux-386.tar.gz) | `4c6a3c12f131c3c88612f888257d00a3cc7fef67947757b897b0d8be9fab547c`
[kubernetes-client-linux-amd64.tar.gz](https://dl.k8s.io/v1.6.0/kubernetes-client-linux-amd64.tar.gz) | `4a5daf0459dffc24bf0ccbb2fc881f688008e91ae41fde961b81d09b0801004c`
[kubernetes-client-linux-arm64.tar.gz](https://dl.k8s.io/v1.6.0/kubernetes-client-linux-arm64.tar.gz) | `91d5e31407140a55cf00c0dc6e20aa8433cc918615dedd842637585e81694ebd`

## WARNING: etcd backup strongly recommended

Before updating to 1.6, you are strongly recommended to back up your etcd data.
Please consult the installation procedure you are using (kargo, kops, kube-up,
kube-aws, kubeadm etc) for specific advice.

1.6 encourages etcd3, and switching from etcd2 to etcd3 involves a full
migration of data between different storage engines.  You must stop the API
from writing to etcd during an etcd2 -> etcd3 migration.  HA installations cannot
be migrated at the current time using the official Kubernetes procedure.

1.6 will also default to protobuf encoding if using etcd3.  **This change is
irreversible.**  To rollback, you must restore from a backup made before the
poes not support protobuf encoding, if you roll back to 1.5 after upgrading to
protobuf you will be forced to restore from backup, and you will lose any changes
since you converted to protobuf.  After conversion to protobuf, you should
validate the correct operation of your cluster thoroughly before returning it
to normal operation.

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
* The [`kubefed` federation bootstrap tool](https://kubernetes.io/docs/tutorials/federation/set-up-cluster-federationthe kubelet. Docker remains the default runtime via Docker-CRI (which moves to beta).
  * **WARNING:** A [known issue](https://github.com/kubernetes/kubernetes/issues/44041)
    in v1.6.0 causes `Pod.Spec.HostPid` (using the host PID namespace for the pod) to always
    be false. Please wait for v1.6.2, which will include a fix for this issue.
* Various scheduling features have graduated to beta:
  * You can now use [multiple schedulers](https://kubernetes.io/docs/tutorials/clusters/multiple-schedulers/)
  * [Nodes](https://kubernetes.io/docs/concepts/configuration/assign-pod-node/#node-affinity-beta-feature) and [pods](https://kubernetes.io/docs/concepts/configuration/assign-pod-node/#inter-pod-affinity-and-anti-affinity-beta-feature) now support affinity and anti-affinity
  * Advanced scheduling can be performed with [taints and tolerations](https://kubernetes.io/docs/concepts/configuration/assign-pod-node/#taints-and-tolerations-beta-feature)
* You can now specify (per pod) how long a pod should stay bound to a node, when there is a node problem.
* Various storage features have graduated to GA:
  * StorageClass pre-installed and set as default on Azure, AWS, GCE, OpenStack, and vSphere
  * Configurable [Dynamic Provisioning](https://kubernetes.io/docs/concepts/storage/persistent-volumes/#dynamic) and [StorageClass](https://kubernetes.io/docs/concepts/storage/persistent-volumes/#storageclasses)
* DaemonSets [can now be updated by a rolling update](https://kubernetes.io/docs/tasks/manage-daemon/update-daemon-set).

## Action Required

### Certificates API
* Users of the alpha certificates API should delete v1alpha1 CSRs from the API before upgrading and recreate them as v1beta1 CSR after upgrading. ([#39772](https://github.com/kubernetes/kubernetes/pull/39772), [@mikedanese](https://github.com/mikedanese))

### Cluster Autoscaler
* If you are using (or planning to use) Cluster Autoscaler pleasn it is actually needed, when there are
unschedulable pods, scale up is required and cloud provider is slow to set up networking for new nodes.
Anyway, the cluster should get back to the proper size after 10 min.

### Deployment
* Deployment now fully respects ControllerRef to avoid fighting over Pods and ReplicaSets. At the time of upgrade, **you must not have Deployments with selectors that overlap**, or else [ownership of ReplicaSets may change](https://github.com/kubernetes/community/blob/master/contributors/design-proposals/controller-ref.md#upgrading). ([#42175](https://github.com/kubernetes/kubernetes/pull/42175), [@enisoc](https://github.com/enisoc))

### Federationarun))
* Cluster federation servers have changed the location in etcd where federated services are stored, so existing federated services must be deleted and recreated. Before upgrading, export all federated services from the federation server and delete the services. After upgrading the cluster, recreate the federated services from the exported data. ([#37770](https://github.com/kubernetes/kubernetes/pull/37770), [@enj](https://github.com/enj))

### Internal Storage Layer
* upgrade to etcd3 prior to upgrading to 1.6 **OR** explicitly specify `--storage-backend=etcd2 --storage-media-type=application/json` when starting the apiserver

### Node Components
* **Kubelet with the Docker-CRI implementation**
  * The Docker-CRI implementation is enabled by default.
  * It is not compatible with containers created by older Kubelets. It is
    recommended to drain your node before upgrade. If you choose to perform
    an in-place upgrade, the Kubelet will automatically restart all
    Kubernetes-managed containers on the node.
  * It is not compatible with CNI plugins that do not conform to the
    [error handling behavior in the spec](https://github.com/containernetworking/cni/blob/master/SPEC.md#network-configuration-list-error-handling).
    The plugins are being updated to resolve this issue ([#43488](https://github.com/kubernetes/kubernetes/issues/43488)).
    You can disable CRI explicitly (`--enable-cri=false`) as a
    temporary workaround.
      * The standard `bridge` plugin have been validated to interoperate with
         the new CRI + CNI code path.
      * If you are using plugins other than `bridge`, make sure you have
        updated custom plugins to the latest version that is compatible.

### Service
* The 'endpoints.beta.kubernetes.io/hostnames-map' annotation is no longer supported.  Users can use the 'Endpoints.subsets[].addresses[].hostname' field instead. ([#39284](https://github.com/kubernetes/kubernetes/pull/39284), [@bowei](https://github.com/bowei))

### StatefulSet [ownership of Pods may change](https://github.com/kubernetes/community/blob/master/contributors/design-proposals/controller-ref.md#upgrading). ([#42080](https://github.com/kubernetes/kubernetes/pull/42080), [@enisoc](https://github.com/enisoc))


### Node Components
* **[stable]** Init containers have graduated to GA and now appear as a field.
  The beta annotation value will still be respected and overrides the field
  value.
* Kubelet Container Runtime Interface (CRI) support
  - **[beta]** The Docker-CRI implementation is enabled by default in kubelet.
    You can disable it by --enable-cri=false. See
    [notes on the new implementation](https://github.com/kubernetes/community/blob/master/contributors/devel/container-runtime-interface.md#kubernetes-v16-release-docker-cri-integration-beta)
    for more details.
  - **[alpha]** Alpha support for other runtimes:
    [cri-o](https://github.com/kubernetes-incubator/cri-o/releases/tag/v0.1), [frakti](https://github.com/kubernetes/frakti/releases/tag/v0.1), [rkt](https://github.com/coreos/rkt/issues?q=is%3Aopen+is%3Aissue+label%3Aarea%2Fcri).
* **[beta]** Node Problem Detector is beta (v0.3.0) now. New
  features added into node-problem-detector:v0.3.0:
  - Add support for journald.
  - The ability to monitor any system daemon logs. Previously only kernel
    logs were supported.
  - The ability to be deployed and run as a native daemon.
* **[alpha]** Critical Pods: When feature gate "ExperimentalCriticalPodAnnotation" is
  set to true, the system will guarantee scheduling and admission of pods with
  the following annotation - `scheduler.alpha.kubernetes.io/critical-pod`
  - This feature should be used in conjunction with the
    [rescheduler](https://kubernetes.io/docs/admin/rescheduler/) to guarantee
    resource availability for critical system pods.

### Volumes
* **[stable]** StorageClass API is promoted to v1 (storage.k8s.io/v1).
* **[stable]** Default storage classes are deployed during installation on Azure, AWS, GCE, OpenStack and vSphere.
* **[stable]** Added ability to populate environment variables from a configmap or secret.
* **[stable]** Support for user-written/run dynamic PV provisioners. The Kubernetes Incubator contains [a golang library and examples](https://github.com/kubernetes-incubator/external-storage).
* **[stable]** Volume plugin for ScaleIO enabling pods to seamlessly access and use data stored on Dell EMC ScaleIO volumes.
* **[stable]** Volume plugin for Portworx added capability to use [Portworx](http://www.portworx.com) as a storage provider for Kubernetes clusters. Portworx pools server capacity and turns servers or cloud instances into converged, highly available compute and storage nodes.
* **[stable]** Add support to use NFSv3, NFSv4, and GlusterFS on GCE/GKE GCI image based clusters.
* **[beta]** Added support for mount options in persistent volumes.
* **[alpha]** All in one volume proposal - a new volume driver capable of projecting secrets, configmaps, and downward API items into the same directory.
* **[alpha]** Flex volume API and Improved lifecycle (flexvolume).

## Deprecations
* Remove extensions/v1beta1 Jobs resource, and job/v1beta1 generator. ([#38614](https://github.com/kubernetes/kubernetes/pull/38614), [@soltysh](https://github.com/soltysh))
* `federation/deploy/deploy.sh` was an interim solution introduced in Kubernetes v1.4 to simplify the federation control plane deployment experience. Now that we have `kubefed`, we are deprecating `deploy.sh` scripts. ([#38902](https://github.com/kubernetes/kubernetes/pull/38902), [@madhusudancs](https://github.com/madhusudancs))


### Cluster Provisioning Scripts
* The bash AWS deployment via kube-up.sh has been deprecated. See http://kubernetes.io/docs/getting-started-guides/aws/ for alternatives. ([#38772](https://github.com/kubernetes/kubernetes/pull/38772), [@zmerlynn](https://github.com/zmerlynn))
* Remove Azure kube-up as the Azure community has focused efforts elsewhere. ([#41672](https://github.com/kubernetes/kubernetes/pull/41672), [@mikedanese](https://github.com/mikedanese))
* Remove the deprecated vsphere kube-up. ([#39140](https://github.com/kubernetes/kubernetes/pull/39140), [@kerneltime](https://github.com/kerneltime))

### kubeadm
* Quite a few flags been renamed or removed.  Those options that are removed as flags can still be accessed via the config file.  Most noteably this includes external etcd settings and the option for setting the cloud provider on the API server.  The [kubeadm reference documentation](https://kubernetes.io/docs/admin/kubeadm/) is up to date with the new flags.

### Other Deprecations
* Remove cmd/kube-discovery from the tree since it's not necessary anymore ([#42070](https://github.com/kubernetes/kubernetes/pull/42070), [@luxas](https://github.com/luxas))

## Changes to API Resources
### ABAC
* ABAC policies using `"user":"*"` or `"group":"*"` to match all users or groups will only match authenticated requests. To match unauthenticated requests, ABAC policies must explicitly specify `"group":"system:unauthenticated"` ([#38968](https://github.com/kubernetes/kubernetes/pull/38968), [@liggitt](https://github.com/liggitt))

### DaemonSet
* DaemonSet now respects ControllerRef to avoid fighting over Pods. ([#42173](https://github.com/kubernetes/kubernetes/pull/42173), [@enisoc](https://github.com/enisoc))
* Make DaemonSet respect critical pods annotation when scheduling. ([#42028](https://github.com/kubernetes/kubernetes/pull/42028), [@janetkuo](https://github.com/janetkuo))
* Implement the update feature for DaemonSet. ([#41116](https://github.com/kubernetes/kubernetes/pull/41116), [@lukaszo](https://github.com/lukaszo))
* Make DaemonSets survive taint-based evictions when nodes turn unreachable/notReady. ([#41896](https://github.com/kubernetes/kubernetes/pull/41896), [@kevin-wangzefeng](https://github.com/kevin-wangzefeng))
* Make DaemonSet controller respect node taints and pod tolerations. ([#41172](https://github.com/kubernetes/kubernetes/pull/41172), [@janetkuo](https://github.com/janetkuo))
* DaemonSet controller actively kills failed pods (to recreate them) ([#40330](https://github.com/kubernetes/kubernetes/pull/40330), [@janetkuo](https://github.com/janetkuo))
* DaemonSet ObservedGeneration ([#39157](https://github.com/kubernetes/kubernetes/pull/39157), [@lukaszo](https://github.com/lukaszo))

#### Generic API Server
* Move pkg/api/rest into genericapiserver ([#39948](https://github.com/kubernetes/kubernetes/pull/39948), [@sttts](https://github.com/sttts))
* Move non-generic apiserver code out of the generic packages ([#38191](https://github.com/kubernetes/kubernetes/pull/38191), [@sttts](https://github.com/sttts))
* Fixes API compatibility issue with empty lists incorrectly returning a null `items` field instead of an empty array. ([#39834](https://github.com/kubernetes/kubernetes/pull/39834), [@liggitt](https://github.com/liggitt))
* Re-add /healthz/ping handler in genericapiserver ([#38603](https://github.com/kubernetes/kubernetes/pull/38603), [@sttts](https://github.com/sttts))
* Remove genericapiserver.Options.MasterServiceNamespace ([#38186](https://github.com/kubernetes/kubernetes/pull/38186), [@sttts](https://github.com/sttts))
* genericapiserver: cut off more dependencies – episode 3 ([#40426](https://github.com/kubernetes/kubernetes/pull/40426), [@sttts](https://github.com/sttts))
* genericapiserver: more dependency cutoffs ([#40216](https://github.com/kubernetes/kubernetes/pull/40216), [@sttts](https://github.com/sttts))
* genericapiserver: cut off kube pkg/version dependency ([#39943](https://github.com/kubernetes/kubernetes/pull/39943), [@sttts](https://github.com/sttts))
* genericapiserver: cut off pkg/serviceaccount dependency ([#39945](https://github.com/kubernetes/kubernetes/pull/39945), [@sttts](https://github.com/sttts))
* genericapiserver: cut off pkg/apis/extensions and pkg/storage dependencies ([#39946](https://github.com/kubernetes/kubernetes/pull/39946), [@sttts](https://github.com/sttts))
* genericapiserver: cut off certificates api dependency ([#39947](https://github.com/kubernetes/kubernetes/pull/39947), [@sttts](https://github.com/sttts))
* genericapiserver: extract CA cert from server cert and SNI cert chains ([#39022](https://github.com/kubernetes/kubernetes/pull/39022), [@sttts](https://github.com/sttts))
* genericapiserver: turn APIContainer.SecretRoutes into a real ServeMux ([#38826](https://github.com/kubernetes/kubernetes/pull/38826), [@sttts](https://github.com/sttts))
* genericapiserver: unify swagger and openapi in config ([#38690](https://github.com/kubernetes/kubernetes/pull/38690), [@sttts](https://github.com/sttts))

### kubeadm
* A new label and taint is used for marking the master. The label is `node-role.kubernetes.io/master=""` and the taint has the effect `NoSchedule`. Tolerate the `node-role.kubernetes.io/master="":NoSchedule` taint to schedule a workload on the master (a networking DaemonSet for example).
* The kubelet API is now secured, only cluster admins are allowed to access it.
* Insecure access to the API Server over `localhost:8080` is now disabled.
* The control plane components now talk securely to each other. The API Server talks securely to the kubelets in the cluster.
* kubeadm creates RBAC-enabled clusters. This means that some add-ons which worked previously won't work without having their YAML configuration updated. Please see each vendor's own documentation to check that the add-ons you are using will work with Kubernetes 1.6.
* The kube-discovery Deployment isn't used anymore when creating a kubeadm cluster and shouldn't be used anywhere else either due to its insecure nature.
* The Certificates API has graduated from alpha to beta. This is a backwards-incompatible change since the alpha support is dropped, and therefore kubeadm v1.5 and v1.6 don't work together (for example kubeadm v1.5 can't join a kubeadm v1.6 cluster).
* Supporting only etcd3, with 3.0.14 as the minimum version.
* `kubeadm reset` will no longer drain nodes automatically.  This is because the credentials on nodes do not have permission to perform this operation.  We have documented an [alternate procedure](https://kubernetes.io/docs/getting-started-guides/kubeadm/#tear-down), driven from the API server/master.
* Hook up kubeadm against the BootstrapSigner ([#41417](https://github.com/kubernetes/kubernetes/pull/41417), [@luxas](https://github.com/luxas))
* Rename some flags for beta UI and fixup some logic ([#42064](https://github.com/kubernetes/kubernetes/pull/42064), [@luxas](https://github.com/luxas))
* Insecure access to the API Server at localhost:8080 will be turned off in v1.6 when using kubeadm ([#42066](https://github.com/kubernetes/kubernetes/pull/42066), [@luxas](https://github.com/luxas))
* Flag --use-kubernetes-version for kubeadm init renamed to --kubernetes-version ([#41820](https://github.com/kubernetes/kubernetes/pull/41820), [@kad](https://github.com/kad))
* Remove the --cloud-provider flag for beta init UX ([#41710](https://github.com/kubernetes/kubernetes/pull/41710), [@luxas](https://github.com/luxas))
* Fixed an SELinux issue in kubeadm on Docker 1.12+ by moving etcd SELinux options from container to pod. ([#40682](https://github.com/kubernetes/kubernetes/pull/40682), [@dgoodwin](https://github.com/dgoodwin))
* Add authorization mode to kubeadm ([#39846](https://github.com/kubernetes/kubernetes/pull/39846), [@andrewrynhard](https://github.com/andrewrynhard))
* Refactor the certificate and kubeconfig code in the kubeadm binary into two phases ([#39280](https://github.com/kubernetes/kubernetes/pull/39280), [@luxas](https://github.com/luxas))
* Added kubeadm commands to manage bootstrap tokens and the duration they are valid for. ([#35805](https://github.com/kubernetes/kubernetes/pull/35805), [@dgoodwin](https://github.com/dgoodwin))

### kubectl

#### New Commands
- `apply set-last-applied` *updates the applied-applied-configuration annotation* ([#41694](https://github.com/kubernetes/kubernetes/pull/41694), [@shiywang](https://github.com/shiywang))
- `kubectl apply view-last-applied` *viewing the last configuration file applied* ([#41146](https://github.com/kubernetes/kubernetes/pull/41146), [@shiywang](https://github.com/shiywang))

### Node Components
* Kubelet config should ignore file start with dots.
  ([#39196](https://github.com/kubernetes/kubernetes/pull/39196), [@resouer](https://github.com/resouer))
* Bump GCI to gci-stable-56-9000-84-2.
  ([#41819](https://github.com/kubernetes/kubernetes/pull/41819),
  [@dchen1107](https://github.com/dchen1107))
* Bump GCE ContainerVM to container-vm-v20170214 to address CVE-2016-9962.
  ([#41449](https://github.com/kubernetes/kubernetes/pull/41449),
  [@zmerlynn](https://github.com/zmerlynn))
* Kubelet: Remove the PLEG health check from /healthz, Kubelet will now report
* NodeNotReady on failed PLEG health check.
  ([#41569](https://github.com/kubernetes/kubernetes/pull/41569),
  [@yujuhong](https://github.com/yujuhong))
* CRI: upgrade protobuf to v3. Protobuf v2 and v3 are not compatible.
  ([#39158](https://github.com/kubernetes/kubernetes/pull/39158), [@feiskyer](https://github.com/feiskyer))
* kubelet exports metrics for cgroup management ([#41988](https://github.com/kubernetes/kubernetes/pull/41988), [@sjenning](https://github.com/sjenning))
* Experimental support to reserve a pod's memory request from being utilized by
  pods in lower QoS tiers.
  ([#41149](https://github.com/kubernetes/kubernetes/pull/41149),
  [@sjenning](https://github.com/sjenning))
* Port forwarding can forward over websockets or SPDY.
  ([#33684](https://github.com/kubernetes/kubernetes/pull/33684),
  [@fraenkel](https://github.com/fraenkel))
* Flag gate faster evictions based on node memory pressure using kernel memcg
  notifications - `--experimental-kernel-memcg-notification`.
  ([#38258](https://github.com/kubernetes/kubernetes/pull/38258),
  [@derekwaynecarr](https://github.com/derekwaynecarr))
* Nodes can now report two additional address types in their status: InternalDNS
  and ExternalDNS. The apiserver can use --kubelet-preferred-address-types to
  give priority to the type of address it uses to reach nodes.
  ([#34259](https://github.com/kubernetes/kubernetes/pull/34259), [@liggitt](https://github.com/liggitt))

#### Bug fixes
* Add image cache to fix the issue where kubelet hands when reporting the node
  status. ([#38375](https://github.com/kubernetes/kubernetes/pull/38375),
  [@Random-Liu](https://github.com/Random-Liu))
* Fix logic error in graceful deletion that caused pods not being able to
  be deleted. ([#37721](https://github.com/kubernetes/kubernetes/pull/37721),
  [@derekwaynecarr](https://github.com/derekwaynecarr))
* Fix ConfigMap for Windows Containers.
  ([#39373](https://github.com/kubernetes/kubernetes/pull/39373),
  [@jbhurat](https://github.com/jbhurat))
* Fix the “pod rejected by kubelet may stay at pending forever” bug.
  (https://github.com/kubernetes/kubernetes/pull/37661),
  [@yujuhong](https://github.com/yujuhong))

### kube-controller-manager
* add --controllers to controller manager ([#39740](https://github.com/kubernetes/kubernetes/pull/39740), [@deads2k](https://github.com/deads2k))

### kube-dns
* Adds support for configurable DNS stub domains and upstream nameservers.
  The following configuration options have been added to the `kube-system:kube-dns` ConfigMap:
  ```
  "stubDomains": {
    "acme.local": ["1.2.3.4"]
  },
  ```
  is a map of domain to list of nameservers for the domain. This is used
  to inject private DNS domains into the kube-dns namespace. In the above
  example, any DNS requests for *.acme.local will be served by the
  nameserver 1.2.3.4.
  ```
  "upstreamNameservers": ["8.8.8.8", "8.8.4.4"]
  ```
  is a list of upstreamNameservers to use, overriding the configuration
  specified in /etc/resolv.conf.

* An empty `kube-system:kube-dns` ConfigMap will be created for the cluster if one did not already exist.

## External Dependency Version Information

Continuous integration builds have used the following versions of external dependencies, however, this is not a strong recommendation and users should consult an appropriate installation or upgrade guide before deciding what versions of etcd, docker or rkt to use.

* Docker versions 1.10.3, 1.11.2, 1.12.6 have been validated
  * Docker version 1.12.6 known issues
    * overlay2 driver not fully supported
    * live-restore not fully supported
    * no shared pid namespace support
  * Docker version 1.11.2 known issues
    * Kernel crash with Aufs storage driver on Debian Jessie ([#27885](https://github.com/kubernetes/kubernetes/issues/27885))
      which can be identified by the [node problem detector](http://kubernetes.io/docs/admin/node-problem/)
    * Leaked File descriptors ([#275](https://github.com/docker/containerd/issues/275))
    * Additional memory overhead per container ([#21737](https://github.com/docker/docker/issues/21737))
  * Docker 1.10.3 contains [backports provided by RedHat](https://github.com/docker/docker/compare/v1.10.3...runcom:docker-1.10.3-stable) for known issues
  * Support for Docker version 1.9.x has been removed
* rkt version 1.23.0+
  * known issues with the rkt runtime are [listed in the Getting Started Guide](http://kubernetes.io/docs/getting-started-guides/rkt/notes/)
* etcd version 3.0.17
## Changelog since v1.6.0-rc.1


### Previous Releases Included in v1.6.0
- [v1.6.0-rc.1](https://github.com/kubernetes/kubernetes/blob/master/CHANGELOG.md#v160-rc1)
- [v1.6.0-beta.4](https://github.com/kubernetes/kubernetes/blob/master/CHANGELOG.md#v160-beta4)
- [v1.6.0-beta.3](https://github.com/kubernetes/kubernetes/blob/master/CHANGELOG.md#v160-beta3)
- [v1.6.0-beta.2](https://github.com/kubernetes/kubernetes/blob/master/CHANGELOG.md#v160-beta2)
- [v1.6.0-beta.1](https://github.com/kubernetes/kubernetes/blob/master/CHANGELOG.md#v160-beta1)
- [v1.6.0-alpha.3](https://github.com/kubernetes/kubernetes/blob/master/CHANGELOG.md#v160-alpha3)
- [v1.6.0-alpha.2](https://github.com/kubernetes/kubernetes/blob/master/CHANGELOG.md#v160-alpha2)
- [v1.6.0-alpha.1](https://github.com/kubernetes/kubernetes/blob/master/CHANGELOG.md#v160-alpha1)
**No notable changes for this release**



  * <strong>Significant scale improvements</strong>. Increased cluster scale by 400% to 1000 nodes with 30,000 pods per cluster.
Kubelet supports 100 pods per node with 4x reduced system overhead.
  * <strong>Simplified application deployment and management. </strong>
     * Dynamic Configuration (ConfigMap API in the core API group) enables application
configuration to be stored as a Kubernetes API object and pulled dynamically on
container startup, as an alternative to baking in command-line flags when a
container is built.
     * Turnkey Deployments (Deployment API (Beta) in the Extensions API group)
automate deployment and rolling updates of applications, specified
declaratively. It handles versioning, multiple simultaneous rollouts,
aggregating status across all pods, maintaining application availability, and
rollback.
  * <strong>Automated cluster management: </strong>
     * Kubernetes clusters can now span zones within a cloud provider. Pods from a
service will be automatically spread across zones, enabling applications to
tolerate zone failure.
     * Simplified way to run a container on every node (DaemonSet API (Beta) in the
Extensions API group): Kubernetes can schedule a service (such as a logging
agent) that runs one, and only one, pod per node.
     * TLS and L7 support (Ingress API (Beta) in the Extensions API group): Kubernetes
is now easier to integrate into custom networking environments by supporting
TLS for secure communication and L7 http-based traffic routing.
     * Graceful Node Shutdown (aka drain) - The new “kubectl drain” command gracefully
evicts pods from nodes in preparation for disruptive operations like kernel
upgrades or maintenance.
     * Custom Metrics for Autoscaling (HorizontalPodAutoscaler API in the Autoscaling
API group): The Horizontal Pod Autoscaling feature now supports custom metrics
(Alpha), allowing you to specify application-level metrics and thresholds to
trigger scaling up and down the number of pods in your application.
  * <strong>New GUI</strong> (dashboard) allows you to get started quickly and enables the same
functionality found in the CLI as a more approachable and discoverable way of
interacting with the system. Note: the GUI is enabled by default in 1.2 clusters.

<img src="docs/images/newgui.png" width="" alt="Dashboard UI screenshot showing cards that represent applications that run inside a cluster" title="Dashboard UI apps screen">
