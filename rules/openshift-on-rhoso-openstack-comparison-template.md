# OpenShift Deployment Mode Comparison for RHOSO

> Use this template with `claude-openshift-rhoso-doc-rules.md`. Do not fill any section with assumptions. Replace every `Source required` entry with a Red Hat official reference before publishing.

## 1. Executive summary

Summarize the comparison between IPI, UPI, and platform-agnostic OpenShift deployment modes for RHOSO.

Required points:

- RHOSO is deployed on an operational Red Hat OpenShift Container Platform cluster.
- The OpenShift deployment mode affects infrastructure provisioning, day-2 operations, machine management, network dependencies, storage integration, and scale-out workflow.
- Do not state a recommended mode unless a Red Hat source explicitly supports the recommendation.

References:

| Source | URL | Supports |
|---|---|---|
| RHOSO 18.0 Deploying Red Hat OpenStack Services on OpenShift | https://docs.redhat.com/en/documentation/red_hat_openstack_services_on_openshift/18.0/html/deploying_red_hat_openstack_services_on_openshift/index | RHOSO Operator, control plane, and data plane deployment boundary |
| OpenShift Container Platform 4.18 Installation overview | https://docs.redhat.com/en/documentation/openshift_container_platform/4.18/html/installation_overview/ocp-installation-overview | OpenShift installation mode definitions |

## 2. Source scope and evidence rules

| Rule | Requirement |
|---|---|
| Source type | Red Hat official documentation only |
| Unsupported claims | Mark as `Not confirmed in the referenced Red Hat documentation` |
| Version handling | State OpenShift and RHOSO documentation versions explicitly |
| Evidence label | Use `Documented`, `Derived from documented workflow`, or `Not confirmed` |

## 3. Terminology

| Term | Definition | Evidence strength | Reference |
|---|---|---|---|
| IPI | Source required | Source required | Source required |
| UPI | Source required | Source required | Source required |
| Platform-agnostic install | Source required | Source required | Source required |
| RHOSO control plane | Source required | Source required | Source required |
| RHOSO data plane | Source required | Source required | Source required |

## 4. RHOSO dependency boundary

### Detailed comparison

Explain what belongs to OpenShift deployment and what belongs to RHOSO deployment.

| Layer | Scope | IPI impact | UPI impact | Platform-agnostic impact | Evidence strength | Reference |
|---|---|---|---|---|---|---|
| OpenShift cluster | Cluster infrastructure, nodes, networking, storage integration | Source required | Source required | Source required | Source required | Source required |
| RHOSO Operator | Installed on operational RHOCP cluster | Source required | Source required | Source required | Source required | Source required |
| RHOSO control plane | Created after Operator installation | Source required | Source required | Source required | Source required | Source required |
| RHOSO data plane | Created by RHOSO data plane workflow | Source required | Source required | Source required | Source required | Source required |

### Limitations

| Mode | Limitation | Impact | Confirmed by source? | Reference |
|---|---|---|---|---|
| IPI | Source required | Source required | Source required | Source required |
| UPI | Source required | Source required | Source required | Source required |
| Platform-agnostic | Source required | Source required | Source required | Source required |

## 5. High-level comparison table

| Comparison area | IPI | UPI | Platform-agnostic | Evidence strength | Red Hat reference |
|---|---|---|---|---|---|
| Infrastructure provisioning | Source required | Source required | Source required | Source required | Source required |
| Bootstrap workflow | Source required | Source required | Source required | Source required | Source required |
| Load balancer and DNS responsibility | Source required | Source required | Source required | Source required | Source required |
| Machine API / machine sets | Source required | Source required | Source required | Source required | Source required |
| Node scale-out workflow | Source required | Source required | Source required | Source required | Source required |
| Upgrade workflow | Source required | Source required | Source required | Source required | Source required |
| Storage / CSI integration | Source required | Source required | Source required | Source required | Source required |
| RHOSO impact | Source required | Source required | Source required | Source required | Source required |

## 6. Installation workflow comparison

### Detailed comparison

Write a sourced comparison of installation workflow differences.

### Simple table comparison

| Topic | IPI | UPI | Platform-agnostic | Evidence strength | Red Hat reference |
|---|---|---|---|---|---|
| Installer role | Source required | Source required | Source required | Source required | Source required |
| Required pre-created infrastructure | Source required | Source required | Source required | Source required | Source required |
| RHCOS / Ignition handling | Source required | Source required | Source required | Source required | Source required |
| Bootstrap process | Source required | Source required | Source required | Source required | Source required |

