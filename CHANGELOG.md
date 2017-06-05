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
[kubernetes-client-linux-arm64.tar.gz](https://dl.k8s.io/v1.6.4/kubernetes-client-linux-arm64.tar.gz) | `9bf29b0f8bdde972d62556bdd14622199f979f7dcf56d3948d429b1d73feca08`
[kubernetes-client-linux-arm.tar.gz](https://dl.k8s.io/v1.6.4/kubernetes-client-linux-arm.tar.gz) | `bbca1efe8fb95c6df7b330054776ce619652ba9d4c5428eabef9c435c61d1d9a`
[kubernetes-client-linux-ppc64le.tar.gz](https://dl.k8s.io/v1.6.4/kubernetes-client-linux-ppc64le.tar.gz) | `7aa02e261f36a816dc1c7c898e16d732d9199d827ac4828f8e120b4a9ce5aa05`
[kubernetes-client-linux-s390x.tar.gz](https://dl.k8s.io/v1.6.4/kubernetes-client-linux-s390x.tar.gz) | `531d00c43a49bb72365f2d6c1f31ad99ff09893e41f6b28d21980dbdd3ab0de4`
[kubernetes-client-windows-386.tar.gz](https://dl.k8s.io/v1.6.4/kubernetes-client-windows-386.tar.gz) | `256fa2ffa77a1107e87a5a232bf8aa245afbcb5d383eda18f19f3fedbbad9a69`
[kubernetes-client-windows-amd64.tar.gz](https://dl.k8s.io/v1.6.4/kubernetes-client-windows-amd64.tar.gz) | `c8a97087b81defdc513a9fe4aaf317d10ad6fc3368170465dd4ea64c23655939`

### Server Binaries

filename | sha256 hash
-------- | -----------
[kubernetes-server-linux-amd64.tar.gz](https://dl.k8s.io/v1.6.4/kubernetes-server-linux-amd64.tar.gz) | `76a1d6dbce630b50fd3a5f566fcea6ef1a04996cf4f4c568338a3db0d3b6a3d5`
[kubernetes-server-linux-arm64.tar.gz](https://dl.k8s.io/v1.6.4/kubernetes-server-linux-arm64.tar.gz) | `8b731307138a71ae90e025cb85ec7b4ac9179ebd8923f7abd1c839a2966ff2b0`
[kubernetes-server-linux-arm.tar.gz](https://dl.k8s.io/v1.6.4/kubernetes-server-linux-arm.tar.gz) | `0d3039f22cdc36526257f211c55099552b8d55cda25a05405f2701c869bb4be2`
[kubernetes-server-linux-ppc64le.tar.gz](https://dl.k8s.io/v1.6.4/kubernetes-server-linux-ppc64le.tar.gz) | `6de3a85392ff65c019fd90173f1219a41f56559aebd07b18ed497e46645fcffc`
[kubernetes-server-linux-s390x.tar.gz](https://dl.k8s.io/v1.6.4/kubernetes-server-linux-s390x.tar.gz) | `622a137c06a9fda23ec5941dd41607564804eeede0e6d3976cda6cc136e010c6`

### Node Binaries

filename | sha256 hash
-------- | -----------
[kubernetes-node-linux-amd64.tar.gz](https://dl.k8s.io/v1.6.4/kubernetes-node-linux-amd64.tar.gz) | `df40c178ffbd92376e98dd258113e35c0a46a8313f188d34d391a834baeb1da8`
[kubernetes-node-linux-arm64.tar.gz](https://dl.k8s.io/v1.6.4/kubernetes-node-linux-arm64.tar.gz) | `a27b15a0edcfd78470db54181ea2c2c942b5d4489b6f7a4ba78bb1fac34f8fa8`
[kubernetes-node-linux-arm.tar.gz](https://dl.k8s.io/v1.6.4/kubernetes-node-linux-arm.tar.gz) | `2b4dceee70ba7b508a0acc3cc5ce072d92f9c32c1a6961911b93a5da02ace9f7`
[kubernetes-node-linux-ppc64le.tar.gz](https://dl.k8s.io/v1.6.4/kubernetes-node-linux-ppc64le.tar.gz) | `c5e01f9f7de6ae2d73004bbcd288f5c942414b6639099c1bf52a98e592147745`
[kubernetes-node-linux-s390x.tar.gz](https://dl.k8s.io/v1.6.4/kubernetes-node-linux-s390x.tar.gz) | `eded4d2b94c9c22ae6c865e32a7965c1228d564aebf90c533607c716ed89b676`
[kubernetes-node-windows-amd64.tar.gz](https://dl.k8s.io/v1.6.4/kubernetes-node-windows-amd64.tar.gz) | `da561264f5665fe1ae9a41999731403b147b91c3a5c47439eb828ed688b0738f`

## Changelog since v1.6.3

### Other notable changes

* Fix kubelet panic during disk eviction introduced in 1.6.3. ([#46049](https://github.com/kubernetes/kubernetes/pull/46049), [@enisoc](https://github.com/enisoc))
* Fix pods failing to start if they specify a file as a volume subPath to mount. ([#46046](https://github.com/kubernetes/kubernetes/pull/46046), [@enisoc](https://github.com/enisoc))



# v1.7.0-alpha.4

[Documentation](https://docs.k8s.io) & [Examples](https://releases.k8s.io/master/examples)

## Downloads for v1.7.0-alpha.4


filename | sha256 hash
-------- | -----------
[kubernetes.tar.gz](https://dl.k8s.io/v1.7.0-alpha.4/kubernetes.tar.gz) | `14ef2ce3c9348dce7e83aeb167be324da93b90dbb8016f2aecb097c982abf790`
[kubernetes-src.tar.gz](https://dl.k8s.io/v1.7.0-alpha.4/kubernetes-src.tar.gz) | `faef422988e805a3970985eabff03ed88cfb95ad0d2223abe03011145016e5d0`

### Client Binaries

filename | sha256 hash
-------- | -----------
[kubernetes-client-darwin-386.tar.gz](https://dl.k8s.io/v1.7.0-alpha.4/kubernetes-client-darwin-386.tar.gz) | `077dc5637f42a35c316a5e1c3a38e09625971894a186dd7b1e60408c9a0ac4b8`
[kubernetes-client-darwin-amd64.tar.gz](https://dl.k8s.io/v1.7.0-alpha.4/kubernetes-client-darwin-amd64.tar.gz) | `8e43eb7d1969e82eeb17973e4f09e9fe44ff3430cd2c35170d72a631c460deeb`
[kubernetes-client-linux-386.tar.gz](https://dl.k8s.io/v1.7.0-alpha.4/kubernetes-client-linux-386.tar.gz) | `6ddfdbcb25243901c965b1e009e26a90b1fd08d6483906e1235ef380f6f93c97`
[kubernetes-client-linux-amd64.tar.gz](https://dl.k8s.io/v1.7.0-alpha.4/kubernetes-client-linux-amd64.tar.gz) | `3e7cdd8e0e4d67ff2a0ee2548a4c48a433f84a25384ee9d22c06f4eb2e6db6d7`
[kubernetes-client-linux-arm64.tar.gz](https://dl.k8s.io/v1.7.0-alpha.4/kubernetes-client-linux-arm64.tar.gz) | `3970c88d2c36fcb43a64d4e889a3eb2cc298e893f6084b9a3c902879d777487d`
[kubernetes-client-linux-arm.tar.gz](https://dl.k8s.io/v1.7.0-alpha.4/kubernetes-client-linux-arm.tar.gz) | `156909c55feb06036afff72aa180bd20c14758690cd04c7d8867f49c968e6372`
[kubernetes-client-linux-ppc64le.tar.gz](https://dl.k8s.io/v1.7.0-alpha.4/kubernetes-client-linux-ppc64le.tar.gz) | `601fe881a131ce7868fdecfb1439da94ab5a1f1d3700efe4b8319617ceb23d4e`
[kubernetes-client-linux-s390x.tar.gz](https://dl.k8s.io/v1.7.0-alpha.4/kubernetes-client-linux-s390x.tar.gz) | `2ed3e74e6a972d9ed5b2206fa5e811663497082384f488eada9901e9a99929c7`
[kubernetes-client-windows-386.tar.gz](https://dl.k8s.io/v1.7.0-alpha.4/kubernetes-client-windows-386.tar.gz) | `1aba520fe0bf620f0e77f697194dfd5e336e4a97e2af01f8b94b0f03dbb6299c`
[kubernetes-client-windows-amd64.tar.gz](https://dl.k8s.io/v1.7.0-alpha.4/kubernetes-client-windows-amd64.tar.gz) | `aaf4a42549ea1113915649e636612ea738ead383140d92944c80f3c0d5df8161`

### Server Binaries

filename | sha256 hash
-------- | -----------
[kubernetes-server-linux-amd64.tar.gz](https://dl.k8s.io/v1.7.0-alpha.4/kubernetes-server-linux-amd64.tar.gz) | `1389c798e7805ec26826c0d3b17ab0d4bd51e0db21cf2f5d4bda5e2b530a6bf1`
[kubernetes-server-linux-arm64.tar.gz](https://dl.k8s.io/v1.7.0-alpha.4/kubernetes-server-linux-arm64.tar.gz) | `ccb99da4b069e63695b3b1d8add9a173e21a0bcaf03d031014460092ec726fb4`
[kubernetes-server-linux-arm.tar.gz](https://dl.k8s.io/v1.7.0-alpha.4/kubernetes-server-linux-arm.tar.gz) | `6eb3fe27e5017ed834a309cba21342a8c1443486a75ec87611fa66649dd5926a`
[kubernetes-server-linux-ppc64le.tar.gz](https://dl.k8s.io/v1.7.0-alpha.4/kubernetes-server-linux-ppc64le.tar.gz) | `9b5030b0205ccccfd08b832eec917853fee8bcd34b04033ba35f17698be4a32f`
[kubernetes-server-linux-s390x.tar.gz](https://dl.k8s.io/v1.7.0-alpha.4/kubernetes-server-linux-s390x.tar.gz) | `36b692c221005b52c2a243ddfc16e41a7b157e10fee8662bcd8270280b3f0927`

### Node Binaries

filename | sha256 hash
-------- | -----------
[kubernetes-node-linux-amd64.tar.gz](https://dl.k8s.io/v1.7.0-alpha.4/kubernetes-node-linux-amd64.tar.gz) | `bba76ad441716f938df0fd8c23c48588d1f80603e39dcca1a29c8b3bbe8c1658`
[kubernetes-node-linux-arm64.tar.gz](https://dl.k8s.io/v1.7.0-alpha.4/kubernetes-node-linux-arm64.tar.gz) | `e3e729847a13fd41ee7f969aabb14d3a0f6f8523f6f079f77a618bf5d781fb9c`
[kubernetes-node-linux-arm.tar.gz](https://dl.k8s.io/v1.7.0-alpha.4/kubernetes-node-linux-arm.tar.gz) | `520f98f244dd35bb0d96072003548f8b3aacc1e7beb31b5bc527416f07af9d32`
[kubernetes-node-linux-ppc64le.tar.gz](https://dl.k8s.io/v1.7.0-alpha.4/kubernetes-node-linux-ppc64le.tar.gz) | `686490ba55ea8c7569b3b506f898315c8b1b243de23733e0cd537e2db8e067cb`
[kubernetes-node-linux-s390x.tar.gz](https://dl.k8s.io/v1.7.0-alpha.4/kubernetes-node-linux-s390x.tar.gz) | `a36bb76b390007b271868987739c550c8ac4e856f218f67f2fd780309a2a522e`
[kubernetes-node-windows-amd64.tar.gz](https://dl.k8s.io/v1.7.0-alpha.4/kubernetes-node-windows-amd64.tar.gz) | `e78c5a32584d96ec177e38b445c053e40c358e0549b925981c118f4c23578261`

## Changelog since v1.7.0-alpha.3

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
[kubernetes-client-linux-arm.tar.gz](https://dl.k8s.io/v1.6.0/kubernetes-client-linux-arm.tar.gz) | `985fecd7fb94b42c25b8a56efde1831b2616a6792d3d5a02549248e01ce524ed`
[kubernetes-client-linux-ppc64le.tar.gz](https://dl.k8s.io/v1.6.0/kubernetes-client-linux-ppc64le.tar.gz) | `303279f935289cadfb97a6a5d3f58b0da67d1b88b5ed049e6a98fc203b7b9d52`
[kubernetes-client-windows-386.tar.gz](https://dl.k8s.io/v1.6.0/kubernetes-client-windows-386.tar.gz) | `11d5459b0d413a25045c55ce3548d30616ddc2d62451280d3299baa9f3e3e014`
[kubernetes-client-windows-amd64.tar.gz](https://dl.k8s.io/v1.6.0/kubernetes-client-windows-amd64.tar.gz) | `84eba6f2b2b82a95397688b1e2ca4deb8d7daf1f8a40919fa0312741ca253799`

### Server Binaries

filename | sha256 hash
-------- | -----------
[kubernetes-server-linux-amd64.tar.gz](https://dl.k8s.io/v1.6.0/kubernetes-server-linux-amd64.tar.gz) | `3625b63d573aa4d28eaa30b291017f775f2ddc0523f40d25023ad1da9c30390e`
[kubernetes-server-linux-arm64.tar.gz](https://dl.k8s.io/v1.6.0/kubernetes-server-linux-arm64.tar.gz) | `906496c985d4d836466b73e1c9e618ea8ce07f396aba3a96edcdc6045e0ab4e3`
[kubernetes-server-linux-arm.tar.gz](https://dl.k8s.io/v1.6.0/kubernetes-server-linux-arm.tar.gz) | `3b63f481156f57729bc8100566d8b3d7856791e5b36bb70042e17d21f11f8d5d`
[kubernetes-server-linux-ppc64le.tar.gz](https://dl.k8s.io/v1.6.0/kubernetes-server-linux-ppc64le.tar.gz) | `382666b3892fd4d89be5e4bb052dd0ef0d1c1d213c1ae7a92435083a105064fd`
[kubernetes-server-linux-s390x.tar.gz](https://dl.k8s.io/v1.6.0/kubernetes-server-linux-s390x.tar.gz) | `e15de8896bd84a9b74756adc1a2e20c6912a65f6ff0a3f3dfabc8b463e31d19b`

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
* **CNI plugins now affect node readiness**
  * Kubelet will now block node readiness until a CNI configuration file is
    present in `/etc/cni/net.d` or a given custom CNI configuration path.
    [This change](https://github.com/kubernetes/kurking before
    [networking is ready](https://github.com/kubernetes/kubernetes/issues/43014).
    This change may require changes to clients that gate pod creation and/or
    scheduling on the node condition `type` `Ready` `status` being `True` for pods
    that need to run prior to the network being ready.
* **Enhance Kubelet QoS**:
  * Pods are placed under a new cgroup hierarchy by default. This feature requires
    draining and restarting the node as part of upgrades. To opt-out set
    `--cgroups-per-qos=false`.
  * If `kube-reserved` and/or `system-reserved` are specified, node allocatable
    will be enforced on all pods by default. To opt-out set
    `--enforce-node-allocatable=””`
  * Hard Eviction Thresholds will be subtracted from Capacity while calculating
    Node Allocatable. This will result in a reduction of schedulable capacity in
    clusters post upgrade where kubelet hard eviction has been turned on for
    memory. To opt-out set `--experimental-allocatable-ignore-eviction=true`.
  * More details on these feature here:
    https://kubernetes.io/docs/concepts/cluster-administration/node-allocatable/
* Drop the support for docker 1.9.x. Docker versions 1.10.3, 1.11.2, 1.12.6
  have been validated.
* The following deprecated kubelet flags are removed: `--config`, `--auth-path`,
  `--resource-container`, `--system-container`, `--reconcile-cidr`
* Remove the temporary fix for pre-1.0 mirror pods. Upgrade directly from
  pre-1.0 to 1.6 kubelet is not supported.
* Fluentd was migrated to Daemon Set, which targets nodes with
  beta.kubernetes.io/fluentd-ds-ready=true label. If you use fluentd in your
  cluster please make sure that the nodes with version 1.6+ contains this
  label.

### kubectl
* Running `kubectl taint` (alpha in 1.5) against a 1.6 server requires upgrading kubectl to version 1.6
* Running `kubectl taint` (alpha in 1.5) against a 1.5 server requires a kubectl version of 1.5
* Running `kubectl create secret` no longer accepts passing multiple values to a single --from-literal flag using comma separation
  * Update command invocations to pass separate --from-literal flags for each value

### RBAC
* Default ClusterRole and ClusterRoleBinding objects are automatically updated at server start to add missing permissions and subjects (extra permissions and subjects are left in place). To prevent autoupdating a particular role or rolebinding, annotate it with `rbac.authorization.kubernetes.io/autoupdate=false`. ([#41155](https://github.com/kubernetes/kubernetes/pull/41155), [@liggitt](https://github.com/liggitt))
* `v1beta1` RoleBinding/ClusterRoleBinding subjects changed `apiVersion` to `apiGroup` to fully-qualify a subject. ServiceAccount subje/pull/39383), [@liggitt](https://github.com/liggitt))
    * 1. Be authorized to make the create or update API request
    * 2. Be allowed to bind the referenced role, either by already having all of the permissions contained in the referenced role, or by having the "bind" permission on the referenced role.
* The `--authorization-rbac-super-user` flag (alpha in 1.5) is deprecated; the `system:masters` group has privileged access ([#38121](https://github.com/kubernetes/kubernetes/pull/38121), [@deads2k](https://github.com/deads2k))
* special handling of the user `*` in RoleBinding and ClusterRoleBinding objects is removed in v1beta1. To match all users, explicitly bind to the group `system:authenticated` and/or `system:unauthenticated`. Existing v1alpha1 bindings to the user `*` are automatically converted to the group `system:authenticated`. ([#38981](https://github.com/kubernetes/kubernetes/pull/38981), [@liggitt](https://github.com/liggitt))

### Scheduling
* **Multiple schedulers**
  * Modify your PodSpecs that currently use the `scheduler.alpha.kubernetes.io/name` annotation on Pod, to instead use the `schedulerName` field in the PodSpec.
  * Modify any custom scheduler(s) you have written so that they read the `schedulerName` field on Pod instead of the `scheduler.alpha.kubernetes.io/name` annotation.
  * Note that you can only start using the `schedulerName` field **after** you upgrade to 1.6; it is not recognized in 1.5.

* **Node affinity/anti-affinity and pod affinity/anti-affinity**
  * You can continue to use the alpha version of this feature (with one caveat -- see below), in which you specify affinity requests using Pod annotations, in 1.6 by including `AffinityInAnnotations=true` in `--feature-gates`, such as `--feature-gates=FooBar=true,AffinityInAnnotations=true`. Otherwise, you must modify your PodSpecs that currently use the `scheduler.alpha.kubernetes.io/affinity` annotation on Pod, to instead use the `affinity` field in the PodSpec. Support for the annotation will be removed in a future release, so we encourage you to switch to using the field as soon as possible.
  * Caveat: The alpha version no longer supports, and the beta version does not support, the "empty `podAffinityTerm.namespaces` list means all namespaces" behavior. In both alpha and beta it now means "same namespace as the pod specifying this affinity rule."
  * Note that you can only start using the `affinity` field **after** you upgrade to 1.6; it is not recognized in 1.5.
  * The `--failure-domains` scheduler command line-argument is not supported in the beta version of the feature.

* **Taints**
  * You will need to use `kubectl taint` to re-create all of your taints after kubectl and the master are upgraded to 1.6. Between the time the master is upgraded to 1.6 and when you do this, your existing taintTo see the taints that were created under 1.5 when you are running 1.6, do `kubectl get node <node name> -o yaml` and look for the "Annotation" section with the annotation key `scheduler.alpha.kubernetes.io/taints`
  * You can remove the "old" taints (stored internally as annotations) at any time after the upgrade by doing `kubectl annotate nodes <node name> scheduler.alpha.kubernetes.io/taints-` (note the minus at the end, which means "delete the taint with this key")
  * Note that because any taints you might have created with Kubernetes 1.5 can only affect the scheduling of new pods (the `NoExecute` taint effect is introduced in 1.6), neither the master upgrade nor your running `kubectl taint` to re-create the taints will affect pods that are already running.
  * Rescheduler relies on taints, which were changed in a backward incompatible way. Rescheduler 0.3 shipped together with Kubernetes 1.6 understands the new taints and will clean up the old annotations, but Rescheduler 0.2 shipped together with Kubernetes 1.5 doesn't understand the new taints. In order to avoid eviction loop during 1.5->1.6 upgrade you need to either upgrade the master node atomically (for example by using `upgrade.sh` script for GCE) or ensure that the rescheduler is upgraded first, then the scheduler and then all the other master components.

* **Tolerations**
  * After your master is upgraded to 1.6, you will need to update your PodSpecs to set the `tolerations` field of the PodSpec and remove the `scheduler.alpha.kubernetes.io/tolerations` annotation on the Pod. (It's not strictly necessary to remove the annotation, as it will have no effect once you upgrade to 1.6.) Between the time the master is upgraded to 1.6 and when you do this, tolerations attached to Pods that are created will have no effect. Pods that are already running will not be affected by the upgrade.
  * You can find the PodSpec tolerations that were created as annotations (if any) in a controller definition by doing `kubectl get <controller kind> <controller name> -o yaml` and looking for the "Annotation" section with the annotation key `scheduler.alpha.kubernetes.io/tolerations` (This will work whether you are running Kubernetes 1.5 or 1.6).
  * To update a controller's PodSpec to use the field instead of the annotation, use one of the kubectl commands that do update ("kubectl replace" or "kubectl apply" or "kubectl patch") or just delete the controller entirely and re-create it with a new pod template. Note that you will be able to do these things only after the upgrade.

### Service
* The 'endpoints.beta.kubernetes.io/hostnames-map' annotation is no longer supported.  Users can use the 'Endpoints.subsets[].addresses[].hostname' field instead. ([#39284](https://github.com/kubernetes/kubernetes/pull/39284), [@bowei](https://github.com/bowei))

### StatefulSet [ownership of Pods may change](https://github.com/kubernetes/community/blob/master/contributors/design-proposals/controller-ref.md#upgrading). ([#42080](https://github.com/kubernetes/kubernetes/pull/42080), [@enisoc](https://github.com/enisoc))

### Volumes
* StorageClass pre-installed and set as default on Azure, AWS, GCE, OpenStack, and vSphere.
  * This is something to pay close attention to if you’ve been using Kubernetes for a while, because it changes the default behavior of PersistentVolumeClaim objects on these clouds.
  * Marking a StorageClass as default makes it so that even a PersistentVolumeClaim without a StorageClass specified will trigger dynamic provisioning (instead of binding to an existing pool of PVs).
  * If you depend on the old behavior of volumes binding to existing pool of PersistentVolume objects then modify the StorageClass object and set `storageclass.beta.kubernetes.io/is-default-class` to `false`.
* Flex volume plugin is updated to support attach/detach interfaces. It broke backward compatibility. Please update your drivers and implement the new callouts.  ([#41804](https://github.com/kubernetes/kubernetes/pull/41804), [@chakri-nelluri](https://github.com/chakri-nelluri))

## Notable Features
Features for this release were tracked via the use of the [kubernetes/features](https://github.com/kubernetes/features) issues repo.  Each Feature issue is owned by a Special Interest Group from the [kubernetes/community](https://github.com/kubernetes/community/blob/master/sig-list.md).

### Autoscaling
* **[alpha]** The Horizontal Pod Autoscaler now supports drawing metrics through the API server aggregator.
* **[alpha]** The Horizontal Pod Autoscaler now supports scaling on multiple, custom metrics.
* Cluster Autoscaler publishes its status to kube-system/cluster-autoscaler-status ConfigMap.
* Cluster Autoscaler can continue operations while some nodes are broken or unready.
* Cluster Autoscaler respects Pod Disruption Budgets when removing a node.

### DaemonSet
* **[beta]** Introduce the rolling update feature for DaemonSet. See [Performing a Rolling Update on a DaemonSet](https://kubernetes.io/docs/tasks/manage-daemon/update-daemon-set/).

### Deployment
* **[beta]** Deployments that cannot make progress in rolling out the newest version will now indicate via the API they are blocked ([docs](https://kubernetes.io/docs/user-guide/deployments/#deployment-status))

### Federation
* **[beta]** `kubefed` has graduated to beta: supports hosting federation on on-prem clusters, automatically configures `kube-dns` in joining clusters and allows passing arguments to federation components.

### Internal Storage Layer
* **[stable]** The internal storage layer for kubernetes cluster state has been updated to use etcd v3 by default. Existing clusters will have to plan for a data migration window. ([docs](https://github.com/kubernetes/kubernetes.github.io/pull/2763))([kubernetes/features#44](https://github.com/kubernetes/features/issues/44))

### kubeadm
* **[beta]** Introduces an API for clients to request TLS certificates from the API server. See the [tutorial](https://kubernetes.io/docs/tasks/tls/managing-tls-in-a-cluster).
* **[beta]** kubeadm is enhanced and improved with a baseline feature set and command line flags that are now marked as beta. Other parts of kubeadm, including subcommands under `kubeadm alpha`, are [still in alpha](https://kubernetes.io/docs/admin/kubeadm/).  Using it is considered safe, although note that upgrades and HA are not yet supported. Please [try it out](https://kubernetes.io/docs/getting-started-guides/kubeadm/) and [give us feedback](https://kubernetes.io/docs/getting-started-guides/kubeadm/#feedback)!
* **[alpha]** New Bootstrap Token authentication and management method. Works welting the new out-of-core cloudprovider flow.

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
* **[alpha]** `--experimental-nvidia-gpus` flag is replaced by `Accelerators` alpha
  feature gate along with addition of support for multiple Nvidia GPUs.
  - To use GPUs, pass `Accelerators=true` as part of `--feature-gates` flag.
  - More information [here](https://vishh.github.io/docs/user-guide/gpus/).
* A pod’s Quality of Service Class is now available in its Status.
* Upgrade cAdvisor library to v0.25.0. Notable changes include,
  - Container filesystem usage tracking disabled for device mapper due to excessive
    IOPS.
  - Ignore `.mount` cgroups, fixing disappearing stats.
* A new field `terminationMessagePolicy` has been added to containers that allows
  a user to request FallbackToLogsOnError, which will read from the container's
  logs to populate the termination message if the user does not write to the
  termination message log file. The termination message file is now properly
  readable for end users and has a maximum size (4k bytes) to prevent abuse.
  Each pod may have up to 12k bytes of termination messages before the contents
  of each will be truncated.
* Do not delete pod objects until all its compute resource footprint has been
  reclaimed.
  - This feature prevents the node and scheduler from oversubscribing resources
    that are still being used by a pod in the process of being cleaned up.
  - This feature can result in increase of Pod Deletion latency especially if the
    pod has a large filesystem footprint.

### RBAC
* **[beta]** RBAC API is promoted to v1beta1 (rbac.authorization.k8s.io/v1beta1), and defines default roles for control plane, node, and controller components.
* **[beta]** The Docker-CRI implementation is Beta and is enabled by default in kubelet.  You can disable it by `--enable-cri=false`. See [notes on the new implementation]( https://github.com/kubernetes/community/blob/master/contributors/devel/container-runtime-interface.md#kubernetes-v16-release-docker-cri-integration-beta) for more details.

### Scheduling
- **[beta]** The [multiple schedulers](https://kubernetes.io/docs/tutorials/clusters/multiple-schedulers/). This feature allows you to run multiple schedulers in parallel, each responsible for different sets of pods. When using multiple schedulers, the scheduler name is now specified in a new-in-1.6 `schedulerName` field of the PodSpec rather than using the `scheduler.alpha.kubernetes.io/name` annotation on the Pod. When you upgrade to 1.6, the Kubernetes default scheduler will start using the `schedulerName` field of the PodSpec and will ignore the annotation.
- **[beta]** [Node affinity/anti-affinity](https://kubernetes.io/docs/concepts/configuration/assign-pod-node/) and **[beta]** [pod affinity/anti-affinity](https://kubernetes.io/docs/concepts/configuration/assign-pod-node/). Node affinity/anti-affinity allow you to specify rules for restricting which node(s) a pod can schedule onto, based on the labels on the node. Pod affinity/anti-affinity allow you to specify rules for spreading and packing pods relative to one another, across arbitrary topologies (node, zone, etc.) These affinity rules are now be specified in a new-in-1.6 `affinity` field of the PodSpec. Kubernetes 1.6 continues to support the alpha `scheduler.alpha.kubernetes.io/affinity` annotation on the Pod if you explicitly enable the alpha feature "AffinityInAnnotations", but it er than using the `scheduler.alpha.kubernetes.io/tolerations` annotation on the Pod. When you upgrade to 1.6, the scheduler will start using the fields and will ignore the annotations.
- **[alpha]** Represent node problems "not ready" and "unreachable" using `NoExecute` taints. In combination with `tolerationSeconds` described below, this allows per-pod specification of how long to remain bound to a node that becomes unreachable or not ready, rather than using the default of 5 minutes. You can enable this alpha feature by including `TaintBasedEvictions=true` in `--feature-gates`, such as `--feature-gates=FooBar=true,TaintBasedEvictions=true`. Documentation is [here](https://kubernetes.io/docs/concepts/configuration/assign-pod-node/).

### Service Catalog
- **[alpha]** Adds a new API resource `PodPreset` and admission controller to enable defining cross-cutting injection of Volumes and Environment into Pods.

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

### Admission Control
* Adds a new API resource `PodPreset` and admission controller to enable defining cross-cutting injection of Volumes and Environment into Pods. ([#41931](https://github.com/kubernetes/kubernetes/pull/41931), [@jessfraz](https://github.com/jessfraz))
* Enable DefaultTolerationSeconds admission controller by default ([#41815](https://github.com/kubernetes/kubernetes/pull/41815), [@kevin-wangzefeng](https://github.com/kevin-wangzefeng))
* ResourceQuota ability to support default limited resources ([#36765](https://github.com/kubernetes/kubernetes/pull/36765), [@derekwaynecarr](https://github.com/derekwaynecarr))
* Add defaultTolerationSeconds admission controller ([#41414](https://github.com/kubernetes/kubernetes/pull/41414), [@kevin-wangzefeng](https://github.com/kevin-wangzefeng))
* An `automountServiceAccountToken` field was added to ServiceAccount and PodSpec objects. If set to `false` on a pod spec, no service account token is automounted in the pod. If set to `false` on a service account, no service account token is automounted for that service account unless explicitly overridden in the pod spec. ([#37953](https://github.com/kubernetes/kubernetes/pull/37953), [@liggitt](https://github.com/liggitt))
* Admission control support for versioned configuration files ([#39109](https://github.com/kubernetes/kubernetes/pull/39109), [@derekwaynecarr](https://github.com/derekwaynecarr))
* Ability to quota storage by storage class ([#34554](https://github.com/kubernetes/kubernetes/pull/34554), [@derekwaynecarr](https://github.com/derekwaynecarr))

### Authentication
* The authentication.k8s.io API group was promoted to v1([#41058](https://github.com/kubernetes/kubernetes/pull/41058), [@liggitt](https://github.com/liggitt))

### Authorizationub.com/kubernetes/kubernetes/pull/40709), [@liggitt](https://github.com/liggitt))
* The SubjectAccessReview API now passes subresource and resource name information to the authorizer to answer authorization queries. ([#40935](https://github.com/kubernetes/kubernetes/pull/40935), [@liggitt](https://github.com/liggitt))

### Autoscaling
* Introduces an new alpha version of the Horizontal Pod Autoscaler including expanded support for specifying metrics. ([#36033](https://github.com/kubernetes/kubernetes/pull/36033), [@DirectXMan12](https://github.com/DirectXMan12)
* HorizontalPodAutoscaler is no longer supported in extensions/v1beta1 version. Use autoscaling/v1 instead. ([#35782](https://github.com/kubernetes/kubernetes/pull/35782), [@piosz](https://github.com/piosz))
* Fixes an HPA-related panic due to division-by-zero. ([#39694](https://github.com/kubernetes/kubernetes/pull/39694), [@DirectXMan12](https://github.com/DirectXMan12))

### Certificates
* The CertificateSigningRequest API added the `extra` field to persist all information about the requesting user. This mirrors the fields in the SubjectAccessReview API used to check authorization. ([#41755](https://github.com/kubernetes/kubernetes/pull/41755), [@liggitt](https://github.com/liggitt))
* Native support for token based bootstrap flow.  This includes signing a well known ConfigMap in the `kube-public` namespace and cleaning out expired tokens. ([#36101](https://github.com/kubernetes/kubernetes/pull/36101), [@jbeda](https://github.com/jbeda))

### ConfigMap
* Volumes and environment variables populated from ConfigMap and Secret objects can now tolerate the named source object or specific keys being missing, by adding `optional: true` to the volume or environment variable source specifications. ([#39981](https://github.com/kubernetes/kubernetes/pull/39981), [@fraenkel](https://github.com/fraenkel))
* Allow pods to define multiple environment variables from a whole ConfigMap ([#36245](https://github.com/kubernetes/kubernetes/pull/36245), [@fraenkel](https://github.com/fraenkel))

### CronJob
* Add configurable limits to CronJob resource to specify how many successful and failed jobs are preserved. ([#40932](https://github.com/kubernetes/kubernetes/pull/40932), [@peay](https://github.com/peay))

### DaemonSet
* DaemonSet now respects ControllerRef to avoid fighting over Pods. ([#42173](https://github.com/kubernetes/kubernetes/pull/42173), [@enisoc](https://github.com/enisoc))
* Make DaemonSet respect critical pods annotation when scheduling. ([#42028](https://github.com/kubernetes/kubernetes/pull/42028), [@janetkuo](https://github.com/janetkuo))
* Implement the update feature for DaemonSet. ([#41116](https://github.com/kubernetes/kubernetes/pull/41116), [@lukaszo](https://github.com/lukaszo))
* Make DaemonSets survive taint-based evictions when nodes turn unreachable/notReady. ([#41896](https://github.com/kubernetes/kubernetes/pull/41896), [@kevin-wangzefeng](https://github.com/kevin-wangzefeng))
* Make DaemonSet controller respect node taints and pod tolerations. ([#41172](https://github.com/kubernetes/kubernetes/pull/41172), [@janetkuo](https://github.com/janetkuo))
* DaemonSet controller actively kills failed pods (to recreate them) ([#40330](https://github.com/kubernetes/kubernetes/pull/40330), [@janetkuo](https://github.com/janetkuo))
* DaemonSet ObservedGeneration ([#39157](https://github.com/kubernetes/kubernetes/pull/39157), [@lukaszo](https://github.com/lukaszo))

### Deployment
* Add ready replicas in Deployments ([#37959](https://github.com/kubernetes/kubernetes/pull/37959), [@kargakis](https://github.com/kargakis))
* Deployments that cannot make progress in rolling out the newest version will now indicate via the API they are blocked
* Introduce apps/v1beta1.Deployments resource with modified defaults compared to extensions/v1beta1.Deployments. ([#39683](https://github.com/kubernetes/kubernetes/pull/39683), [@soltysh](https://github.com/soltysh))
* Introduce new generator for apps/v1beta1 deployments ([#42362](https://github.com/kubernetes/kubernetes/pull/42362), [@soltysh](https://github.com/soltysh))

### Node
* Set all node conditions to Unknown when node is unreachable ([#36592](https://github.com/kubernetes/kubernetes/pull/36592), [@andrewsykim](https://github.com/andrewsykim))

### Pod
* Init containers have graduated to GA and now appear as a field.  The beta annotation value will still be respected and overrides the field value. ([#38382](https://github.com/kubernetes/kubernetes/pull/38382), [@hodovska](https://github.com/hodovska))
* A new field `terminationMessagePolicy` has been added to containers that allows a user to request `FallbackToLogsOnError`, which will read from the container's logs to populate the termination message if the user does not write to the termination message log file.  The termination message file is now properly readable for end users and has a maximum size (4k bytes) to prevent abuse.  Each pod may have up to 12k bytes of termination messages before the contents of each will be truncated. ([#39341](https://github.com/kubernetes/kubernetes/pull/39341), [@smarterclayton](https://github.com/smarterclayton))
* Fix issue with PodDisruptionBudgets in which `minAvailable` specified as a percentage did not work with StatefulSet Pods. ([#39454](https://github.com/kubernetes/kubernetes/pull/39454), [@foxish](https://github.com/foxish))
* Node affinity has moved from annotations to api fields in the pod spec.  Node affinity that is defined in the annotations will be ignored. ([#37299](https://github.com/kubernetes/kubernetes/pull/37299), [@rrati](https://github.com/rrati))
* Moved pod affinity and anti-affinity from annotations to api fields [#25319](https://github.com/kubernetes/kubernetes/pull/25319) ([#39478](https://github.com/kubernetes/kubernetes/pull/39478), [@rrati](https://github.com/rrati))
* Add QoS pod status field ([#37968](https://github.com/kubernetes/kubernetes/pull/37968), [@sjenning](https://github.com/sjenning))
### Pod Security Policy
* PodSecurityPolicy resource is now enabled by default in the extensions API group. ([#39743](https://github.com/kubernetes/kubernetes/pull/39743), [@pweil-](https://github.com/pweil-))

### RBAC
* The `attributeRestrictions` field has been removed from the PolicyRule type in the rbac.authorization.k8s.io/v1alpha1 API. The field was not used by the RBAC authorizer. ([#39625](https://github.com/kubernetes/kubernetes/pull/39625), [@deads2k](https://github.com/deads2k))
* A user can now be authorized to bind a particular role by having permission to perform the `bind` verb on the referenced role ([#39383](https://github.com/kubernetes/kubernetes/pull/39383), [@liggitt](https://github.com/liggitt))

### ReplicaSet
* ReplicaSet has onwer ref of the Deployment that created it ([#35676](https://github.com/kubernetes/kubernetes/pull/35676), [@krmayankk](https://github.com/krmayankk))

### Secrets
* Populate environment variables from a secrets. ([#39446](https://github.com/kubernetes/kubernetes/pull/39446), [@fraenkel](https://github.com/fraenkel))
* Added a new secret type "bootstrap.kubernetes.io/token" for dynamically creating TLS bootstrapping bearer tokens. ([#41281](https://github.com/kubernetes/kubernetes/pull/41281), [@ericchiang](https://github.com/ericchiang))

### Service
* Endpoints, that tolerate unready Pods, are now listing Pods in state Terminating as well ([#37093](https://github.com/kubernetes/kubernetes/pull/37093), [@simonswine](https://github.com/simonswine))
* Fix Service Update on LoadBalancerSourceRanges Field ([#37720](https://github.com/kubernetes/kubernetes/pull/37720), [@freehan](https://github.com/freehan))
* Bug fix. Incoming UDP packets not reach newly deployed services ([#32561](https://github.com/kubernetes/kubernetes/pull/32561), [@zreigz](https://github.com/zreigz))
* Services of type loadbalancer consume both loadbalancer and nodeport quota. ([#39364](https://github.com/kubernetes/kubernetes/pull/39364), [@zhouhaibing089](https://github.com/zhouhaibing089))

### StatefulSet

* Fix zone placement heuristics so that multiple mounts in a StatefulSet pod are created in the same zone ([#40910](https://github.com/kubernetes/kubernetes/pull/40910), [@justinsb](https://github.com/justinsb))
* Fixes issue [#38418](https://github.com/kubernetes/kubernetes/pull/38418) which, under circumstance, could cause StatefulSet to deadlock. ([#40838](https://github.com/kubernetes/kubernetes/pull/40838), [@kow3ns](https://github.com/kow3ns))
  * Mediates issue [#36859](https://github.com/kubernetes/kubernetes/pull/36859). StatefulSet only acts on Pods whose identity matches the StatefulSet, providing a partial mediation for overlapping controllers.

### Taints and Tolerations
* Add a manager to NodeController that is responsible for removing Pods from Nodes tainted with NoExecute Taints. This feature is beta (as the rest of taints) and enabled by default. It's gated by controller-manager enable-taint-manager flag. ([#40355](https://github.com/kubernetes/kubernetes/pull/40355), [@gmarek](https://github.com/gmarek))
* Add an alpha feature that makes NodeController set Taints instead of deleting Pods from not Ready Nodes. ([#41133](https://github.com/kubernetes/kubernetes/pull/41133), [@gmarek](https://github.com/gmarek))
* Make tolerations respect wildcard key ([#39914](https://github.com/kubernetes/kubernetes/pull/39914), [@kevin-wangzefeng](https://github.com/kevin-wangzefeng))
* Forgiveness alpha version api definition ([#39469](https://github.com/kubernetes/kubernetes/pull/39469), [@kevin-wangzefeng](https://github.com/kevin-wangzefeng))
* Rescheduler uses taints in v1beta1 and will remove old ones (in version v1alpha1) right after its start. ([#43106](https://github.com/kubernetes/kubernetes/pull/43106), [@piosz](https://github.com/piosz))

### Volumes
* StorageClassName attribute has been added to PersistentVolume and PersistentVolumeClaim objects and should be used instead of annotation `volume.beta.kubernetes.io/storage-class`. The beta annotation is still working in this release, however it will be removed in a future release. ([#42128](https://github.com/kubernetes/kubernetes/pull/42128), [@jsafrane](https://github.com/jsafrane))
* Parameter keys in a StorageClass `parameters` map may not use the `kubernetes.io` or `k8s.io` namespaces. ([#41837](https://github.com/kubernetes/kubernetes/pull/41837), [@liggitt](https://github.com/liggitt))
* Add storage.k8s.io/v1 API ([#40088](https://github.com/kubernetes/kubernetes/pull/40088), [@jsafrane](https://github.com/jsafrane))
* Alpha version of dynamic volume provisioning is removed in this release. Annotation ([#40000](https://github.com/kubernetes/kubernetes/pull/40000), [@jsafrane](https://github.com/jsafrane))
    * "volume.alpha.kubernetes.io/storage-class" does not have any special meaning. A default storage class
    * and  DefaultStorageClass admission plugin can be used to preserve similar behavior of Kubernetes cluster,
    * see https://kubernetes.io/docs/user-guide/persistent-volumes/#class-1 for details.
* Reduce verbosity of volume reconciler when attaching volumes ([#36900](https://github.com/kubernetes/kubernetes/pull/36900), [@codablock](https://github.com/codablock))
* We change the default attach_detach_controller sync period to 1 minute to reduce the query frequency through cloud provider to check whether volumes are attached or not. ([#41363](https://github.com/kubernetes/kubernetes/pull/41363), [@jingxu97](https://github.com/jingxu97))

## Changes to Major Components
### API Server
* **`--anonymous-auth` is enabled by default, unless the API server is started with the `AlwaysAllow` authorizer. ([#38706](https://github.com/kubernetes/kubernetes/pull/38706), [@deads2k](https://github.com/deads2k))**
* **When using OIDC authentication and specifying --oidc-username-claim=email, an `"email_verified":true` claim must be returned from the identity provider. ([#36087](https://g//github.com/liggitt))
* API server now has two separate limits for read-only and mutating inflight requests. ([#36064](https://github.com/kubernetes/kubernetes/pull/36064), [@gmarek](https://github.com/gmarek))
* Restored normalization of custom `--etcd-prefix` when `--storage-backend` is set to etcd3 ([#42506](https://github.com/kubernetes/kubernetes/pull/42506), [@liggitt](https://github.com/liggitt))
* Updating apiserver to return http status code 202 for a delete request when the resource is not immediately deleted because of user requesting cascading deletion using DeleteOptions.OrphanDependents=false. ([#41165](https://github.com/kubernetes/kubernetes/pull/41165), [@nikhiljindal](https://github.com/nikhiljindal))
* Use full package path for definition name in OpenAPI spec ([#40124](https://github.com/kubernetes/kubernetes/pull/40124), [@mbohlool](https://github.com/mbohlool))
* Follow redirects for streaming requests (exec/attach/port-forward) in the apiserver by default (alpha -> beta). ([#40039](https://github.com/kubernetes/kubernetes/pull/40039), [@timstclair](https://github.com/timstclair))
* Add 'X-Content-Type-Options: nosniff" to some error messages ([#37190](https://github.com/kubernetes/kubernetes/pull/37190), [@brendandburns](https://github.com/brendandburns))
* Fixes bug in resolving client-requested API versions ([#38533](https://github.com/kubernetes/kubernetes/pull/38533), [@DirectXMan12](https://github.com/DirectXMan12))
* Replace glog.Fatals with fmt.Errorfs ([#38175](https://github.com/kubernetes/kubernetes/pull/38175), [@sttts](https://github.com/sttts))
* Pipe get options to storage ([#37693](https://github.com/kubernetes/kubernetes/pull/37693), [@wojtek-t](https://github.com/wojtek-t))
* The --long-running-request-regexp flag to kube-apiserver is deprecated and will be removed in a future release. Long-running requests are now detected based on specific verbs (watch, proxy) or subresources (proxy, portforward, log, exec, attach). ([#38119](https://github.com/kubernetes/kubernetes/pull/38119), [@liggitt](https://github.com/liggitt))
* if kube-apiserver is started with `--storage-backend=etcd2`, the media type `application/json` is used. ([#43122](https://github.com/kubernetes/kubernetes/pull/43122), [@liggitt](https://github.com/liggitt))
* API fields that previously serialized null arrays as `null` and empty arrays as `[]` no longer distinguish between those values and always output `[]` when serializing to JSON. ([#43422](https://github.com/kubernetes/kubernetes/pull/43422), [@liggitt](https://github.com/liggitt))
* Generate OpenAPI definition for inlined types ([#39466](https://github.com/kubernetes/kubernetes/pull/39466), [@mbohlool](https://github.com/mbohlool))

### API Server Aggregator
* Rename kubernetes-discovery to kube-aggregator ([#39619](https://github.com/kubernetes/kubernetes/pull/39619), [@deads2k](https://github.com/deads2k))
* Fix connection upgrades through kuberentes-discovery ([#38724](https://github.com/kubernetes/kubernetes/pull/38724), [@deads2k](https://github.com/deads2k))

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

### Client
* Use Prometheus instrumentation conventions ([#36704](https://github.com/kubernetes/kubernetes/pull/36704), [@fabxc](https://github.com/fabxc))
* Clients now use the `?watch=true` parameter to make watch API calls, instead of the `/watch/` path prefix ([#41722](https://github.com/kubernetes/kubernetes/pull/41722), [@liggitt](https://github.com/liggitt))
* Move private key parsing from serviceaccount/jwt.go to client-go/util/cert ([#40907](https://github.com/kubernetes/kubernetes/pull/40907), [@cblecker](https://github.com/cblecker))
* Caching added to the OIDC client auth plugin to fix races and reduce the time kubectl commands using this plugin take by several seconds. ([#38167](https://github.com/kubernetes/kubernetes/pull/38167), [@ericchiang](https://github.com/ericchiang))
* Fix resync goroutine leak in ListAndWatch ([#35672](https://github.com/kubernetes/kubernetes/pull/35672), [@tatsuhiro-t](https://github.com/tatsuhiro-t))

#### client-go
* The main repository does not keep multiple releases of clientsets anymore. Please find previous releases at https://github.com/kubernetes/client-go ([#38154](https://github.com/kubernetes/kubernetes/pull/38154), [@caesarxuchao](https://github.com/caesarxuchao))
* Support whitespace in command path for gcp auth plugin ([#41653](https://github.com/kubernetes/kubernetes/pull/41653), [@jlowdermilk](https://github.com/jlowdermilk))
* client-go no longer imports GCP OAuth2 and OpenID Connect packages by default. ([#41532](https://github.com/kubernetes/kubernetes/pull/41532), [@ericchiang](https://github.com/ericchiang))
* Added bool type support for jsonpath. ([#39063](https://github.com/kubernetes/kubernetes/pull/39063), [@xingzhou](https://github.com/xingzhou))
* Preventing nil pointer reference in client_config ([#40508](https://github.com/kubernetes/kubernetes/pull/40508), [@vjsamuel](https://github.com/vjsamuel))
* Prevent hotloops on error conditions, which could fill up the disk faster than log rotation can free space. ([#40497](https://github.com/kubernetes/kubernetes/pull/40497), [@lavalamp](https://github.com/lavalamp))

### Cloud Provider

#### AWS
* Allow to running the master with a different AWS account or even on a different cloud provider than the nodes. ([#39996](https://github.com/kubernetes/kubernetes/pull/39996), [@scheeles](https://github.com/scheeles))
* Support shared tag `kubernetes.io/cluster/<clusterid>` ([#41695](https://github.com/kubernetes/kubernetes/pull/41695), [@justinsb](https://github.com/justinsb))
* Do not consider master instance zones for dynamic volume creation ([#41702](https://github.com/kubernetes/kubernetes/pull/41702), [@justinsb](https://github.com/justinsb))
* Fix AWS device allocator to only use valid device names ([#41455](https://github.com/kubernetes/kubernetes/pull/41455), [@gnufied](https://github.com/gnufied))
* Trust region if found from AWS metadata ([#38880](https://github.com/kubernetes/kubernetes/pull/38880), [@justinsb](https://github.com/justinsb))
* Remove duplicate calls to DescribeInstance during volume operations ([#39842](https://github.com/kubernetes/kubernetes/pull/39842), [@gnufied](https://github.com/gnufied))
* Recognize eu-west-2 region ([#38746](https://github.com/kubernetes/kubernetes/pull/38746), [@justinsb](https://github.com/justinsb))
* Recognize ca-central-1 region ([#38410](https://github.com/kubernetes/kubernetes/pull/38410), [@justinsb](https://github.com/justinsb))
* Add sequential allocator for device names. ([#38818](https://github.com/kubernetes/kubernetes/pull/38818), [@jsafrane](https://github.com/jsafrane))

#### Azure
* Fix failing load balancers in Azure ([#40405](https://github.com/kubernetes/kubernetes/pull/40405), [@codablock](https://github.com/codablock))
* Reduce time needed to attach Azure disks ([#40066](https://github.com/kubernetes/kubernetes/pull/40066), [@codablock](https://github.com/codablock))
* Remove Azure Subnet RouteTable check ([#38334](https://github.com/kubernetes/kubernetes/pull/38334), [@mogthesprog](https://github.com/mogthesprog))
* Add support for Azure Container Registry, update Azure dependencies ([#37783](https://github.com/kubernetes/kubernetes/pull/37783), [@brendandburns](https://github.com/brendandburns))
* Allow backendpools in Azure Load Balancers which are not owned by cloud provider ([#36882](https://github.com/kubernetes/kubernetes/pull/36882), [@codablock](https://github.com/codablock))

#### GCE
* On GCI by default logrotate is disabled for application containers in favor of rotation mechanism provided by docker logging driver. ([#40634](https://github.com/kubernetes/kubernetes/pull/40634), [@crassirostris](https://github.com/crassirostris))

#### GKE
* New GKE certificates controller. ([#41160](https://github.com/kubernetes/kubernetes/pull/41160), [@pipejakob](https://github.com/pipejakob))

#### vSphere
* Reverts to looking up the current VM in vSphere using the machine's UUID, either obtained via sysfs or via the `vm-uuid` parameter in the cloud configuration file. ([#40892](https://github.com/kubernetes/kubernetes/pull/40892), [@robdaemon](https://github.com/robdaemon))
* Fix for detach volume when node is not present/ powered off ([#40118](https://github.com/kubernetes/kubernetes/pull/40118), [@BaluDontu](https://github.com/BaluDontu))
* Adding vmdk file extension for vmDiskPath in vsphere DeleteVolume ([#40538](https://github.com/kubernetes/kubernetes/pull/40538), [@divyenpatel](https://github.com/divyenpatel))
* Changed default scsi controller type in vSphere Cloud Provider ([#38426](https://github.com/kubernetes/kubernetes/pull/38426), [@abrarshivani](https://github.com/abrarshivani))
* Fixes NotAuthenticated errors that appear in the kubelet and kube-controller-manager due to never logging in to vSphere ([#36169](https://github.com/kubernetes/kubernetes/pull/36169), [@robdaemon](https://github.com/robdaemon))
* Fix panic in vSphere cloud provider ([#38423](https://github.com/kubernetes/kubernetes/pull/38423), [@BaluDontu](https://github.com/BaluDontu))
* Fix space issue in volumePath with vSphere Cloud Provider ([#38338](https://github.com/kubernetes/kubernetes/pull/38338), [@BaluDontu](https://github.com/BaluDontu))

### Federation

#### kubefed
* Flag cleanup ([#41335](https://github.com/kubernetes/kubernetes/pull/41335), [@irfanurrehman](https://github.com/irfanurrehman))
* Create configmap for the cluster kube-dns when cluster joins and remove when it unjoins ([#39338](https://github.com/kubernetes/kubernetes/pull/39338), [@irfanurrehman](https://github.com/irfanurrehman))
* Support configuring dns-provider ([#40528](https://github.com/kubernetes/kubernetes/pull/40528), [@shashidharatd](https://github.com/shashidharatd))
* Bug fix relating kubeconfig path in kubefed init ([#41410](https://github.com/kubernetes/kubernetes/pull/41410), [@irfanurrehman](https://github.com/irfanurrehman))
* Add override flags options to kubefed init ([#40917](https://github.com/kubernetes/kubernetes/pull/40917), [@irfanurrehman](https://github.com/irfanurrehman))
* Add option to expose federation apiserver on nodeport service ([#40516](https://github.com/kubernetes/kubernetes/pull/40516), [@shashidharatd](https://github.com/shashidharatd))
* Add option to disable persistence storage for etcd ([#40862](https://github.com/kubernetes/kubernetes/pull/40862), [@shashidharatd](https://github.com/shashidharatd))
* kubefed init creates a service account for federation controller manager in the federation-system namespace and binds that service account to the federation-system:federation-controller-manager role that has read and list access on secrets in the federation-system namespace.  ([#40392](https://github.com/kubernetes/kubernetes/pull/40392), [@madhusudancs](https://github.com/madhusudancs))
* Implement dry run support in kubefed init ([#36447](https://github.com/kubernetes/kubernetes/pull/36447), [@irfanurrehman](https://github.com/irfanurrehman))
* Make federation etcd PVC size configurable ([#36310](https://github.com/kubernetes/kubernetes/pull/36310), [@irfanurrehman](https://github.com/irfanurrehman))

#### Other Notable Changes
* Federated Ingress over GCE no longer requires separate firewall rules to be created for each cluster to circumvent flapping firewall health checks. ([#41942](https://github.com/kubernetes/kubernetes/pull/41942), [@csbell](https://github.com/csbell))
* Add support for finalizers in federated configmaps (deletes configmaps from underlying clusters). ([#40464](https://github.com/kubernetes/kubernetes/pull/40464), [@csbell](https://github.com/csbell))
* Add support for DeleteOptions.OrphanDependents for federated services. Setting it to false while deleting a federated service also deletes the corresponding services from all registered clusters. ([#36390](https://github.com/kubernetes/kubernetes/pull/36390), [@nikhiljindal](https://github.com/nikhiljindal))
* Add `--controllers` flag to federation controller manager for enable/disable federation ingress controller ([#36643](https://github.com/kubernetes/kubernetes/pull/36643), [@kzwang](https://github.com/kzwang))
* Stop deleting services from underlying clusters when federated service is deleted. ([#37353](https://github.com/kubernetes/kubernetes/pull/37353), [@nikhiljindal](https://github.com/nikhiljindal))
* Expose autoscaling apis through federation api server ([#38976](https://github.com/kubernetes/kubernetes/pull/38976), [@irfanurrehman](https://github.com/irfanurrehman))
* Federation: Add `batch/jobs` API objects to federation-apiserver ([#35943](https://github.com/kubernetes/kubernetes/pull/35943), [@jianhuiz](https://github.com/jianhuiz))
* Add logging of route53 calls ([#39964](https://github.com/kubernetes/kubernetes/pull/39964), [@justinsb](https://github.com/justinsb))

### Garbage Collector
* Added foreground garbage collection: the owner object will not be deleted until all its dependents are deleted by the garbage collector. Please checkout the [user doc](https://kubernetes.io/docs/concepts/abstractions/controllers/garbage-collection/) for details. ([#38676](https://github.com/kubernetes/kubernetes/pull/38676), [@caesarxuchao](https://github.com/caesarxuchao))
  * deleteOptions.orphanDependents is going to be deprecated in 1.7. Please use deleteOptions.propagationPolicy instead.

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

#### Create subcommands
  - `create poddisruptionbudget` ([#36646](https://github.com/kubernetes/kubernetes/pull/36646), [@kargakis](https://github.com/kargakis))
  - `create clusterrole` ([#41538](https://github.com/kubernetes/kubernetes/pull/41538), [@xingzhou](https://github.com/xingzhou))
  - `create role` ([#39852](https://github.com/kubernetes/kubernetes/pull/39852), [@xingzhou](https://github.com/xingzhou))
  - `create clusterrolebinding` ([#37098](https://github.com/kubernetes/kubernetes/pull/37098), [@deads2k](https://github.com/deads2k))
  - `create service externalname` ([#34789](https://github.com/kubernetes/kubernetes/pull/34789), [@adohe](https://github.com/adohe))
- `set selector` - update selector labels ([#38966](https://github.com/kubernetes/kubernetes/pull/38966), [@kargakis](https://github.com/kargakis))
- `can-i` to see if you can perform an action ([#41077](https://github.com/kubernetes/kubernetes/pull/41077), [@deads2k](https://github.com/deads2k))

#### Updates to existing commands
* Printing and output
  * Import a numeric ordering sorting library and use it in the sorting printer. ([#40746](https://github.com/kubernetes/kubernetes/pull/40746), [@matthyx](https://github.com/matthyx))
  * DaemonSet get and describe show status fields.  ([#42843](https://github.com/kubernetes/kubernetes/pull/42843), [@janetkuo](https://github.com/janetkuo))
  * Pods describe shows tolerationSeconds ([#42162](https://github.com/kubernetes/kubernetes/pull/42162), [@kevin-wangzefeng](https://github.com/kevin-wangzefeng))
  * Node describe contains closing paren ([#39217](https://github.com/kubernetes/kubernetes/pull/39217), [@luksa](https://github.com/luksa))
  * Display pod node selectors with kubectl describe. ([#36396](https://github.com/kubernetes/kubernetes/pull/36396), [@aveshagarwal](https://github.com/aveshagarwal))
  * Add Version to the resource printer for 'get nodes' ([#37943](https://github.com/kubernetes/kubernetes/pull/37943), [@ailusazh](https://github.com/ailusazh))
  * Added support for printing in all supported `--output` formats to `kubectl create ...` and `kubectl apply ...` ([#38112](https://github.com/kubernetes/kubernetes/pull/38112), [@juanvallejo](https://github.com/juanvallejo))
  * Add three more columns to `kubectl get deploy -o wide` output. ([#39240](https://github.com/kubernetes/kubernetes/pull/39240), [@xingzhou](https://github.com/xingzhou))
  * Fix kubectl get -f <file> -o <nondefault printer> so it prints all items in the file ([#39038](https://github.com/kubernetes/kubernetes/pull/39038), [@ncdc](https://github.com/ncdc))
  * kubectl describe no longer prints the last-applied-configuration annotation for secrets. ([#34664](https://github.com/kubernetes/kubernetes/pull/34664), [@ymqytw](https://github.com/ymqytw))
  * Completed pods should not be hidden when requested by name via `kubectl get`. ([#42216](https://github.com/kubernetes/kubernetes/pull/42216), [@smarterclayton](https://github.com/smarterclayton))
  * Improve formatting of EventSource in kubectl get and kubectl describe ([#40073](https://github.com/kubernetes/kubernetes/pull/40073), [@matthyx](https://github.com/matthyx))
* Attach now supports multiple types ([#40365](https://github.com/kubernetes/kubernetes/pull/40365), [@shiywang](https://github.com/shiywang))
* Create now accepts the label selector flag for filtering objects to create ([#40057](https://github.com/kubernetes/kubernetes/pull/40057), [@MrHohn](https://github.com/MrHohn))
* Top now accepts short forms for "node" and "pod" ("no", "po") ([#39218](https://github.com/kubernetes/kubernetes/pull/39218), [@luksa](https://github.com/luksa))
* Begin paths for internationalization in kubectl ([#36802](https://github.com/kubernetes/kubernetes/pull/36802), [@brendandburns](https://github.com/brendandburns))
  * Add initial french translations for kubectl ([#40645](https://github.com/kubernetes/kubernetes/pull/40645), [@brendandburns](https://github.com/brendandburns))

#### Updates to apply
* New command `apply set-last-applied` *updates the applied-applied-configuration annotation* ([#41694](https://github.com/kubernetes/kubernetes/pull/41694), [@shiywang](https://github.com/shiywang))
* New command `apply view-last-applied` *command for viewing the last configuration file applied* ([#41146](https://github.com/kubernetes/kubernetes/pull/41146), [@shiywang](https://github.com/shiywang))
* `apply` now supports explicitly clearing values by setting them to null ([#40630](https://github.com/kubernetes/kubernetes/pull/40630), [@liggitt](https://github.com/liggitt))
* Warn user when using `apply` on a resource lacking the `LastAppliedConfig` annotation ([#36672](https://github.com/kubernetes/kubernetes/pull/36672), [@ymqytw](https://github.com/ymqytw))
* PATCH (i.e. apply and edit) now supports merging lists of primitives ([#38665](https://github.com/kubernetes/kubernetes/pull/38665), [@ymqytw](https://github.com/ymqytw))
* `apply` falls back to generic 3-way JSON merge patch for Third Party Resource or unregistered types ([#40666](https://github.com/kubernetes/kubernetes/pull/40666), [@ymqytw](https://github.com/ymqytw))

#### Updates to edit
* `edit` now supports Third party resources and extension API servers. ([#41304](https://github.com/kubernetes/kubernetes/pull/41304), [@liggitt](https://github.com/liggitt))
  * Now to edit a particular API version, provide the fully-qualify the resource, version, and group used to fetch the object (for example, `job.v1.batch/myjob`)
  * Client-side conversion is no longer done, and the `--output-version` option is deprecated for `kubectl edit`.
* `edit` works as intended with apply and will not change the annotation
  * No longer updates the last-applied-configuration annotation when --save-config is unspecified or false. ([#41924](https://github.com/kubernetes/kubernetes/pull/41924), [@ymqytw](https://github.com/ymqytw))
  * Fixes issue that caused apply to revert changes made by edit

#### Bug fixes
* Fixed --save-config in create subcommand to save the annotation ([#40289](https://github.com/kubernetes/kubernetes/pull/40289), [@xilabao](https://github.com/xilabao))
* Fixed an issue where 'kubectl get --sort-by=' would return an error if the specified fields in sort were not specified in one or more of the returned objects. ([#40541](https://github.com/kubernetes/kubernetes/pull/40541), [@fabianofranz](https://github.com/fabianofranz))
  * Previously this would cause the command to fail regardless of whether or not the field was present in the object model
  * Now the command will succeed even if the sort-by field is missing from one or more of the objects
* Fixed issue with kubectl proxy so it will now proxy an empty path - e.g. http://localhost:8001 ([#39226](https://github.com/kubernetes/kubernetes/pull/39226), [@luksa](https://github.com/luksa))
* Fixed an issue where commas were not accepted in --from-literal flags for the creation of secrets. ([#35191](https://github.com/kubernetes/kubernetes/pull/35191), [@SamiHiltunen](https://github.com/SamiHiltunen))
  * Passing multiple values separated by a comma in a single --from-literal flag is no longer supported. Please use multiple --from-literal flags to provide multiple values.
* Fixed a bug where the --server, --token, and --certificate-authority flags were not overriding the related in-cluster configs when provided in a `kubectl` call inside a cluster. ([#39006](https://github.com/kubernetes/kubernetes/pull/39006), [@fabianofranz](https://github.com/fabianofranz))

#### Other Notable Changes
* The api server will publish the extensions/Deployments API as preferred over the apps/Deployment (introduced in 1.6). ([#43553](https://github.com/kubernetes/kubernetes/pull/43553), [@liggitt](https://github.com/liggitt))
  * This will ensure certain commands in 1.5 versions of kubectl continue function when run against a 1.6 server. (e.g. `kubectl edit deployment`)
* Taint
  * The `taint` command will not function in a skewed 1.5 / 1.6 environment - client and server versions must match (See Action required section above)
  * Change taints/tolerations to api fields ([#38957](https://github.com/kubernetes/kubernetes/pull/38957), [@aveshagarwal](https://github.com/aveshagarwal))
  * Make kubectl taint command respect effect NoExecute ([#42120](https://github.com/kubernetes/kubernetes/pull/42120), [@kevin-wangzefeng](https://github.com/kevin-wangzefeng))
* Allow drain --force to remove pods whose managing resource is deleted. ([#41864](https://github.com/kubernetes/kubernetes/pull/41864), [@marun](https://github.com/marun))
* `--output-version` is ignored for all commands except `kubectl convert`.  This is consistent with the generic nature of `kubectl` CRUD commands and the previous removal of `--api-version`.  Specific versions can be specified in the resource field: `resource.version.group`, `jobs.v1.batch`. ([#41576](https://github.com/kubernetes/kubernetes/pull/41576), [@deads2k](https://github.com/deads2k))
* Allow missing keys in templates by default ([#39486](https://github.com/kubernetes/kubernetes/pull/39486), [@ncdc](https://github.com/ncdc))
* Add error message when trying to use clusterrole with namespace in kubectl ([#36424](https://github.com/kubernetes/kubernetes/pull/36424), [@xilabao](https://github.com/xilabao))
* When deleting an object with `--grace-period=0`, the client will begin a graceful deletion and wait until the resource is fully deleted.  To force deletion, use the `--force` flag. ([#37263](https://github.com/kubernetes/kubernetes/pull/37263), [@smarterclayton](https://github.com/smarterclayton))

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

### kube-proxy
* **- Add tcp/udp userspace proxy support for Windows. ([#41487](https://github.com/kubernetes/kubernetes/pull/41487), [@anhowe](https://github.com/anhowe))**
* Add DNS suffix search list support in Windows kube-proxy. ([#41618](https://github.com/kubernetes/kubernetes/pull/41618), [@JiangtianLi](https://github.com/JiangtianLi))
* Add a KUBERNETES_NODE_* section to build kubelet/kube-proxy for windows ([#38919](https://github.com/kubernetes/kubernetes/pull/38919), [@brendandburns](https://github.com/brendandburns))
* Remove outdated net.experimental.kubernetes.io/proxy-mode and net.beta.kubernetes.io/proxy-mode annotations from kube-proxy. ([#40585](https://github.com/kubernetes/kubernetes/pull/40585), [@cblecker](https://github.com/cblecker))
* proxy/iptables: don't sync proxy rules if services map didn't change ([#38996](https://github.com/kubernetes/kubernetes/pull/38996), [@dcbw](https://github.com/dcbw))
* Update kube-proxy image to be based off of Debian 8.6 base image. ([#39695](https://github.com/kubernetes/kubernetes/pull/39695), [@ixdy](https://github.com/ixdy))
* Update amd64 kube-proxy base image to debian-iptables-amd64:v5 ([#39725](https://github.com/kubernetes/kubernetes/pull/39725), [@ixdy](https://github.com/ixdy))
* Clean up the kube-proxy container image by removing unnecessary packages and files. ([#42090](https://github.com/kubernetes/kubernetes/pull/42090), [@timstclair](https://github.com/timstclair))
* Better compat with very old iptables (e.g. CentOS 6) ([#37594](https://github.com/kubernetes/kubernetes/pull/37594), [@thockin](https://github.com/thockin))

### Scheduler
* Add the support to the scheduler for spreading pods of StatefulSets. ([#41708](https://github.com/kubernetes/kubernetes/pull/41708), [@bsalamat](https://github.com/bsalamat))
* Added support to minimize sending verbose node information to scheduler extender by sending only node names and expecting extenders to cache the rest of the node information ([#41119](https://github.com/kubernetes/kubernetes/pull/41119), [@sarat-k](https://github.com/sarat-k))
* Support KUBE_MAX_PD_VOLS on Azure ([#41398](https://github.com/kubernetes/kubernetes/pull/41398), [@codablock](https://github.com/codablock))
* Mark multi-scheduler graduation to beta and then v1. ([#38871](https://github.com/kubernetes/kubernetes/pull/38871), [@k82cn](https://github.com/k82cn))
* Scheduler treats StatefulSet pods as belonging to a single equivalence class. ([#39718](https://github.com/kubernetes/kubernetes/pull/39718), [@foxish](https://github.com/foxish))
* Update FitError as a message component into the PodConditionUpdater. ([#39491](https://github.com/kubernetes/kubernetes/pull/39491), [@jayunit100](https://github.com/jayunit100))
* Fix comment and optimize code ([#38084](https://github.com/kubernetes/kubernetes/pull/38084), [@tanshanshan](https://github.com/tanshanshan))
* Add flag to enable contention profiling in scheduler. ([#37357](https://github.com/kubernetes/kubernetes/pull/37357), [@gmarek](https://github.com/gmarek))
* Try self-repair scheduler cache or panic ([#37379](https://github.com/kubernetes/kubernetes/pull/37379), [@wojtek-t](https://github.com/wojtek-t))

### Volume Plugins

#### Azure Disk
* restrict name length for Azure specifications ([#40030](https://github.com/kubernetes/kubernetes/pull/40030), [@colemickens](https://github.com/colemickens))

#### GlusterFS
* The glusterfs dynamic volume provisioner will now choose a unique GID for new persistent volumes from a range that can be configured in the storage class with the "gidMin" and "gidMax" parameters. The default range is 2000 - 2147483647 (max int32). ([#37886](https://github.com/kubernetes/kubernetes/pull/37886), [@obnoxxx](https://github.com/obnoxxx))

#### Photon
* Fix photon controller plugin to construct with correct PdID ([#37167](https://github.com/kubernetes/kubernetes/pull/37167), [@luomiao](https://github.com/luomiao))

#### rbd
* force unlock rbd image if the image is not used ([#41597](https://github.com/kubernetes/kubernetes/pull/41597), [@rootfs](https://github.com/rootfs))

#### vSphere
* Fix fsGroup to vSphere ([#38655](https://github.com/kubernetes/kubernetes/pull/38655), [@abrarshivani](https://github.com/abrarshivani))
* Fix issue when attempting to unmount a wrong vSphere volume ([#37413](https://github.com/kubernetes/kubernetes/pull/37413), [@BaluDontu](https://github.com/BaluDontu))

#### Other Notable Changes
* Implement bulk polling of volumes ([#41306](https://github.com/kubernetes/kubernetes/pull/41306), [@gnufied](https://github.com/gnufied))
* Check if pathExists before performing Unmount ([#39311](https://github.com/kubernetes/kubernetes/pull/39311), [@rkouj](https://github.com/rkouj))
* Unmount operation should not fail if volume is already unmounted ([#38547](https://github.com/kubernetes/kubernetes/pull/38547), [@rkouj](https://github.com/rkouj))
* Provide kubernetes-controller-manager flags to control volume attach/detach reconciler sync.  The duration of the syncs can be controlled, and the syncs can be shut off as well. ([#39551](https://github.com/kubernetes/kubernetes/pull/39551), [@chrislovecnm](https://github.com/chrislovecnm))
* Fix unmountDevice issue caused by shared mount in GCI ([#38411](https://github.com/kubernetes/kubernetes/pull/38411), [@jingxu97](https://github.com/jingxu97))
* Fix permissions when using fsGroup ([#37009](https://github.com/kubernetes/kubernetes/pull/37009), [@sjenning](https://github.com/sjenning))
* Fixed issues ([#39202](https://github.com/kubernetes/kubernetes/pull/39202)), ([#41041](https://github.com/kubernetes/kubernetes/pull/41041)) and ([#40941](https://github.com/kubernetes/kubernetes/pull/40941)) that caused the iSCSI connections to
  be prematurely closed when deleting a pod with an iSCSI persistent volume attached and that prevented the use of newly created LUNs on targets with preestablished connections. ([#41196](https://github.com/kubernetes/kubernetes/pull/41196)), [@CristianPop](https://github.com/CristianPop))

## Changes to Cluster Provisioning Scripts

### AWS
* Deployment of AWS Kubernetes clusters using the in-tree bash deployment (i.e. cluster/kube-up.sh or get-kube.sh) is obsolete. v1.5.x will be the last release to support cluster/kube-up.sh with AWS. For a list of viable alternatives, see: http://kubernetes.io/docs/getting-started-guides/aws/  ([#42196](https://github.com/kubernetes/kubernetes/pull/42196), [@zmerlynn](https://github.com/zmerlynn))
* Fix an issue where AWS tear-down leaks an DHCP Option Set. ([#38645](https://github.com/kubernetes/kubernetes/pull/38645), [@zmerlynn](https://github.com/zmerlynn))

### Juju
* The kubernetes-master, kubernetes-worker and kubeapi-load-balancer charms have gained an nrpe-external-master relation, allowing the integration of their monitoring in an external Nagios server. ([#41923](https://github.com/kubernetes/kubernetes/pull/41923), [@Cynerva](https://github.com/Cynerva))
* Disable anonymous auth on kubelet ([#41919](https://github.com/kubernetes/kubernetes/pull/41919), [@Cynerva](https://github.com/Cynerva))
* Fix shebangs in charm actions to use python3 ([#42058](https://github.com/kubernetes/kubernetes/pull/42058), [@Cynerva](https://github.com/Cynerva))
* K8s master charm now properly keeps distributed master files in sync for an HA control plane. ([#41351](https://github.com/kubernetes/kubernetes/pull/41351), [@chuckbutler](https://github.com/chuckbutler))
* Improve status messages ([#40691](https://github.com/kubernetes/kubernetes/pull/40691), [@Cynerva](https://github.com/Cynerva))
* Splits Juju Charm layers into master/worker roles ([#40324](https://github.com/kubernetes/kubernetes/pull/40324), [@chuckbutler](https://github.com/chuckbutler))
    * Adds support for 1.5.x series of Kubernetes
    * Introduces a tactic for keeping templates in sync with upstream eliminating template drift
    * Adds CNI support to the Juju Charms
    * Adds durable storage support to the Juju Charms
    * Introduces an e2e Charm layer for repeatable testing efforts and validation of clusters

### libvirt CoreOS
* To add local registry to libvirt_coreos ([#36751](https://github.com/kubernetes/kubernetes/pull/36751), [@sdminonne](https://github.com/sdminonne))

### GCE
* **the `gce` provider enables both RBAC authorization and the permissive legacy ABAC policy that makes all service accounts superusers. To opt out of the permissive ABAC policy, export the environment variable `ENABLE_LEGACY_ABAC=false` before running `cluster/kube-up.sh`. ([#43544](https://github.com/kubernetes/kubernetes/pull/43544), [@liggitt](https://github.com/liggitt))**
* **the `gce` provider ensures the bootstrap admin token user is included in the super-user group ([#39537](https://github.com/kubernetes/kubernetes/pull/39537), [@liggitt](https://github.com/liggitt))**
* Remove support for debian masters in GCE kube-up. ([#41666](https://github.com/kubernetes/kubernetes/pull/41666), [@mikedanese](https://github.com/mikedanese))
* Remove support for trusty in GCE kube-up. ([#41670](https://github.com/kubernetes/kubernetes/pull/41670), [@mikedanese](https://github.com/mikedanese))
* Don't fail if the grep fails to match any resources ([#41933](https://github.com/kubernetes/kubernetes/pull/41933), [@ixdy](https://github.com/ixdy))
* Fix the output of health-mointor.sh ([#41525](https://github.com/kubernetes/kubernetes/pull/41525), [@yujuhong](https://github.com/yujuhong))
* Added configurable etcd initial-cluster-state to kube-up script. ([#41332](https://github.com/kubernetes/kubernetes/pull/41332), [@jszczepkowski](https://github.com/jszczepkowski))
* The kube-apiserver [basic audit log](https://kubernetes.io/docs/admin/audit/) can be enabled in GCE by exporting the environment variable `ENABLE_APISERVER_BASIC_AUDIT=true` before running `cluster/kube-up.sh`. This will log to `/var/log/kube-apiserver-audit.log` and use the same `logrotate` settings as `/var/log/kube-apiserver.log`. ([#41211](https://github.com/kubernetes/kubernetes/pull/41211), [@enisoc](https://github.com/enisoc))
* On kube-up.sh clusters on GCE, kube-scheduler now contacts the API on the secured port. ([#41285](https://github.com/kubernetes/kubernetes/pull/41285), [@liggitt](https://github.com/liggitt))
* Use existing ABAC policy file when upgrading GCE cluster ([#40172](https://github.com/kubernetes/kubernetes/pull/40172), [@liggitt](https://github.com/liggitt))
* Ensure the GCI metadata files do not have newline at the end ([#38727](https://github.com/kubernetes/kubernetes/pull/38727), [@Amey-D](https://github.com/Amey-D))
* Fixed detection of master during creation of multizone nodes cluster by kube-up. ([#38617](https://github.com/kubernetes/kubernetes/pull/38617), [@jszczepkowski](https://github.com/jszczepkowski))
* Fixed validation of multizone cluster for GCE ([#38695](https://github.com/kubernetes/kubernetes/pull/38695), [@jszczepkowski](https://github.com/jszczepkowski))
* Fix GCI mounter issue ([#38124](https://github.com/kubernetes/kubernetes/pull/38124), [@jingxu97](https://github.com/jingxu97))
* Exit with error if <version number or publication> is not the final parameter. ([#37723](https://github.com/kubernetes/kubernetes/pull/37723), [@mtaufen](https://github.com/mtaufen))
* GCI: Remove /var/lib/docker/network ([#37593](https://github.com/kubernetes/kubernetes/pull/37593), [@yujuhong](https://github.com/yujuhong))
* Fix the equality checks for numeric values in cluster/gce/util.sh. ([#37638](https://github.com/kubernetes/kubernetes/pull/37638), [@roberthbailey](https://github.com/roberthbailey))
* Modify GCI mounter to enable NFSv3 ([#37582](https://github.com/kubernetes/kubernetes/pull/37582), [@jingxu97](https://github.com/jingxu97))
* Use gsed on the Mac ([#37562](https://github.com/kubernetes/kubernetes/pull/37562), [@roberthbailey](https://github.com/roberthbailey))
* Bump GCI
* to gci-beta-56-9000-80-0 ([#41027](https://github.com/kubernetes/kubernetes/pull/41027), [@dchen1107](https://github.com/dchen1107))
* to gci-stable-56-9000-84-2 ([#41819](https://github.com/kubernetes/kubernetes/pull/41819), [@dchen1107](https://github.com/dchen1107))
* Bump GCE ContainerVM
  * to container-vm-v20161208 ([release notes](https://cloud.google.com/compute/docs/containers/container_vms#changelog)) ([#38432](https://github.com/kubernetes/kubernetes/pull/38432), [@timstclair](https://github.com/timstclair))
  * to container-vm-v20170201 to address CVE-2016-9962. ([#40828](https://github.com/kubernetes/kubernetes/pull/40828), [@zmerlynn](https://github.com/zmerlynn))
  * to container-vm-v20170117 to pick up CVE fixes in base image. ([#40094](https://github.com/kubernetes/kubernetes/pull/40094), [@zmerlynn](https://github.com/zmerlynn))
  * to container-vm-v20170214 to address CVE-2016-9962. ([#41449](https://github.com/kubernetes/kubernetes/pull/41449), [@zmerlynn](https://github.com/zmerlynn))

### OpenStack
* Do not daemonize `salt-minion` for the openstack-heat provider. ([#40722](https://github.com/kubernetes/kubernetes/pull/40722), [@micmro](https://github.com/micmro))
* OpenStack-Heat will now look for an image named "CentOS-7-x86_64-GenericCloud-1604". To restore the previous behavior set OPENSTACK_IMAGE_NAME="CentOS7" ([#40368](https://github.com/kubernetes/kubernetes/pull/40368), [@sc68cal](https://github.com/sc68cal))
* Fixes a bug in the OpenStack-Heat kubernetes provider, in the handling of differences between the Identity v2 and Identity v3 APIs ([#40105](https://github.com/kubernetes/kubernetes/pull/40105), [@sc68cal](https://github.com/sc68cal))

### Container Images
* Update gcr.io/google-containers/rescheduler to v0.2.2, which uses busybox as a base image instead of ubuntu. ([#41911](https://github.com/kubernetes/kubernetes/pull/41911), [@ixdy](https://github.com/ixdy))
* Remove unnecessary metrics (http/process/go) from being exposed by etcd-version-monitor ([#41807](https://github.com/kubernetes/kubernetes/pull/41807), [@shyamjvs](https://github.com/shyamjvs))
* Align the hyperkube image to support running binaries at /usr/local/bin/ like the other server images ([#41017](https://github.com/kubernetes/kubernetes/pull/41017), [@luxas](https://github.com/luxas))
* Bump up GLBC version from 0.9.0-beta to 0.9.1 ([#41037](https://github.com/kubernetes/kubernetes/pull/41037), [@bprashanth](https://github.com/bprashanth))

### Other Notable Changes
* The default client certificate generated by kube-up now contains the superuser `system:masters` group ([#39966](https://github.com/kubernetes/kubernetes/pull/39966), [@liggitt](https://github.com/liggitt))
* Added support for creating HA clusters for centos using kube-up.sh. ([#39462](https://github.com/kubernetes/kubernetes/pull/39462), [@Shawyeok](https://github.com/Shawyeok))
* Enable lazy inode table and journal initialization for ext3 and ext4 ([#38865](https://github.com/kubernetes/kubernetes/pull/38865), [@codablock](https://github.com/codablock))
* Since `kubernetes.tar.gz` no longer includes client or server binaries, `cluster/kube-{up,down,push}.sh` now automatically download released binaries if they are missing. ([#38730](https://github.com/kubernetes/kubernetes/pull/38730), [@ixdy](https://github.com/ixdy))
* Fix broken cluster/centos and enhance the style ([#34002](https://github.com/kubernetes/kubernetes/pull/34002), [@xiaoping378](https://github.com/xiaoping378))
* Set kernel.softlockup_panic =1 based on the flag. ([#38001](https://github.com/kubernetes/kubernetes/pull/38001), [@dchen1107](https://github.com/dchen1107))
* Configure local-up-cluster.sh to handle auth proxies ([#36838](https://github.com/kubernetes/kubernetes/pull/36838), [@deads2k](https://github.com/deads2k))
* `kube-up.sh`/`kube-down.sh` no longer force update gcloud for provider=gce|gke. ([#36292](https://github.com/kubernetes/kubernetes/pull/36292), [@jlowdermilk](https://github.com/jlowdermilk))
* Collect logs for dead kubelets too ([#37671](https://github.com/kubernetes/kubernetes/pull/37671), [@mtaufen](https://github.com/mtaufen))

## Changes to Addons

### Dashboard
* Update dashboard version to v1.6.0 ([#43210](https://github.com/kubernetes/kubernetes/pull/43210), [@floreks](https://github.com/floreks))

### DNS
* Updates the dnsmasq cache/mux layer to be managed by dnsmasq-nanny. ([#41826](https://github.com/kubernetes/kubernetes/pull/41826), [@bowei](https://github.com/bowei))
  dnsmasq-nanny manages dnsmasq based on values from the
  kube-system:kube-dns configmap:
  ```
  "stubDomains": {
  "acme.local": ["1.2.3.4"]
   },
  ```

  is a map of domain to list of nameservers for the domain. This is used
  to inject private DNS domains into the kube-dns namespace. In the above
  example, any DNS requests for `*.acme.local` will be served by the
  ```
  nameserver 1.2.3.4.
  ```

  ```
  upstreamNameservers": ["8.8.8.8", "8.8.4.4"]
  ```
  is a list of upstreamNameservers to use, overriding the configuration
  specified in `/etc/resolv.conf`.
* `kube-dns` now runs using a separate `system:serviceaccount:kube-system:kube-dns` service account which is automatically bound to the correct RBAC permissions. ([#38816](https://github.com/kubernetes/kubernetes/pull/38816), [@deads2k](https://github.com/deads2k))
* Use kube-dns:1.11.0 ([#39925](https://github.com/kubernetes/kubernetes/pull/39925), [@sadlil](https://github.com/sadlil))

### DNS Autoscaler
* Patch CVE-2016-8859 in gcr.io/google-containers/cluster-proportional-autoscaler-amd64 ([#42933](https://github.com/kubernetes/kubernetes/pull/42933), [@timstclair](https://github.com/timstclair))

### Cluster Autoscaler
* Allow the Horizontal Pod Autoscaler controller to talk to the metrics API and custom metrics API as standard APIs. ([#41824](https://github.com/kubernetes/kubernetes/pull/41824), [@DirectXMan12](https://github.com/DirectXMan12))

### Cluster Load Balancing
* Update defaultbackend image to 1.3 ([#42212](https://github.com/kubernetes/kubernetes/pull/42212), [@timstclair](https://github.com/timstclair))

### etcd Empty Dir Cleanup
* Base etcd-empty-dir-cleanup on busybox, run as nobody, and update to etcdctl 3.0.14 ([#41674](https://github.com/kubernetes/kubernetes/pull/41674), [@ixdy](https://github.com/ixdy))

### Fluentd
* Migrated fluentd addon to daemon set ([#32088](https://github.com/kubernetes/kubernetes/pull/32088), [@piosz](https://github.com/piosz))
* Fluentd was migrated to Daemon Set, which targets nodes with beta.kubernetes.io/fluentd-ds-ready=true label. If you use fluentd in your cluster please make sure that the nodes with version 1.6+ contains this label. ([#42931](https://github.com/kubernetes/kubernetes/pull/42931), [@piosz](https://github.com/piosz))
* Fluentd-gcp containers spawned by DaemonSet are now configured using ConfigMap ([#42126](https://github.com/kubernetes/kubernetes/pull/42126), [@crassirostris](https://github.com/crassirostris))
* Cleanup fluentd-gcp image: rebase on debian-base, switch to upstream packages, remove fluent-ui & rails ([#41998](https://github.com/kubernetes/kubernetes/pull/41998), [@timstclair](https://github.com/timstclair))
* On GCE, the apiserver audit log (`/var/log/kube-apiserver-audit.log`) will be sent through fluentd if enabled. It will go to the same place as `kube-apiserver.log`, but tagged as its own stream. ([#41360](https://github.com/kubernetes/kubernetes/pull/41360), [@enisoc](https://github.com/enisoc))
* If `experimentalCriticalPodAnnotation` feature gate is set to true, fluentd pods will not be evicted by the kubelet. ([#41035](https://github.com/kubernetes/kubernetes/pull/41035), [@vishh](https://github.com/vishh))
* fluentd config for GKE clusters updated: detect exceptions in container log streams and forward them as one log entry. ([#39656](https://github.com/kubernetes/kubernetes/pull/39656), [@thomasschickinger](https://github.com/thomasschickinger))
* Make fluentd pods critical ([#39146](https://github.com/kubernetes/kubernetes/pull/39146), [@crassirostris](https://github.com/crassirostris))
* Fluentd/Elastisearch add-on: correctly parse and index kubernetes labels ([#36857](https://github.com/kubernetes/kubernetes/pull/36857), [@Shrugs](https://github.com/Shrugs))

### Heapster
* Bumped Heapster to v1.3.0. ([#43298](https://github.com/kubernetes/kubernetes/pull/43298), [@piosz](https://github.com/piosz))
  * More details about the release https://github.com/kubernetes/heapster/releases/tag/v1.3.0

### Registry
* Use daemonset in docker registry add on ([#35582](https://github.com/kubernetes/kubernetes/pull/35582), [@surajssd](https://github.com/surajssd))
* contribute deis/registry-proxy as a replacement for kube-registry-proxy ([#35797](https://github.com/kubernetes/kubernetes/pull/35797), [@bacongobbler](https://github.com/bacongobbler))

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



# v1.4.6

[Documentation](http://kubernetes.github.io) & [Examples](http://releases.k8s.io/release-1.4/examples)

## Downloads for v1.4.6


filename | sha256 hash
-------- | -----------
[kubernetes.tar.gz](https://storage.googleapis.com/kubernetes-release/release/v1.4.6/kubernetes.tar.gz) | `6f8242aa29493e1f824997748419e4a287c28b06ed13f17b1ba94bf07fdfa3be`
[kubernetes-src.tar.gz](https://storage.googleapis.com/kubernetes-release/release/v1.4.6/kubernetes-src.tar.gz) | `a2a2d885d246300b52adb5d7e1471b382c77d90a816618518c2a6e9941208e40`

### Client Binaries

filename | sha256 hash
-------- | -----------
[kubernetes-client-darwin-386.tar.gz](https://storage.googleapis.com/kubernetes-release/release/v1.4.6/kubernetes-client-darwin-386.tar.gz) | `4db6349c976f893d0000dcb5b2ab09327824d0c38b3beab961711a0951cdfc82`
[kubernetes-client-darwin-amd64.tar.gz](https://storage.googleapis.com/kubernetes-release/release/v1.4.6/kubernetes-client-darwin-amd64.tar.gz) | `2d31dea858569f518410effb20d3c3b9a6798d706dacbafd85f1f67f9ccbe288`
[kubernetes-client-linux-386.tar.gz](https://storage.googleapis.com/kubernetes-release/release/v1.4.6/kubernetes-client-linux-386.tar.gz) | `7980cf6132a7a6bf3816b8fd60d7bc1c9cb447d45196c31312b9d73567010909`
[kubernetes-client-linux-amd64.tar.gz](https://storage.googleapis.com/kubernetes-release/release/v1.4.6/kubernetes-client-linux-amd64.tar.gz) | `95b3cbd339f7d104d5b69b08d53060bfc78bd4ee7a94ede7ba4c0a76b615f8b1`
[kubernetes-client-linux-arm64.tar.gz](https://storage.googleapis.com/kubernetes-release/release/v1.4.6/kubernetes-client-linux-arm64.tar.gz) | `0f03cff262b0f4cc218b0f79294b4cbd8f92146c31137c75a27012d956864c79`
[kubernetes-client-linux-arm.tar.gz](https://storage.googleapis.com/kubernetes-release/release/v1.4.6/kubernetes-client-linux-arm.tar.gz) | `f8c76fe8c41a5084cc1a1ab3e08d7e2d815f7baedfadac0dc6f9157ed2c607c9`
[kubernetes-client-windows-386.tar.gz](https://storage.googleapis.com/kubernetes-release/release/v1.4.6/kubernetes-client-windows-386.tar.gz) | `c29b3c8c8a72246852db048e922ad2221f35e1c309571f73fd9f3d9b01be5f79`
[kubernetes-client-windows-amd64.tar.gz](https://storage.googleapis.com/kubernetes-release/release/v1.4.6/kubernetes-client-windows-amd64.tar.gz) | `95bf20bdbe354476bbd3647adf72985698ded53a59819baa8268b5811e19f952`

### Server Binaries

filename | sha256 hash
-------- | -----------
[kubernetes-server-linux-amd64.tar.gz](https://storage.googleapis.com/kubernetes-release/release/v1.4.6/kubernetes-server-linux-amd64.tar.gz) | `f0a60c45f3360696431288826e56df3b8c18c1dc6fc3f0ea83409f970395e38f`
[kubernetes-server-linux-arm64.tar.gz](https://storage.googleapis.com/kubernetes-release/release/v1.4.6/kubernetes-server-linux-arm64.tar.gz) | `8c667d4792fcfee821a2041e5d0356e1abc2b3fa6fe7b69c5479e48c858ba29c`
[kubernetes-server-linux-arm.tar.gz](https://storage.googleapis.com/kubernetes-release/release/v1.4.6/kubernetes-server-linux-arm.tar.gz) | `c57246d484b5f98d6aa16591f2b4c4c1a01ebbc7be05bce8690a4f3b88582844`

## Changelog since v1.4.5

### Other notable changes

* Fix issue in reconstruct volume data when kubelet restarts ([#36616](https://github.com/kubernetes/kubernetes/pull/36616), [@jingxu97](https://github.com/jingxu97))
* Add sync state loop in master's volume reconciler ([#34859](https://github.com/kubernetes/kubernetes/pull/34859), [@jingxu97](https://github.com/jingxu97))
* AWS: strong-typing for k8s vs aws volume ids ([#35883](https://github.com/kubernetes/kubernetes/pull/35883), [@justinsb](https://github.com/justinsb))
* Bump GCI version to gci-beta-55-8872-47-0 ([#36679](https://github.com/kubernetes/kubernetes/pull/36679), [@mtaufen](https://github.com/mtaufen))

```
  gci-beta-55-8872-47-0:
  Date:           Nov 11, 2016
  Kernel:         ChromiumOS-4.4
  Kubernetes:     v1.4.5
  Docker:         v1.11.2
  Changelog (vs 55-8872-18-0)
    * Cherry-pick runc PR#608: Eliminate redundant parsing of mountinfo
    * Updated kubernetes to v1.4.5
    * Fixed a bug in e2fsprogs that caused mke2fs to take a very long time. Upstream fix: http://git.kernel.org/cgit/fs/ext2/e2fsprogs.git/commit/?h=next&id=d33e690fe7a6cbeb51349d9f2c7fb16a6ebec9c2 
```

# v1.3.0-alpha.2

[Documentation](http://kubernetes.github.io) & [Examples](http://releases.k8s.io/master/examples)

## Downloads

binary | sha1 hash | md5 hash
------ | --------- | --------
[kubernetes.tar.gz](https://storage.googleapis.com/kubernetes-release/release/v1.3.0-alpha.2/kubernetes.tar.gz) | `305c8c2af7e99d463dbbe4208ecfe2b50585e796` | `aadb8d729d855e69212008f8fda628c0`

## Changes since v1.3.0-alpha.1

### Other notable changes

* Make kube2sky and skydns docker images cross-platform ([#19376](https://github.com/kubernetes/kubernetes/pull/19376), [@luxas](https://github.com/luxas))
* Allowing type object in kubectl swagger validation ([#24054](https://github.com/kubernetes/kubernetes/pull/24054), [@nikhiljindal](https://github.com/nikhiljindal))
* Fix TerminationMessagePath ([#23658](https://github.com/kubernetes/kubernetes/pull/23658), [@Random-Liu](https://github.com/Random-Liu))
* Trusty: Do not create the docker-daemon cgroup ([#23996](https://github.com/kubernetes/kubernetes/pull/23996), [@andyzheng0831](https://github.com/andyzheng0831))
* Make ConfigMap volume readable as non-root ([#23793](https://github.com/kubernetes/kubernetes/pull/23793), [@pmorie](https://github.com/pmorie))
* only include running and pending pods in daemonset should place calculation ([#23929](https://github.com/kubernetes/kubernetes/pull/23929), [@mikedanese](https://github.com/mikedanese))
* Upgrade to golang 1.6 ([#22149](https://github.com/kubernetes/kubernetes/pull/22149), [@luxas](https://github.com/luxas))
* Cross-build hyperkube and debian-iptables for ARM. Also add a flannel image ([#21617](https://github.com/kubernetes/kubernetes/pull/21617), [@luxas](https://github.com/luxas))
* Add a timeout to the sshDialer to prevent indefinite hangs. ([#23843](https://github.com/kubernetes/kubernetes/pull/23843), [@cjcullen](https://github.com/cjcullen))
* Ensure object returned by volume getCloudProvider incorporates cloud config ([#23769](https://github.com/kubernetes/kubernetes/pull/23769), [@saad-ali](https://github.com/saad-ali))
* Update Dashboard UI addon to v1.0.1 ([#23724](https://github.com/kubernetes/kubernetes/pull/23724), [@maciaszczykm](https://github.com/maciaszczykm))
* Add zsh completion for kubectl ([#23797](https://github.com/kubernetes/kubernetes/pull/23797), [@sttts](https://github.com/sttts))
* AWS kube-up: tolerate a lack of ephemeral volumes ([#23776](https://github.com/kubernetes/kubernetes/pull/23776), [@justinsb](https://github.com/justinsb))
* duplicate kube-apiserver to federated-apiserver ([#23509](https://github.com/kubernetes/kubernetes/pull/23509), [@jianhuiz](https://github.com/jianhuiz))
* Kubelet: Start using the official docker engine-api ([#23506](https://github.com/kubernetes/kubernetes/pull/23506), [@Random-Liu](https://github.com/Random-Liu))
* Fix so setup-files don't recreate/invalidate certificates that already exist ([#23550](https://github.com/kubernetes/kubernetes/pull/23550), [@luxas](https://github.com/luxas))
* A pod never terminated if a container image registry was unavailable ([#23746](https://github.com/kubernetes/kubernetes/pull/23746), [@derekwaynecarr](https://github.com/derekwaynecarr))
* Fix jsonpath to handle maps with key of nonstring types ([#23358](https://github.com/kubernetes/kubernetes/pull/23358), [@aveshagarwal](https://github.com/aveshagarwal))
* Trusty: Regional release .tar.gz support ([#23558](https://github.com/kubernetes/kubernetes/pull/23558), [@andyzheng0831](https://github.com/andyzheng0831))
* Add support for 3rd party objects to kubectl ([#18835](https://github.com/kubernetes/kubernetes/pull/18835), [@brendandburns](https://github.com/brendandburns))
* Remove unnecessary override of /etc/init.d/docker on containervm image. ([#23593](https://github.com/kubernetes/kubernetes/pull/23593), [@dchen1107](https://github.com/dchen1107))
* make docker-checker more robust ([#23662](https://github.com/kubernetes/kubernetes/pull/23662), [@ArtfulCoder](https://github.com/ArtfulCoder))
* Change kube-proxy & fluentd CPU request to 20m/80m. ([#23646](https://github.com/kubernetes/kubernetes/pull/23646), [@cjcullen](https://github.com/cjcullen))
* Create a new Deployment in kube-system for every version. ([#23512](https://github.com/kubernetes/kubernetes/pull/23512), [@Q-Lee](https://github.com/Q-Lee))
* IngressTLS: allow secretName to be blank for SNI routing ([#23500](https://github.com/kubernetes/kubernetes/pull/23500), [@tam7t](https://github.com/tam7t))
* don't sync deployment when pod selector is empty ([#23467](https://github.com/kubernetes/kubernetes/pull/23467), [@mikedanese](https://github.com/mikedanese))
* AWS: Fix problems with >2 security groups ([#23340](https://github.com/kubernetes/kubernetes/pull/23340), [@justinsb](https://github.com/justinsb))



# v1.2.2

[Documentation](http://kubernetes.github.io) & [Examples](http://releases.k8s.io/release-1.2/examples)

## Downloads

binary | sha1 hash | md5 hash
------ | --------- | --------
[kubernetes.tar.gz](https://storage.googleapis.com/kubernetes-release/release/v1.2.2/kubernetes.tar.gz) | `8dede5833a1986434adea80749624f81a0db7bb4` | `72a5389f22827fb5133fdc3b7bfb9b3a`

## Changes since v1.2.1

### Other notable changes

* Trusty: Update heapster manifest handling code ([#23434](https://github.com/kubernetes/kubernetes/pull/23434), [@andyzheng0831](https://github.com/andyzheng0831))
* Support addon Deployments, make heapster a deployment with a nanny. ([#22893](https://github.com/kubernetes/kubernetes/pull/22893), [@Q-Lee](https://github.com/Q-Lee))
* Create a new Deployment in kube-system for every version. ([#23512](https://github.com/kubernetes/kubernetes/pull/23512), [@Q-Lee](https://github.com/Q-Lee))
* Use SCP to dump logs and parallelize a bit. ([#22835](https://github.com/kubernetes/kubernetes/pull/22835), [@spxtr](https://github.com/spxtr))
* Trusty: Regional release .tar.gz support ([#23558](https://github.com/kubernetes/kubernetes/pull/23558), [@andyzheng0831](https://github.com/andyzheng0831))
* Make ConfigMap volume readable as non-root ([#23793](https://github.com/kubernetes/kubernetes/pull/23793), [@pmorie](https://github.com/pmorie))
* only include running and pending pods in daemonset should place calculation ([#23929](https://github.com/kubernetes/kubernetes/pull/23929), [@mikedanese](https://github.com/mikedanese))
* A pod never terminated if a container image registry was unavailable ([#23746](https://github.com/kubernetes/kubernetes/pull/23746), [@derekwaynecarr](https://github.com/derekwaynecarr))
* Update Dashboard UI addon to v1.0.1 ([#23724](https://github.com/kubernetes/kubernetes/pull/23724), [@maciaszczykm](https://github.com/maciaszczykm))
* Ensure object returned by volume getCloudProvider incorporates cloud config ([#23769](https://github.com/kubernetes/kubernetes/pull/23769), [@saad-ali](https://github.com/saad-ali))
* Add a timeout to the sshDialer to prevent indefinite hangs. ([#23843](https://github.com/kubernetes/kubernetes/pull/23843), [@cjcullen](https://github.com/cjcullen))
* AWS kube-up: tolerate a lack of ephemeral volumes ([#23776](https://github.com/kubernetes/kubernetes/pull/23776), [@justinsb](https://github.com/justinsb))
* Fix so setup-files don't recreate/invalidate certificates that already exist ([#23550](https://github.com/kubernetes/kubernetes/pull/23550), [@luxas](https://github.com/luxas))

# v1.2.1

[Documentation](http://kubernetes.github.io) & [Examples](http://releases.k8s.io/release-1.2/examples)

## Downloads

binary | sha1 hash | md5 hash
------ | --------- | --------
[kubernetes.tar.gz](https://storage.googleapis.com/kubernetes-release/release/v1.2.1/kubernetes.tar.gz) | `1639807c5788e1c6b1ab51fd30b723fb5debd865` | `235a1da47972c96a560d718d3256ca4f`


## Changes since v1.2.0

### Other notable changes

* AWS: Fix problems with >2 security groups ([#23340](https://github.com/kubernetes/kubernetes/pull/23340), [@justinsb](https://github.com/justinsb))
* IngressTLS: allow secretName to be blank for SNI routing ([#23500](https://github.com/kubernetes/kubernetes/pull/23500), [@tam7t](https://github.com/tam7t))
* Heapster patch release to 1.0.2 ([#23487](https://github.com/kubernetes/kubernetes/pull/23487), [@piosz](https://github.com/piosz))
* Remove unnecessary override of /etc/init.d/docker on containervm image. ([#23593](https://github.com/kubernetes/kubernetes/pull/23593), [@dchen1107](https://github.com/dchen1107))
* Change kube-proxy & fluentd CPU request to 20m/80m. ([#23646](https://github.com/kubernetes/kubernetes/pull/23646), [@cjcullen](https://github.com/cjcullen))
* make docker-checker more robust ([#23662](https://github.com/kubernetes/kubernetes/pull/23662), [@ArtfulCoder](https://github.com/ArtfulCoder))
* validate that daemonsets don't have empty selectors on creation ([#23530](https://github.com/kubernetes/kubernetes/pull/23530), [@mikedanese](https://github.com/mikedanese))
* don't sync deployment when pod selector is empty ([#23467](https://github.com/kubernetes/kubernetes/pull/23467), [@mikedanese](https://github.com/mikedanese))
* Support differentiation of OS distro in e2e tests ([#23466](https://github.com/kubernetes/kubernetes/pull/23466), [@andyzheng0831](https://github.com/andyzheng0831))
* don't sync daemonsets with selectors that match all pods ([#23223](https://github.com/kubernetes/kubernetes/pull/23223), [@mikedanese](https://github.com/mikedanese))
* Trusty: Avoid reaching GCE custom metadata size limit ([#22818](https://github.com/kubernetes/kubernetes/pull/22818), [@andyzheng0831](https://github.com/andyzheng0831))
* Update kubectl help for 1.2 resources ([#23305](https://github.com/kubernetes/kubernetes/pull/23305), [@janetkuo](https://github.com/janetkuo))
* Removing URL query param from swagger UI to fix the XSS issue ([#23234](https://github.com/kubernetes/kubernetes/pull/23234), [@nikhiljindal](https://github.com/nikhiljindal))
* Fix hairpin mode ([#23325](https://github.com/kubernetes/kubernetes/pull/23325), [@MurgaNikolay](https://github.com/MurgaNikolay))
* Bump to container-vm-v20160321 ([#23313](https://github.com/kubernetes/kubernetes/pull/23313), [@zmerlynn](https://github.com/zmerlynn))
* Remove the restart-kube-proxy and restart-apiserver functions ([#23180](https://github.com/kubernetes/kubernetes/pull/23180), [@roberthbailey](https://github.com/roberthbailey))
* Copy annotations back from RS to Deployment on rollback ([#23160](https://github.com/kubernetes/kubernetes/pull/23160), [@janetkuo](https://github.com/janetkuo))
* Trusty: Support hybrid cluster with nodes on ContainerVM ([#23079](https://github.com/kubernetes/kubernetes/pull/23079), [@andyzheng0831](https://github.com/andyzheng0831))
* update expose command description to add deployment ([#23246](https://github.com/kubernetes/kubernetes/pull/23246), [@AdoHe](https://github.com/AdoHe))
* Add a rate limiter to the GCE cloudprovider ([#23019](https://github.com/kubernetes/kubernetes/pull/23019), [@alex-mohr](https://github.com/alex-mohr))
* Add a Deployment example for kubectl expose. ([#23222](https://github.com/kubernetes/kubernetes/pull/23222), [@madhusudancs](https://github.com/madhusudancs))
* Use versioned object when computing patch ([#23145](https://github.com/kubernetes/kubernetes/pull/23145), [@liggitt](https://github.com/liggitt))
* kubelet: send all recevied pods in one update ([#23141](https://github.com/kubernetes/kubernetes/pull/23141), [@yujuhong](https://github.com/yujuhong))
* Add a SSHKey sync check to the master's healthz (when using SSHTunnels). ([#23167](https://github.com/kubernetes/kubernetes/pull/23167), [@cjcullen](https://github.com/cjcullen))
* Validate minimum CPU limits to be >= 10m ([#23143](https://github.com/kubernetes/kubernetes/pull/23143), [@vishh](https://github.com/vishh))
* Fix controller-manager race condition issue which cause endpoints flush during restart ([#23035](https://github.com/kubernetes/kubernetes/pull/23035), [@xinxiaogang](https://github.com/xinxiaogang))
* MESOS: forward globally declared cadvisor housekeeping flags ([#22974](https://github.com/kubernetes/kubernetes/pull/22974), [@jdef](https://github.com/jdef))
* Trusty: support developer workflow on base image ([#22960](https://github.com/kubernetes/kubernetes/pull/22960), [@andyzheng0831](https://github.com/andyzheng0831))



# v1.3.0-alpha.1

[Documentation](http://kubernetes.github.io) & [Examples](http://releases.k8s.io/HEAD/examples)

## Downloads

binary | sha1 hash | md5 hash
------ | --------- | --------
[kubernetes.tar.gz](https://storage.googleapis.com/kubernetes-release/release/v1.3.0-alpha.1/kubernetes.tar.gz) | `e0041b08e220a4704ea2ad90a6ec7c8f2120c2d3` | `7bb2df32aea94678f72a8d1f43a12098`

## Changes since v1.2.0

### Action Required

* Disabling swagger ui by default on apiserver. Adding a flag that can enable it ([#23025](https://github.com/kubernetes/kubernetes/pull/23025), [@nikhiljindal](https://github.com/nikhiljindal))
* restore ability to run against secured etcd ([#21535](https://github.com/kubernetes/kubernetes/pull/21535), [@AdoHe](https://github.com/AdoHe))

### Other notable changes

* validate that daemonsets don't have empty selectors on creation ([#23530](https://github.com/kubernetes/kubernetes/pull/23530), [@mikedanese](https://github.com/mikedanese))
* Trusty: Update heapster manifest handling code ([#23434](https://github.com/kubernetes/kubernetes/pull/23434), [@andyzheng0831](https://github.com/andyzheng0831))
* Support differentiation of OS distro in e2e tests ([#23466](https://github.com/kubernetes/kubernetes/pull/23466), [@andyzheng0831](https://github.com/andyzheng0831))
* don't sync daemonsets with selectors that match all pods ([#23223](https://github.com/kubernetes/kubernetes/pull/23223), [@mikedanese](https://github.com/mikedanese))
* Trusty: Avoid reaching GCE custom metadata size limit ([#22818](https://github.com/kubernetes/kubernetes/pull/22818), [@andyzheng0831](https://github.com/andyzheng0831))
* Update kubectl help for 1.2 resources ([#23305](https://github.com/kubernetes/kubernetes/pull/23305), [@janetkuo](https://github.com/janetkuo))
* Support addon Deployments, make heapster a deployment with a nanny. ([#22893](https://github.com/kubernetes/kubernetes/pull/22893), [@Q-Lee](https://github.com/Q-Lee))
* Removing URL query param from swagger UI to fix the XSS issue ([#23234](https://github.com/kubernetes/kubernetes/pull/23234), [@nikhiljindal](https://github.com/nikhiljindal))
* Fix hairpin mode ([#23325](https://github.com/kubernetes/kubernetes/pull/23325), [@MurgaNikolay](https://github.com/MurgaNikolay))
* Bump to container-vm-v20160321 ([#23313](https://github.com/kubernetes/kubernetes/pull/23313), [@zmerlynn](https://github.com/zmerlynn))
* Remove the restart-kube-proxy and restart-apiserver functions ([#23180](https://github.com/kubernetes/kubernetes/pull/23180), [@roberthbailey](https://github.com/roberthbailey))
* Copy annotations back from RS to Deployment on rollback ([#23160](https://github.com/kubernetes/kubernetes/pull/23160), [@janetkuo](https://github.com/janetkuo))
* Trusty: Support hybrid cluster with nodes on ContainerVM ([#23079](https://github.com/kubernetes/kubernetes/pull/23079), [@andyzheng0831](https://github.com/andyzheng0831))
* update expose command description to add deployment ([#23246](https://github.com/kubernetes/kubernetes/pull/23246), [@AdoHe](https://github.com/AdoHe))
* Add a rate limiter to the GCE cloudprovider ([#23019](https://github.com/kubernetes/kubernetes/pull/23019), [@alex-mohr](https://github.com/alex-mohr))
* Add a Deployment example for kubectl expose. ([#23222](https://github.com/kubernetes/kubernetes/pull/23222), [@madhusudancs](https://github.com/madhusudancs))
* Use versioned object when computing patch ([#23145](https://github.com/kubernetes/kubernetes/pull/23145), [@liggitt](https://github.com/liggitt))
* kubelet: send all recevied pods in one update ([#23141](https://github.com/kubernetes/kubernetes/pull/23141), [@yujuhong](https://github.com/yujuhong))
* Add a SSHKey sync check to the master's healthz (when using SSHTunnels). ([#23167](https://github.com/kubernetes/kubernetes/pull/23167), [@cjcullen](https://github.com/cjcullen))
* Validate minimum CPU limits to be >= 10m ([#23143](https://github.com/kubernetes/kubernetes/pull/23143), [@vishh](https://github.com/vishh))
* Fix controller-manager race condition issue which cause endpoints flush during restart ([#23035](https://github.com/kubernetes/kubernetes/pull/23035), [@xinxiaogang](https://github.com/xinxiaogang))
* MESOS: forward globally declared cadvisor housekeeping flags ([#22974](https://github.com/kubernetes/kubernetes/pull/22974), [@jdef](https://github.com/jdef))
* Trusty: support developer workflow on base image ([#22960](https://github.com/kubernetes/kubernetes/pull/22960), [@andyzheng0831](https://github.com/andyzheng0831))
* Bumped Heapster to stable version 1.0.0 ([#22993](https://github.com/kubernetes/kubernetes/pull/22993), [@piosz](https://github.com/piosz))
* Deprecating --api-version flag ([#22410](https://github.com/kubernetes/kubernetes/pull/22410), [@nikhiljindal](https://github.com/nikhiljindal))
* allow resource.version.group in kubectl ([#22853](https://github.com/kubernetes/kubernetes/pull/22853), [@deads2k](https://github.com/deads2k))
* Use SCP to dump logs and parallelize a bit. ([#22835](https://github.com/kubernetes/kubernetes/pull/22835), [@spxtr](https://github.com/spxtr))
* update wide option output ([#22772](https://github.com/kubernetes/kubernetes/pull/22772), [@AdoHe](https://github.com/AdoHe))
* Change scheduler logic from random to round-robin ([#22430](https://github.com/kubernetes/kubernetes/pull/22430), [@gmarek](https://github.com/gmarek))



# v1.2.0

[Documentation](http://kubernetes.github.io) & [Examples](http://releases.k8s.io/release-1.2/examples)

## Downloads

binary | sha1 hash | md5 hash
------ | --------- | --------
[kubernetes.tar.gz](https://storage.googleapis.com/kubernetes-release/release/v1.2.0/kubernetes.tar.gz) | `52dd998e1191f464f581a9b87017d70ce0b058d9` | `c0ce9e6150e9d7a19455db82f3318b4c`

## Changes since v1.1.1

### Major Themes

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

### Other notable improvements

  * Job was Beta in 1.1 and is GA in 1.2 .
     * <code>apiVersion: batch/v1 </code>is now available.  You now do not need to specify the <code>.spec.selector</code> field — a [unique selector is automatically generated ](http://kubernetes.io/docs/user-guide/jobs/#pod-selector)for you.
     * The previous version, <code>apiVersion: extensions/v1beta1</code>, is still supported.  Even if you roll back to 1.1, the objects created using
the new apiVersion will still be accessible, using the old version.   You can
continue to use your existing JSON and YAML files until you are ready to switch
to <code>batch/v1</code>.  We may remove support for Jobs with  <code>apiVersion: extensions/v1beta1 </code>in 1.3 or 1.4.
  *  HorizontalPodAutoscaler was Beta in 1.1 and is GA in 1.2 .
     * <code>apiVersion: autoscaling/v1 </code>is now available.  Changes in this version are:
        * Field CPUUtilization which was a nested structure CPUTargetUtilization in
HorizontalPodAutoscalerSpec was replaced by TargetCPUUtilizationPercentage
which is an integer.
        * ScaleRef of type SubresourceReference in HorizontalPodAutoscalerSpec which
referred to scale subresource of the resource being scaled was replaced by
ScaleTargetRef which points just to the resource being scaled.
        * In extensions/v1beta1 if CPUUtilization in HorizontalPodAutoscalerSpec was not
specified it was set to 80 by default while in autoscaling/v1 HPA object
without TargetCPUUtilizationPercentage specified is a valid object. Pod
autoscaler controller will apply a default scaling policy in this case which is
equivalent to the previous one but may change in the future.
     * The previous version, <code>apiVersion: extensions/v1beta1</code>, is still supported.  Even if you roll back to 1.1, the objects created using
the new apiVersions will still be accessible, using the old version.  You can
continue to use your existing JSON and YAML files until you are ready to switch
to <code>autoscaling/v1</code>.  We may remove support for HorizontalPodAutoscalers with  <code>apiVersion: extensions/v1beta1 </code>in 1.3 or 1.4.
  * Kube-Proxy now defaults to an iptables-based proxy. If the --proxy-mode flag is
specified while starting kube-proxy (‘userspace’ or ‘iptables’), the flag value
will be respected. If the flag value is not specified, the kube-proxy respects
the Node object annotation: ‘net.beta.kubernetes.io/proxy-mode’. If the
annotation is not specified, then ‘iptables’ mode is the default. If kube-proxy
is unable to start in iptables mode because system requirements are not met
(kernel or iptables versions are insufficient), the kube-proxy will fall-back
to userspace mode. Kube-proxy is much more performant and less
resource-intensive in ‘iptables’ mode.
  * Node stability can be improved by reserving [resources](https://github.com/kubernetes/kubernetes/blob/release-1.2/docs/proposals/node-allocatable.md) for the base operating system using --system-reserved and --kube-reserved Kubelet flags
  * Liveness and readiness probes now support more configuration parameters:
periodSeconds, successThreshold, failureThreshold
  * The new ReplicaSet API (Beta) in the Extensions API group is similar to
ReplicationController, but its [selector](http://kubernetes.io/docs/user-guide/labels/#label-selectors) is more general (supports set-based selector; whereas ReplicationController
only supports equality-based selector).
  * Scale subresource support is now expanded to ReplicaSets along with
ReplicationControllers and Deployments. Scale now supports two different types
of selectors to accommodate both [equality-based selectors](http://kubernetes.io/docs/user-guide/labels/#equality-based-requirement) supported by ReplicationControllers and [set-based selectors](http://kubernetes.io/docs/user-guide/labels/#set-based-requirement) supported by Deployments and ReplicaSets.
  * “kubectl run” now produces Deployments (instead of ReplicationControllers) and
Jobs (instead of Pods) by default.
  * Pods can now consume Secret data in environment variables and inject those
environment variables into a container’s command-line args.
  * Stable version of Heapster which scales up to 1000 nodes: more metrics, reduced
latency, reduced cpu/memory consumption (~4mb per monitored node).
  * Pods now have a security context which allows users to specify:
     * attributes which apply to the whole pod:
        * User ID
        * Whether all containers should be non-root
        * Supplemental Groups
        * FSGroup - a special supplemental group
        * SELinux options
     * If a pod defines an FSGroup, that Pod’s system (emptyDir, secret, configMap,
etc) volumes and block-device volumes will be owned by the FSGroup, and each
container in the pod will run with the FSGroup as a supplemental group
  * Volumes that support SELinux labelling are now automatically relabeled with the
Pod’s SELinux context, if specified
  * A stable client library release\_1\_2 is added. The library is [here](pkg/client/clientset_generated/), and detailed doc is [here](docs/devel/generating-clientset.md#released-clientsets). We will keep the interface of this go client stable.
  * New Azure File Service Volume Plugin enables mounting Microsoft Azure File
Volumes (SMB 2.1 and 3.0) into a Pod. See [example](https://github.com/kubernetes/kubernetes/blob/release-1.2/examples/azure_file/README.md) for details.
  * Logs usage and root filesystem usage of a container, volumes usage of a pod and node disk usage are exposed through Kubelet new metrics API.

### Experimental Features

  * Dynamic Provisioning of PersistentVolumes: Kubernetes previously required all
volumes to be manually provisioned by a cluster administrator before use. With
this feature, volume plugins that support it (GCE PD, AWS EBS, and Cinder) can
automatically provision a PersistentVolume to bind to an unfulfilled
PersistentVolumeClaim.
  * Run multiple schedulers in parallel, e.g. one or more custom schedulers
alongside the default Kubernetes scheduler, using pod annotations to select
among the schedulers for each pod. Documentation is [here](http://kubernetes.io/docs/admin/multiple-schedulers.md), design doc is [here](docs/proposals/multiple-schedulers.md).
  * More expressive node affinity syntax, and support for “soft” node affinity.
Node selectors (to constrain pods to schedule on a subset of nodes) now support
the operators {<code>In, NotIn, Exists, DoesNotExist, Gt, Lt</code>}  instead of just conjunction of exact match on node label values. In
addition, we’ve introduced a new “soft” kind of node selector that is just a
hint to the scheduler; the scheduler will try to satisfy these requests but it
does not guarantee they will be satisfied. Both the “hard” and “soft” variants
of node affinity use the new syntax. Documentation is [here](http://kubernetes.io/docs/user-guide/node-selection/) (see section “Alpha feature in Kubernetes v1.2: Node Affinity“). Design doc is [here](https://github.com/kubernetes/kubernetes/blob/release-1.2/docs/design/nodeaffinity.md).
  * A pod can specify its own Hostname and Subdomain via annotations (<code>pod.beta.kubernetes.io/hostname, pod.beta.kubernetes.io/subdomain)</code>. If the Subdomain matches the name of a [headless service](http://kubernetes.io/docs/user-guide/services/#headless-services) in the same namespace, a DNS A record is also created for the pod’s FQDN. More
details can be found in the [DNS README](https://github.com/kubernetes/kubernetes/blob/release-1.2/cluster/saltbase/salt/kube-dns/README.md#a-records-and-hostname-based-on-pod-annotations---a-beta-feature-in-kubernetes-v12). Changes were introduced in PR [#20688](https://github.com/kubernetes/kubernetes/pull/20688).
  * New SchedulerExtender enables users to implement custom
out-of-(the-scheduler)-process scheduling predicates and priority functions,
for example to schedule pods based on resources that are not directly managed
by Kubernetes. Changes were introduced in PR [#13580](https://github.com/kubernetes/kubernetes/pull/13580). Example configuration and documentation is available [here](docs/design/scheduler_extender.md). This is an alpha feature and may not be supported in its current form at beta
or GA.
  * New Flex Volume Plugin enables users to use out-of-process volume plugins that
are installed to “/usr/libexec/kubernetes/kubelet-plugins/volume/exec/” on
every node, instead of being compiled into the Kubernetes binary. See [example](examples/volumes/flexvolume/README.md) for details.
  * vendor volumes into a pod. It expects vendor drivers are installed in the
volume plugin path on each kubelet node. This is an alpha feature and may
change in future.
  * Kubelet exposes a new Alpha metrics API - /stats/summary in a user friendly format with reduced system overhead. The measurement is done in PR [#22542](https://github.com/kubernetes/kubernetes/pull/22542).

### Action required

  * Docker v1.9.1 is officially recommended. Docker v1.8.3 and Docker v1.10 are
supported. If you are using an older release of Docker, please upgrade. Known
issues with Docker 1.9.1 can be found below.
  * CPU hardcapping will be enabled by default for containers with CPU limit set,
if supported by the kernel. You should either adjust your CPU limit, or set CPU
request only, if you want to avoid hardcapping. If the kernel does not support
CPU Quota, NodeStatus will contain a warning indicating that CPU Limits cannot
be enforced.
  * The following applies only if you use the Go language client (<code>/pkg/client/unversioned</code>) to create Job by defining Go variables of type "<code>k8s.io/kubernetes/pkg/apis/extensions".Job</code>).  We think <strong>this is not common</strong>, so if you are not sure what this means, you probably aren't doing this.  If
you do this, then, at the time you re-vendor the "<code>k8s.io/kubernetes/"</code> code, you will need to set <code>job.Spec.ManualSelector = true</code>, or else set <code>job.Spec.Selector = nil.  </code>Otherwise, the jobs you create may be rejected.  See [Specifying your own pod selector](http://kubernetes.io/docs/user-guide/jobs/#specifying-your-own-pod-selector).
  * Deployment was Alpha in 1.1 (though it had apiVersion extensions/v1beta1) and
was disabled by default. Due to some non-backward-compatible API changes, any
Deployment objects you created in 1.1 won’t work with in the 1.2 release.
     * Before upgrading to 1.2, <strong>delete all Deployment alpha-version resources</strong>, including the Replication Controllers and Pods the Deployment manages. Then
create Deployment Beta resources after upgrading to 1.2. Not deleting the
Deployment objects may cause the deployment controller to mistakenly match
other pods and delete them, due to the selector API change.
     * Client (kubectl) and server versions must match (both 1.1 or both 1.2) for any
Deployment-related operations.
     * Behavior change:
        * Deployment creates ReplicaSets instead of ReplicationControllers.
        * Scale subresource now has a new <code>targetSelector</code> field in its status. This field supports the new set-based selectors supported
by Deployments, but in a serialized format.
     * Spec change:
        * Deployment’s [selector](http://kubernetes.io/docs/user-guide/labels/#label-selectors) is now more general (supports set-based selector; it only supported
equality-based selector in 1.1).
        * .spec.uniqueLabelKey is removed -- users can’t customize unique label key --
and its default value is changed from
“deployment.kubernetes.io/podTemplateHash” to “pod-template-hash”.
        * .spec.strategy.rollingUpdate.minReadySeconds is moved to .spec.minReadySeconds
  * DaemonSet was Alpha in 1.1 (though it had apiVersion extensions/v1beta1) and
was disabled by default. Due to some non-backward-compatible API changes, any
DaemonSet objects you created in 1.1 won’t work with in the 1.2 release.
     * Before upgrading to 1.2, <strong>delete all DaemonSet alpha-version resources</strong>. If you do not want to disrupt the pods, use kubectl delete daemonset <name>
--cascade=false. Then create DaemonSet Beta resources after upgrading to 1.2.
     * Client (kubectl) and server versions must match (both 1.1 or both 1.2) for any
DaemonSet-related operations.
     * Behavior change:
        * DaemonSet pods will be created on nodes with .spec.unschedulable=true and will
not be evicted from nodes whose Ready condition is false.
        * Updates to the pod template are now permitted. To perform a rolling update of a
DaemonSet, update the pod template and then delete its pods one by one; they
will be replaced using the updated template.
     * Spec change:
        * DaemonSet’s [selector](http://kubernetes.io/docs/user-guide/labels/#label-selectors) is now more general (supports set-based selector; it only supported
equality-based selector in 1.1).
  * Running against a secured etcd requires these flags to be passed to
kube-apiserver (instead of --etcd-config):
     * --etcd-certfile, --etcd-keyfile (if using client cert auth)
     * --etcd-cafile (if not using system roots)
  * As part of preparation in 1.2 for adding support for protocol buffers (and the
direct YAML support in the API available today), the Content-Type and Accept
headers are now properly handled as per the HTTP spec.  As a consequence, if
you had a client that was sending an invalid Content-Type or Accept header to
the API, in 1.2 you will either receive a 415 or 406 error.
The only client
this is known to affect is curl when you use -d with JSON but don't set a
content type, helpfully sends "application/x-www-urlencoded", which is not
correct.
Other client authors should double check that you are sending proper
accept and content type headers, or set no value (in which case JSON is the
default).
An example using curl:
<code>curl -H "Content-Type: application/json" -XPOST -d
'{"apiVersion":"v1","kind":"Namespace","metadata":{"name":"kube-system"}}' "[http://127.0.0.1:8080/api/v1/namespaces](http://127.0.0.1:8080/api/v1/namespaces)"</code>
  * The version of InfluxDB is bumped from 0.8 to 0.9 which means storage schema
change. More details [here](https://docs.influxdata.com/influxdb/v0.9/administration/upgrading/).
  * We have renamed “minions” to “nodes”.  If you were specifying NUM\_MINIONS or
MINION\_SIZE to kube-up, you should now specify NUM\_NODES or NODE\_SIZE.

### Known Issues

  * Paused deployments can't be resized and don't clean up old ReplicaSets.
  * Minimum memory limit is 4MB. This is a docker limitation
  * Minimum CPU limits is 10m. This is a Linux Kernel limitation
  * “kubectl rollout undo” (i.e. rollback) will hang on paused deployments, because
paused deployments can’t be rolled back (this is expected), and the command
waits for rollback events to return the result. Users should use “kubectl
rollout resume” to resume a deployment before rolling back.
  * “kubectl edit <list>” will open the editor multiple times, once for each
resource in the list.
  * If you create HPA object using autoscaling/v1 API without specifying
targetCPUUtilizationPercentage and read it using kubectl it will print default
value as specified in extensions/v1beta1 (see details in [#23196](https://github.com/kubernetes/kubernetes/issues/23196)).
  * If a node or kubelet crashes with a volume attached, the volume will remain
attached to that node. If that volume can only be attached to one node at a
time (GCE PDs attached in RW mode, for example), then the volume must be
manually detached before Kubernetes can attach it to other nodes.
  * If a volume is already attached to a node any subsequent attempts to attach it
again (due to kubelet restart, for example) will fail. The volume must either
be manually detached first or the pods referencing it deleted (which would
trigger automatic volume detach).
  * In very large clusters it may happen that a few nodes won’t register in API
server in a given timeframe for whatever reasons (networking issue, machine
failure, etc.). Normally when kube-up script will encounter even one NotReady
node it will fail, even though the cluster most likely will be working. We
added an environmental variable to kube-up ALLOWED\_NOTREADY\_NODES that
defines the number of nodes that if not Ready in time won’t cause kube-up
failure.
  * “kubectl rolling-update” only supports Replication Controllers (it doesn’t
support Replica Sets). It’s recommended to use Deployment 1.2 with “kubectl
rollout” commands instead, if you want to rolling update Replica Sets.
  * When live upgrading Kubelet to 1.2 without draining the pods running on the node,
the containers will be restarted by Kubelet (see details in [#23104](https://github.com/kubernetes/kubernetes/issues/23104)).

#### Docker Known Issues

##### 1.9.1

  * Listing containers can be slow at times which will affect kubelet performance.
More information [here](https://github.com/docker/docker/issues/17720)
  * Docker daemon restarts can fail. Docker checkpoints have to deleted between
restarts. More information [here](https://github.com/kubernetes/kubernetes/issues/20995)
  * Pod IP allocation-related issues. Deleting the docker checkpoint prior to
restarting the daemon alleviates this issue, but hasn’t been verified to
completely eliminate the IP allocation issue. More information [here](https://github.com/kubernetes/kubernetes/issues/21523#issuecomment-191498969)
  * Daemon becomes unresponsive (rarely) due to kernel deadlocks. More information [here](https://github.com/kubernetes/kubernetes/issues/21866#issuecomment-189492391)

### Provider-specific Notes

#### Various

   Core changes:

  * Support for load balancers with source ranges

#### AWS

Core changes:

  * Support for ELBs with complex configurations: better subnet selection with
multiple subnets, and internal ELBs
  * Support for VPCs with private dns names
  * Multiple fixes to EBS volume mounting code for robustness, and to support
mounting the full number of AWS recommended volumes.
  * Multiple fixes to avoid hitting AWS rate limits, and to throttle if we do
  * Support for the EC2 Container Registry (currently in us-east-1 only)

With kube-up:

  * Automatically install updates on boot & reboot
  * Use optimized image based on Jessie by default
  * Add support for Ubuntu Wily
  * Master is configured with automatic restart-on-failure, via CloudWatch
  * Bootstrap reworked to be more similar to GCE; better supports reboots/restarts
  * Use an elastic IP for the master by default
  * Experimental support for node spot instances (set NODE\_SPOT\_PRICE=0.05)

#### GCE

  * Ubuntu Trusty support added

Please see the [Releases Page](https://github.com/kubernetes/kubernetes/releases) for older releases.


[![Analytics](https://kubernetes-site.appspot.com/UA-36037335-10/GitHub/CHANGELOG.md?pixel)]()ithub.com/kubernetes/kubernetes/pull/36087), [@ericchiang](https://github.com/ericchiang))**
  * `--basic-auth-file` supports optionally specifying groups in the fourth column of the file ([#39651](https://github.com/kubernetes/kubernetes/pull/39651), [@liggitt](https:
* The authorization.k8s.io API group was promoted to v1 ([#40709](https://githwill be removed in a future release. When you upgrade to 1.6, if you have not enabled the alpha feature, then the scheduler will use the `affinity` field in PodSpec and will ignore the annotation. If you have enabled the alpha feature, then the scheduler will use the `affinity` field in PodSpec if it is present, and otherwise will use the annotation.
- **[beta]** [Taints and tolerations](https://kubernetes.io/docs/concepts/configuration/assign-pod-node/). This feature allows you to specify rules for "repelling" pods from nodes by default, which enables use cases like dedicated nodes and reserving nodes with special features for pods that need those features. We've also added a `NoExecute` taint type that evicts already-running pods, and an associated `tolerationSeconds` field to tolerations to delay the eviction for a specified amount of time. As before, taints are created using `kubectl taint` (but internally they are now represented as a field `taints` in the NodeSpec rather than using the `scheduler.alpha.kubernetes.io/taints` annotation on Node). Tolerations are now specified in a new-in-1.6 `tolerations` field of the PodSpec rathl with kubeadm. kubeadm now supports managing tokens, including time based expiration, after the cluster is launched.  See [kubeadm reference docs](https://kubernetes.io/docs/admin/kubeadm/#manage-tokens) for details.
* **[alpha]** Adds a new cloud-controller-manager binary that may be used for tes
* StatefulSet now respects ControllerRef to avoid fighting over Pods. At the time of upgrade, **you must not have StatefulSets with selectors that overlap** with any other controllers (such as ReplicaSets), or elses will have no effect.
  * You can find out what taints you have in place on a node while you are still running Kubernetes 1.5 by doing `kubectl describe node <node name>`; the `Taints` section will show the taints you have in place. cts default to an apiGroup of `""`, User and Group subjects default to an apiGroup of `"rbac.authorization.k8s.io"`. ([#41184](https://github.com/kubernetes/kubernetes/pull/41184), [@liggitt](https://github.com/liggitt))
* To create or update an RBAC RoleBinding or ClusterRoleBinding object, a user must: ([#39383](https://github.com/kubernetes/kubernetesbernetes/pull/43474) ensures
    kubelet does not start pods that require netwo
* The --dns-provider argument of 'kubefed init' is now mandatory and does not default to `google-clouddns`. To initialize a Federation control plane with Google Cloud DNS, use the following invocation: 'kubefed init --dns-provider=google-clouddns' ([#42092](https://github.com/kubernetes/kubernetes/pull/42092), [@marun](https://github.com/me wait for Kubernetes 1.6.1. In 1.6.0 Cluster Autoscaler
may occasionally increase the size of the cluster a bit more tha-kubefed/) has also graduated to beta.
* Interaction with container runtimes is now through the CRI interface, enabling easier integration of runtimes with 
* Kubernetes now supports up to 5,000 nodes via etcrotobuf/etcd3 switch, and any changes since the backup will be lost.  As 1.5
des-client-linux-s390x.tar.gz](https://dl.k8s.io/v1.6.0/kubernetes-client-linux-s390x.tar.gz) | `2bd216c6b7d4f09de02c3b5d20021124f7d04f483ab600b291c515386003ca74`
[kubernetetes-client-darwin-amd64.tar.gz](https://dl.k8s.io/v1.6.0/kubernetes-client-darwin-amd64.tar.gz) | `af8d1aa034721b31fd14f7b93f5ef16f8dbac4fdcd9e312c3c61e6cf03295057`
[kubernbernetes-server-linux-amd64.tar.gz) | `3e5c7103f44f20a95db29243a43f04aca731c8a4d411c80592ea49f7550d875c`
[kubernetes-server-linux-arm64.tar.gz](https://dl.k8s.io/v1.6.1/ku555b7c558900b0cf1f9a3f2733e9a`
[kubernetes-client-linux-arm64.tar.gz](https://dl.k8s.io/v1.6.1/kubernetes-client-linux-arm64.tar.gz) | `b798e4b440df52e35809310147f8678a1d9b822dce85212fcf382d19ec2bd8c3`
[kubernetes-client-linux-arm.tar.gz](https://dl.k8s.io/v1.6.1/kubernetes-client-linux-arm.tar.gz) | `3227e745db3986a6be9c16c8ffb4f40ce604a40s for Services on Azure ([#42034](https://github.com/kubernetes/kubernetes/pull/42034), [@brendandburns](https://github.com/brendandburns))
* 1. create configmap has a new option --from-env-file that populates a configmap from file which follows a key=val format for each line. ([#38882](https://github.com/kubernetes/kubernetes/pull/38882), [@fraenkel](https://github.com/fraenkel))
    * 2. create secret has a new option --rnetes/kubernetes/pull/42666), [@timothysc](https://github.com/timothysc))
* OpenStack clusters can now specify whether worker nodes are assigned a floating IP ([#42638](https://github.com/ersion' ([#39858](https://github.com/kubernetes/kubernetes/pull/39858), [@alejandroEsc](https://github.com/alejandroEsc))
* Support secure etcd cluster for centos provider. ([#42994](https://github.com/kubernetes/kubernetes/pull/42994), [@Shawyeok](https://github.com/Shawyeok))
* Use Cluster Autoscaler 0.5.1, which fixes an issue in Cluster Autoscaler 0.5 where the cluster may be scaled up unnps://github.com/kubernetes/kubernetes/pull/42083), [@fraenkel](https://github.com/fraenkel))
    * 1. validate the name of the ConfigMap in a ConfigMapRef
    * 2. validate the name of the Secret in a SecretRef
* RBAC role and rolebinding auto-reconciliation is now p
* get-kube-local.sh checks pods with option "--namespace=kube-system" ([#42518](https://github.com/kubernetes/kubernetes/pull/42518), [@mtanino](https://github.com/mtanino))
* Using http2 in kubeapi-load-balancer to fix kubectl exec uses ([#43625](https://github.com/kubernetes/kubernetes/pull/43625), [@mbruzek](https://github.com/mb24f2b42`
[kubernetes-client-linux-ppc64le.tar.gz](https://dl.k8s.io/v1.7.0-alpha.1/kubernetes-client-linux-ppc64le.tar.gz) | `d583aff4c86de142b5e6e23cd5c8eb9617fea6574acede9fa2420169405429c6`
[kubernetes-client-linux-s390x.tar.gz](https://dl.k8s.io/v1.7.0-alpha.1/kubernetes-client-linux-s390x.tar.gz) | `ab14c4806b4e9c7a41993924467969886e1288216d80d2d077a2c
[kubernetes-client-darwin-386.tar.gz](https://dl.k8s.io/v1.7.0-alpha.1/kubernetes-client-darwin-386.tar.gz) | `115543a5ec55f9039136e0ecfd90d6510b146075d13987fad9c03db3761fbac6`
[kubernetes-client-darwin-amd64.tar.gz](https://dl.k8s.io/v1.7.0-alpha.1/kubernetes-client-darwin-amd64.tar.gz) | `91b7cc89386041125af2ecafd3c6e73197f0b7af3ec817d9aed4822e1543eee9`
[kubernetes-client-linux-386.tar.om/kubernetes/kubernetes/pull/43945), [@mikkeloscar](https://github.com/mikkeloscar))
* Fix [Kubelet panic when Docker is not running](https://github.com/kubernetes/kubernetes/issues/44027). ([#44047](https://github.com/kubernetes/kubernetes/pull/44047), [@yujuhong](https://github.com/yujuhong))
* Fix [vSphere volumes in SELinux environment](https://github.com/kubernetes/kubernetes/issues/42972). ([#42973](https://github.com/kubernetes/kubernetes/pull/42973), [@gnufied](https://github.com/gnufied))
* Fix bug with error "Volume has no class annotation" when deleting a PersistentVolume. ([#43982](https://githubps://github.com/kubernetes/kubernetes/pull/44235), [@mrIncompetent](https://github.com/mrIncompetent))
* kubeadm: Make `kubeadm reset` tolerant of a disabled docker service. ([#43951](https://github.com/kubernetes/kubernetes/pull/43951), [@luxas](https://github.com/luxas))
* Fix [broken service accounts when using dedicated service account key](https://github.com/kubernetes/kubernetes/issues/44285). ([#44169](https://github.com/kubernetes/kubernetes/pull/44169), [@mikedanese](https://github.com/mikedanese))
* Fix for kube-proxy healthcheck handling an update that simultaneously removes one port and adds another. ([#44246](https://github.com/kubernetes/kux for [disabling federation controllers through override args](https://github.com/kubernetes/kubernetes/issues/42761). ([#44341](https://github.com/kubernetes/kubernetes/pull/44341), [@irfanurrehman](https://github.com/irfanurrehman))
* Fix for [federation failing to propagate cascading deletion](https://github.com/kubernetes/kubernetes/issues/44304). ([#44108](https://github.com/kubernetes/kubernetes/pull/44108), [@csbell](https://github.com/csbell))
* Fix for [failure to delete federation controllers with finalizers](https://github.com/kubernetes/kubernetes/issues/43828). ([#44084](https://github.com/kubernetes/kubernetes/pull/44084), [@nikhiljindal](https://github.com/nikhiljindal))
* Fi-apiserver now drops unneeded path information if an older version of Windows kubectl sends it. ([#44421](https://github.com/kubernetes/kubernetes/pull/44421), [@mml](https://github.com/mml))
* CRI: Fix kubelet failing to start when using rkt. ([#44569](https://github.com/kubernetes/kubernetes/pull/44569), [@yujuhong](https://github.com/yujuhong))
* CRI: `kubectl logs -f` now stops following when container stops, as it did pre-CRI. ([#44406](https://github.com/kubernetes/kubernetes/pull/44406), [@Random-Liu](https://github.com/Random-Liu))
* Azure cloudprovider: Reduce the polling delay for all azure clients to 5 seconds. This should speed up some operations at the cost of some additional quota. ([#43699](https://github.com/kubernetes/kubernetes/pull/43699), [@colemickens](https://github.com/colemickens))
* kube4c2bb0f`
[kubernetes-client-linux-s390x.tar.gz](https://dl.k8s.io/v1.6.2/kubernetes-client-linux-s390x.tar.gz) | `e030593109a369bc3288c9f47703843248dbe4a9ade496f936d8cc355a874ba6`
[kubernetes-client-windows-386.tar.gz](https://dl.k8s.io/v1.6.2/kubernetes-client-windows-386.tar.gz) | `a2b0053de6b62d09123d8fcc1927a8cf9ab2a5a312794a858e7b423f4ffdbe3e`
[kubernetes-client-windows-amd64.tar.gz](https://dl.k8s.io/v1.6.2/kubernetes-client-windows-amd64.tar.gz) | `eafdaa29a70d1820be0dc181074c5788127996402bbd5af53b0b765ed
[kubernetes-client-darwin-386.tar.gz](https://dl.k8s.io/v1.6.2/kubernetes-client-darwin-386.tar.gz) | `3b1437cbc9d10e5466c83304c54ab06f5a880e0b047e2b0ea775530ee893b6b6`
[kubernetes-client-darwin-amd64.tar.gz](https://dl.k8s.io/v1.6.2/kubernetes-client-darwin-amd64.tar.gz) | `e3dad0848b3d6c1737199d0704c692e74bf979e6a81fabea79c5b2499ca3fa73`
[kubernetes-client-linux-386.tar.gz](https://dl.k8s.io/v1.6.2/kubernetes-client-linux-386.tar.gz) | `962f576e67f13f8f8afc958f89f0371c7496b2540372ef7f8e1bd0e43a67e829`
[kubernetes-client-linux-amd64.tar.gz](https://dl.k8s.io/v1.6.2/kubernetes-client-linux-amd64.tar.gz) | `f8ef17b8b4bb8f6974fa2b3faa992af3c39ad318c30bdfe1efab957361d8bdf1.6.2


filename | sha256 hash
-------- | -------rothers))
* print warning when delete current context ([#42538](https://github.com/kubernetes/kubernetes/pull/42538), [@adohe](https://github.com/adohe))
* Add node e2e tests for hostPid ([#44119](https://github.com/kubernetes/kubernetes/pull/44119), [@feiskyer](https://github.com/feiskyer))
* kubeadm: Make `kubeadm reset` tolerant of a disabled docker service. ([#43951](https://github.com/kubernetes/kubernetes/pull/43951), [@luxas](https://github.com/luxas))
* kubelet: make dockershim.sock configurable ([#43914](https://github.com/kubernetes/kubernetes/pull/43914), [@ncdc](https://github.com/ncdc))
* Fix [broken service accounts when using dedicated service account key](https://github.com/kubernetes/kubernetes/issues/44285). ([#44169](https://github.com/kubernetc merge patch tags in go struct tags ([#44121](https://github.com/kubernetes/kubernetes/pull/44121), [@mbohlool](https://github.com/mbohlool))
* Use go1.8.1 for arm and ppc64le ([#44216](https://github.com/kubernetes/kubernetes/pull/44216), [@mkumatag](https://github.com/mkumatag))
* Aggregated used ports at the NodeInfo level for `PodFitsHostPorts` predicate. ([#42524](https://github.com/kubernetes/kubernetes/pull/42524), [@k82cn](https://github.com/k82cn))
* Catch error when failed to make directory in NFS volume plugin ([#38801](https://github.com/kubernetes/kubernetes/pull/38801), [@nak3](https://github.com/nak3))
* Support iSCSI CHAP authentication ([#43396](https:/b](https://github.com/justinsb))
* In 'kubectl describe', find controllers with ControllerRef, instead of showing the original creator. ([#42849](https://github.com/kubernetes/kubernetes/pull/42849), [@janetkuo](https://github.com/janetkuo))
* Heat cluster operations now support environments that have multiple Swift URLs ([#41561](https://github.com/kubernetes/kubernetes/pull/41561), [@jamiehannaford](https://github.com/jamiehannaford))
* Adds support for allocation of pod IPs via IP aliases. ([#42147](https://github.com/kubernetes/kubernetes/pull/42147), [@bowei](https://github.com/bowei))
* alpha volume provisioning is removed and default storage class should be used instead. ([#44090](https://github.com/kubernetes/kubernetes/pull/44090), [@NickrenREN](https://github.com/NickrenREN))
* validateClusterInfo: use clientcmdapi.NewCluster() ([#44221](https://github.com/kubernetes/kubernetes/pull/44221), [@ncdc](her charm failures in LXD
    * Fix stop hook failure on kubernetes-worker charm://github.com/kubernetes/kubernetes/pull/41849 cannot modify blockOwnerDeletion field of existing ownerReferences, or add new ownerReference with blockOwnerDeletion=true ([#43876](https://github.com/kubernetes/kubernetes/pull/43876), [@caesarxuchao](https://github.com/caesarxuchao))
* kube-apiserver: --service-account-lookup now defaults to true, requiring the Secret API object containing the token to exist in order for a service account token to be valid. This enables service account tokens to be revoked by deleting the Secret object containing the token. ([#44071](https://github.com/kubernetes/kubernetes/pull/44071), [@liggitt](https://github.com/liggitt))
* CRI: `kubectl logs -f` now stops following when container stops, as it did pre-CRI. ([#44406](https://github.com/kubernetes/kubernetes/pull/44406), [@Random-Liu](https://github.com/Random-Liu))
* Add completion support for --namespace and --cluster to kubectl ([#44251](https://github.com/kubernetes/kubernetes/pull/44251), [@superbrothers](https://github.com/superbrothers))
* dnsprovider: avoid pani), [@perotinus](https://github.com/perotinus))
* CRI: Fix kubelet failing to start when using rkt. ([#44569](https://github.com/kubernetes/kubernetes/pull/44569), [@yujuhong](https://github.com/yujuhong))
* Remove deprecatedPublicIPs field ([#44519](https://github.com/kubernetes/kubernetes/pull/44519), [@thockin](https://github.com/thockin))
* Remove deprecated ubuntu kube-up deployment. ([#44344](https://github.com/kubernetes/kubernetes/pull/44344), [@mikedanese](https://github.com/mikedanese))
* Use OS-specific libs when computing client User-Agent in kubectl, etc. ([#44423](https://github.com/kubernetes/kubernetes/pull/44423), [@monopole](https://github.com/monopole))
* kube-apiserver now drops unneeded path information if an older version of Windows kubectl sends it. ([#44421](https://github.com/kubernetes/kubernetes/pull/44421), [@mml](https://github.com/mml))
* Extending the gc admission plugin so that a user who doesn't have delete permission of the *owner*
    * Fix handling of juju kubernetes-worker.restart-needed state
    * Fix nagios checks in charms
* Users can now specify listen and advertise URLs for etcd in a kubeadm cluster  ([#42246](https://github.com/kubernetes/kubernetes/pull/42246), [@jamiehannaford](https://github.com/jamiehannaford))
* Fixed `kubectl cluster-info dump` to support multi-container pod. ([#44088](https://github.com/kubernetes/kubernetes/pull/44088), [@xingzhou](https://github.com/xingzhou))
* Prints out status updates when running `kubefed init` ([#41849](https
-------- | -----------
[kubernetes-server-linux-amd64.tar.gz](https://dl.k8s.io/v1.7.0-alpha.2/kubernetes-server-linux-amd64.tar.gz) | `e14c0748789f6a1c3840ab05d0ad5b796a0f03722ee923f8208740f702c0bc19`
[kubernetes-server-linux-arm64.tar.gz](https://dl.k8s.io/v1.7.0-alpha.2/kubernetes-server-linux-arm64.tar.gz) | `270e0a6fcc0a2f38c8c6e8929a4a593535014bde88f69479a52c5b625bca435c`
[kubernetes-server-linux-arm.tar.gz](https://dl.k8s.io/v1.7.0-alpha.2/kubernetes-server-linux-arm.tar.gz) | `0bd58c2f8d8b6e8110354ccd71eb97eb873aca7b074ce9f83dab4f62a696e964`
[kubernetes-server-linux-ppc64le.tar.gz](https://dl.k8s.io/v1.7.0-alpha.2/kubernetes-server-linux-ppc64le.tar.gz) | `57a4a5dcdb573fb6dc08dbd53d0f196c66d245fa2159a92bf8da0d29128e486d`
[kubernetes-server-linux-s390x.tar.gz](https://dl.k8s.io/v1.7.0-alpha.2/kubernetx-amd64.tar.gz](https://dl.k8s.io/v1.7.0-alpha.2/kubernetes-client-linux-amd64.tar.gz) | `b9cb60ba71dfa144ed1e6f2116afd078782372d427912838c56f3b77a74afda0`
[kubernetes-client-linux-arm64.tar.gz](https://dl.k8s.io/v1.7.0-alpha.2/kubernetes-client-linux-arm64.tar.gz) | `bc0446c484dba91d8f1e32c0175b81dca5c6ff0ac9f5dd3f69cff529afb83aff`
[kubernetes-client-linux-arm.tar.gz](https://dl.k8s.io/v1.7.0-alpha.2/kubernetes-client-linux-arm.tar.gz) | `f794765ca98a2c0611fda32756250eff743c25b66cd4d973fc5720a55771c1c6`
[kubernetes-client-linux-ppc64le.tar.gz](https://dl.k8s.io/v1.7.0-alpha.2/kubernetes-client-linux-ppc64le.tar.gz) | `216cb6e96ba6af5ae259c069576fcd873c48a8a4e8918f5e08ac13427fbefd57`
[kubernetes-client-linux-s390x.tar.gz](https://dl.k8s.io/v1.7.0-alpha.2/kubernetes-client-linux-s390x.tar.gz) | `fb7903d028744fdfe3119ade6b2ee71532e3d69a82bd5834206fe84e50821253`
[kubernetes-client-windows-386.tar.gz](https://dl.k8s.io/v1.7.0-alpha.2/kubernetes-client-windows-386.tar.gz) | `6bdfbd12361f814c86f268dcc807314f322efe9390ca2d91087e617814e91684`
[kubernetes-client-wind

# v1.7.0-alpha.2

[Documentation](https://docs.k8s.io) & [Examples](https://releases.k8s.io/master/examples)

## Downloads for v1.
-------- | -----------gress/releases/tag/0.9.1), [0.9.2](https://github.com/kubernetes/ingress/releases/tag/0.9.2) ([#43098](https://gianges expected. ([#42842](https://github.com/kubernetes/kubernetes/pull/42842), [@ixdy](https://github.com/ixdy))
* list-resources: don't fail if the grep fails to match any resources ([#41933](https://github.com/kubernetes/kubernetes/pull/41933), [@ixdy](https://github.com/ixdy))
* Update gcr.io/google-containers/rescheduler to v0.2.2, which uses busybox as a base image instead of ubuntu. ([#41911](https://github.com/kubernetes/kubernetes/pull/41911), [@ixdy](https://github.com/ixdy))
* Backporting TPR fix to 1.4 ([#42380](https://github.com/kubernetes/kubernetes/pull/42380), [@foxish](https://github.com/foxish))
* Fix AWS device allocator to only use valid device names ([#41455](https://github.com/kubernetes/kubernetes/pull/41455), [@gnufied](https://github.com/gnufied))
* Reverts to looking up the current VM in vSphere using the machine's UUID, either obtained via sysfs or via the `vm-uuid` parameter in the cloud configuration file. ([#40892](https://github.com/kubernetes/kubernetes/pull/40892), [@robdaemothub.com/kubernetes/kubernetes/pull/43098), [@timstclair](https://github.com/timstclair))
* Patch CVE-2016-8859 in alpine based images: ([#42937](https://github.com/kubernetes/kubernetes/pull/42937), [@timstclair](https://github.com/timstclair))
    * - gcr.io/google-containers/etcd-empty-dir-cleanup
    * - gcr.io/google-containers/kube-dnsmasq-amd64
* Check if pathExists before performing Unmount ([#39311](https://github.com/kubernetes/kubernetes/pull/39311), [@rkouj](https://github.com/rkouj))
* NONE ([#39768](https://github.com/kubernetes/kubernetes/pull/39768), [@rkouj](https://github.com/rkouj))
* Unmount operation should not fail if volume is already unmounted ([#38547](https://github.com/kubernetes/kubernetes/pull/38547), [@rkouj](https://github.com/rkouj))
* Updates base image used for `kube-addon-manager` to latest `python:2.7-slim` and embedded `kubectl` to `v1.3.10`. No functionality ch
[kubernetes-node*.tar.gz](https://dl.k8s.io/v1.4.12/kubernetes-node*.tar.gz) | ``

## Changelog since v1.4.9

### Other notable changes

* kube-apiserver now drops unneeded path information if an older version of Windows kubectl sends it. ([#44586](https://github.com/kubernetes/kubernetes/pull/44586), [@mml](https://github.com/mml))
* Bump gcr.io/google_containers/glbc from 0.8.0 to 0.9.2. Release notes: [0.9.0](https://github.com/kubernetes/ingress/releases/tag/0.9.0), [0.9.1](https://github.com/kubernetes/in
### Client Binaries

filename | sha256 hash
-------- | -----------
[kubernetes-client-darwin-386.tar.gz](https://dl.k8s.io/v1.4.12/kubernetes-client-darwin-386.tar.gz) | `e91c76b6281fe7b488f2f30aeaeecde58a6df1a0e23f6c431b6dc9d1adc1ff1a`
[kubernetes-client-darwin-amd64.tar.gz](https://dl.k8s.io/v1.4.12/kubernetes-client-darwin-amd64.tar.gz) | `4504bc965bd1b5bcea91d18c3a879252026796fdd251b72e3541499c65ac20e0`
[kubernetes-client-linux-386.tar.gz](https://dl.k8s.io/v1.4.12/kubernetes-client-linux-386.tar.gz) | `adf1f939db2da0b87bca876d9bee69e0d6bf4ca

### Other notable changes

* kube-apiserver now drops unneeded path information if an older version of Windows kubectl sends it. ([#44585](https://github.com/kubernetes/kubernetes/pull/44585), [@mml](https://github.com/mml))
* Fix for kube-proxy healthcheck handling an update that simultaneously removes one port and adds another. ([#44365](https://github.com/kubernetes/kubernetes/pull/44365), [@MrHohn](https://github.com/MrHohn))
* Fix [broken service accounts when using dedicated service account key](https://github.com/kubernetes/kubernetes/issues/44285). ([#44169](https://github.com/kubernetes/kubernetes/pull/44169), [@mikedanese](https://github.com/mikedanese))
* Update to fluentd-gcp:1.28.3, rebased on ubuntu-slim:0.8 ([#43928](https://github.com/kubernetes/kubernetes/pull/43928), [@ixdy](https://github.com/ixdy))
* Fix polarity of NodePort logic to avoid leaked ports ([#43259](https://github.com/kubernetes/kubernetes/pull/43259), [@thockin](https://github.com/thockin))
* Upgrade golang versions to 1.7.5 ([#41771](https://github.com/kubernetes/kubernetes/pull/41771), [@cblecker](https://github.com/[kubernetes-client-windows-amd64.tar.gz](https://dl.k8s.io/v1.5.7/kubernetes-client-windows-amd64.tar.gz) | `f1f7e588dca059a4cbe97b4a28a983d346f93fc2bb0d4a1dbbb7d55a3e33caef`

### Server Binaries

filename | sha256 hash
-------- | -----------
[kubernetes-server-linux-amd64.tar.gz](https://dl.k8s.io/v1.5.7/kubernetes-server-linux-amd64.tar.gz) | `ae18d659811da316d4a8bbdce15c4396fdee0068f9d3247a72c3a23433fee44c`
[kubernetes-server-linux-arm64.tar.gz](https://dl.k8s.io/v1.5.7/kubernetes-server-linux-arm64.tar.gz) | `d56187d19b42848b7ff09e82c0452120c173ae56709cae88f96312ee7c41b0c4`


[Documentation](https://docs.k8s.io) & [Examples](https://releases.k8s.io/release-1.5/examples)

## Downloads for v1.5.7


filename | sha256 hash
-------- | -----------
[kubernetes.tar.gz](https://dl.k8s.io/v1.5.7/kubernetes.tar.gz) | `36bc0bcdce4060546f3fef7186f1207d30d5fd340e72113ff592966bd6684827`
[kubernetes-src.tar.gz](https://dl.k8s.io/v1.5.7/kubernetes-src.tar.gz) | `b329b02e9542049b9b85f8083a466e51799691bcf06fdf172b9c0f1cb61bdb6d`

### Client Binaries

filename | sha256 hash
-------- | -----------
[kubernetes-client-darwin-386.tar.gz](https://dl.k8s.io/v1.5.7/kubernetes-client-darwin-386.tar.gz) | `824ea7e5987e4ac7915b11fcd86658221a5a1e942a3f5210383435953509f96f`
[kubernetes-client-darwin-amd64.tar.gz](https://dl.k8s.io/v1.5.7/kubernetes-client-darwin-amd64.tar.gz) | `251a91eff457640066dd395393b16aae81850225db29207c07321b62fd9213ab`
[kubernetes-client-linux-386.tar.gz](https://dl.k8s.io/v1.5.7/kubernetes-client-linux-386.tar.gz) | `84c69d23010304308459ad520375fd017f57562f8a78b6157ef0ea093636a8b6`
[kubernetes-client-linux-amd64.tar.gz](https://dl.k8s.io/v1.5.7/kubernetes-client-linux-amd64.tar.gz) | `991e1eab65d1817ca3600e3ba3bc63ed86cf139a4669f84899f593ff684fb36c`
[kubernetes-client-linux-arm64.tar.gz](https://dl.k8s.io/v1.5.7/kubernetails only after cdk-addons are configured ([#44945](https://github.com/kubernetes/kubernetes/pull/44945), [@ktsakalozos](https://github.com/ktsakalozos))
* Added support to the pause action in the kubernetes-worker charm for new flag --delete-local-data ([#44931](https://github.com/kubernetes/kubernetes/pull/44931), [@chuckbutler](https://github.com/chuckbutler))
* Upgradlse positive "meaningful conflict" detection for strategic cated` group in the impersonated user automatically. ([#44076](https://github.com/kubernetes/kubernetes/pull/44076), [@liggitt](https://github.com/liggitt))