### Pros and cons

| Mode | Pros | Cons / trade-offs | Evidence strength | Reference |
|---|---|---|---|---|
| IPI | Source required | Source required | Source required | Source required |
| UPI | Source required | Source required | Source required | Source required |
| Platform-agnostic | Source required | Source required | Source required | Source required |

### Detailed workflow

#### IPI workflow
1. Source required
2. Source required
3. Source required

#### UPI workflow
1. Source required
2. Source required
3. Source required

#### Platform-agnostic workflow
1. Source required
2. Source required
3. Source required

### Limitations

| Mode | Limitation | Impact | Confirmed by source? | Reference |
|---|---|---|---|---|
| IPI | Source required | Source required | Source required | Source required |
| UPI | Source required | Source required | Source required | Source required |
| Platform-agnostic | Source required | Source required | Source required | Source required |

## 7. Day-2 operations comparison

Cover operational responsibility after installation.

| Topic | IPI | UPI | Platform-agnostic | Evidence strength | Red Hat reference |
|---|---|---|---|---|---|
| Machine lifecycle | Source required | Source required | Source required | Source required | Source required |
| Node replacement | Source required | Source required | Source required | Source required | Source required |
| OS and runtime configuration | Source required | Source required | Source required | Source required | Source required |
| RHOSO Operator lifecycle | Source required | Source required | Source required | Source required | Source required |

## 8. Network operations comparison

Cover API, Ingress, DNS, load balancing, cluster network, and RHOSO network dependencies only as documented.

| Topic | IPI | UPI | Platform-agnostic | Evidence strength | Red Hat reference |
|---|---|---|---|---|---|
| API load balancing | Source required | Source required | Source required | Source required | Source required |
| Application Ingress | Source required | Source required | Source required | Source required | Source required |
| DNS records | Source required | Source required | Source required | Source required | Source required |
| RHOSO service networks | Source required | Source required | Source required | Source required | Source required |

## 9. Container runtime and node configuration comparison

Cover CRI-O, kubelet, systemd, kernel, MachineConfig, KubeletConfig, and ContainerRuntimeConfig.

| Topic | IPI | UPI | Platform-agnostic | Evidence strength | Red Hat reference |
|---|---|---|---|---|---|
| CRI-O configuration | Source required | Source required | Source required | Source required | Source required |
| Kubelet configuration | Source required | Source required | Source required | Source required | Source required |
| OS configuration | Source required | Source required | Source required | Source required | Source required |
| MachineConfig impact | Source required | Source required | Source required | Source required | Source required |

## 10. Upgrade and lifecycle comparison

| Topic | IPI | UPI | Platform-agnostic | Evidence strength | Red Hat reference |
|---|---|---|---|---|---|
| Cluster update mechanism | Source required | Source required | Source required | Source required | Source required |
| Machine Config Operator behavior | Source required | Source required | Source required | Source required | Source required |
| Machine config pools | Source required | Source required | Source required | Source required | Source required |
| Node drain/cordon behavior | Source required | Source required | Source required | Source required | Source required |
| RHOSO lifecycle relationship | Source required | Source required | Source required | Source required | Source required |

## 11. Storage and CSI comparison

| Topic | IPI | UPI | Platform-agnostic | Evidence strength | Red Hat reference |
|---|---|---|---|---|---|
| Persistent storage responsibility | Source required | Source required | Source required | Source required | Source required |
| CSI driver selection | Source required | Source required | Source required | Source required | Source required |
| Default storage availability | Source required | Source required | Source required | Source required | Source required |
| RHOSO storage dependency | Source required | Source required | Source required | Source required | Source required |

## 12. Scale-out and machine management comparison

| Topic | IPI | UPI | Platform-agnostic | Evidence strength | Red Hat reference |
|---|---|---|---|---|---|
| Adding worker nodes | Source required | Source required | Source required | Source required | Source required |
| Machine sets | Source required | Source required | Source required | Source required | Source required |
| Manual node provisioning | Source required | Source required | Source required | Source required | Source required |
| RHOSO scale impact | Source required | Source required | Source required | Source required | Source required |

## 13. Difficulty and effort comparison

Do not rank difficulty by opinion. Compare only by documented tasks and operational responsibility.

| Effort area | IPI documented tasks | UPI documented tasks | Platform-agnostic documented tasks | Evidence strength | Reference |
|---|---|---|---|---|---|
| Pre-install preparation | Source required | Source required | Source required | Source required | Source required |
| Bootstrap | Source required | Source required | Source required | Source required | Source required |
| Network setup | Source required | Source required | Source required | Source required | Source required |
| Storage setup | Source required | Source required | Source required | Source required | Source required |
| Scale-out | Source required | Source required | Source required | Source required | Source required |
| Upgrade | Source required | Source required | Source required | Source required | Source required |

## 14. Pros and cons by mode

| Mode | Pros | Cons / trade-offs | Evidence strength | Reference |
|---|---|---|---|---|
| IPI | Source required | Source required | Source required | Source required |
| UPI | Source required | Source required | Source required | Source required |
| Platform-agnostic | Source required | Source required | Source required | Source required |

## 15. Limitations by mode

| Mode | Limitation | Operational impact | RHOSO impact | Confirmed by source? | Reference |
|---|---|---|---|---|---|
| IPI | Source required | Source required | Source required | Source required | Source required |
| UPI | Source required | Source required | Source required | Source required | Source required |
| Platform-agnostic | Source required | Source required | Source required | Source required | Source required |

## 16. Decision checklist

Use this only as a neutral checklist. Do not turn it into a recommendation unless Red Hat documentation directly supports the recommendation.

| Question | Why it matters | Evidence source |
|---|---|---|
| Is the target platform supported by IPI? | Determines whether installer-provisioned infrastructure is available | Source required |
| Who owns load balancer and DNS provisioning? | Affects installation and operations responsibility | Source required |
| Is Machine API operational for this deployment? | Affects machine sets and scale-out workflow | Source required |
| What CSI storage backend is required? | Affects RHOSO persistent storage readiness | Source required |
| What RHOSO control plane and data plane topology is required? | Affects capacity and network planning | Source required |

## 17. Open questions / not-confirmed items

| Item | Why it is not confirmed | Needed source |
|---|---|---|
| Source required | Source required | Source required |

## 18. References

| Area | Official source | URL | Notes |
|---|---|---|---|
| OpenShift installation overview | OpenShift Container Platform 4.18 Installation overview | https://docs.redhat.com/en/documentation/openshift_container_platform/4.18/html/installation_overview/ocp-installation-overview | Installation modes and infrastructure responsibility |
| Installation method selection | OpenShift Container Platform 4.18 Selecting a cluster installation method and preparing it for users | https://docs.redhat.com/en/documentation/openshift_container_platform/4.18/html/installation_overview/installing-preparing | Installation method selection and platform-agnostic notes |
| Platform-agnostic install | OpenShift Container Platform 4.18 Installing a cluster on any platform | https://docs.redhat.com/en/documentation/openshift_container_platform/4.18/html/installing_on_any_platform/installing-platform-agnostic | RHCOS and Ignition workflow |
| Bare-metal UPI | OpenShift Container Platform 4.18 User-provisioned infrastructure | https://docs.redhat.com/en/documentation/openshift_container_platform/4.18/html/installing_on_bare_metal/user-provisioned-infrastructure | User-provisioned load balancing and infrastructure |
| Machine management | OpenShift Container Platform 4.18 Machine management | https://docs.redhat.com/en/documentation/openshift_container_platform/4.18/html-single/machine_management/index | Machine sets and user-provisioned infrastructure management |
| Machine configuration | OpenShift Container Platform 4.18 Machine configuration | https://docs.redhat.com/en/documentation/openshift_container_platform/4.18/html-single/machine_configuration/index | CRI-O, kubelet, systemd, kernel, MachineConfig |
| Updates | OpenShift Container Platform 4.18 Updating clusters | https://docs.redhat.com/en/documentation/openshift_container_platform/4.18/html-single/updating_clusters/index | Cluster update process and MCO behavior |
| Storage | OpenShift Container Platform 4.18 Storage | https://docs.redhat.com/en/documentation/openshift_container_platform/4.18/html-single/storage/index | CSI and persistent storage behavior |
| RHOSO planning | RHOSO 18.0 Planning your deployment | https://docs.redhat.com/en/documentation/red_hat_openstack_services_on_openshift/18.0/html-single/planning_your_deployment/index | RHOSO planning prerequisites and architecture |
| RHOSO deployment | RHOSO 18.0 Deploying Red Hat OpenStack Services on OpenShift | https://docs.redhat.com/en/documentation/red_hat_openstack_services_on_openshift/18.0/html/deploying_red_hat_openstack_services_on_openshift/index | RHOSO Operator, control plane, and data plane deployment |
