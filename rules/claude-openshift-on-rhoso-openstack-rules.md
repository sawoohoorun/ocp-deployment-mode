# Claude Documentation Rules: OpenShift Deployment Mode Comparison for RHOSO

## Purpose
Use this file as the governing instruction set whenever Claude creates, edits, reviews, or optimizes Markdown content about **OpenShift deployment mode comparison for Red Hat OpenStack Services on OpenShift (RHOSO)**.

The required comparison scope is:

- Installer-provisioned infrastructure (IPI)
- User-provisioned infrastructure (UPI)
- Platform-agnostic / installing on any platform
- How each OpenShift deployment approach affects RHOSO planning, installation, and day-2 operations

## Non-negotiable rules

1. **Use Red Hat official documentation only.**
   - Primary source domain: `docs.redhat.com`
   - Secondary Red Hat official source allowed only when docs are insufficient: `access.redhat.com` or `redhat.com`
   - Do not cite blogs, Medium, Reddit, vendor blogs, GitHub issues, personal notes, or AI-generated summaries.

2. **No assumption.**
   - Every factual claim must be traceable to a Red Hat official source.
   - If the source does not explicitly say something, write: `Not confirmed in the referenced Red Hat documentation`.
   - Do not infer supportability, limitations, or recommendations unless Red Hat documentation states them.

3. **Every section must include references.**
   - Each topic section must include a `References` subsection.
   - Each reference must include:
     - Document title
     - Product/version if visible
     - Section/chapter title if available
     - Full URL
     - Short note explaining what the source supports

4. **Separate OpenShift behavior from RHOSO behavior.**
   - OpenShift installation mode affects the substrate where RHOSO runs.
   - RHOSO itself is installed after an operational Red Hat OpenShift Container Platform cluster exists.
   - Clearly distinguish:
     - OpenShift cluster installation and operations
     - RHOSO Operator installation
     - RHOSO control plane creation
     - RHOSO data plane creation

5. **Version must be explicit.**
   - Prefer Red Hat OpenShift Container Platform 4.18 when RHOSO 18.0 is the target.
   - If a source uses a different OpenShift version, label it clearly and avoid implying it applies to all versions.
   - Do not mix source versions silently.

6. **Use evidence strength labels.**
   Each row or claim that compares modes must use one of these labels:
   - `Documented`: directly stated in Red Hat documentation.
   - `Derived from documented workflow`: assembled from documented steps without adding unsupported claims.
   - `Not confirmed`: not found in the cited Red Hat documentation.

7. **Do not make unsupported ranking claims.**
   Avoid claims like `best`, `recommended`, `easiest`, `lowest effort`, `production ready`, or `most scalable` unless Red Hat explicitly states it.
   When comparing effort, use documented workflow complexity, required manual tasks, and operational touchpoints.

8. **Use neutral wording.**
   Prefer:
   - `requires manual provisioning of...`
   - `installation program creates...`
   - `Machine API availability affects...`
   - `additional validation and configuration are required...`

   Avoid:
   - `obviously better`
   - `always choose`
   - `not suitable`
   - `unsupported` unless the source explicitly says unsupported.

## Required document structure

Any generated Markdown comparison must follow this structure:

```markdown
# OpenShift Deployment Mode Comparison for RHOSO

## 1. Executive summary
## 2. Source scope and evidence rules
## 3. Terminology
## 4. RHOSO dependency boundary
## 5. High-level comparison table
## 6. Installation workflow comparison
## 7. Day-2 operations comparison
## 8. Network operations comparison
## 9. Container runtime and node configuration comparison
## 10. Upgrade and lifecycle comparison
## 11. Storage and CSI comparison
## 12. Scale-out and machine management comparison
## 13. Difficulty and effort comparison
## 14. Pros and cons by mode
## 15. Limitations by mode
## 16. Decision checklist
## 17. Open questions / not-confirmed items
## 18. References
```

## Required comparison format per topic

Every major topic must include all of the following:

### A. Detailed comparison
Explain how IPI, UPI, and platform-agnostic differ for the topic. Include only sourced statements.

### B. Simple table comparison
Use this table format:

| Topic | IPI | UPI | Platform-agnostic | Evidence strength | Red Hat reference |
|---|---|---|---|---|---|
| Example | ... | ... | ... | Documented | Red Hat doc title + URL |

### C. Pros and cons
Use this table format:

| Mode | Pros | Cons / trade-offs | Evidence strength | Reference |
|---|---|---|---|---|
| IPI | ... | ... | ... | ... |
| UPI | ... | ... | ... | ... |
| Platform-agnostic | ... | ... | ... | ... |

### D. Detailed workflow
Use numbered steps. Each step must include a source or state `Source required`.

### E. Limitations
Use a table:

| Mode | Limitation | Impact | Confirmed by source? | Reference |
|---|---|---|---|---|

## Required topics and source expectations

### 1. RHOSO dependency boundary
Must state that RHOSO deployment begins on an operational Red Hat OpenShift Container Platform cluster. The RHOSO OpenStack Operator is installed on RHOCP, then the control plane and data plane are created.

Required source:
- Red Hat OpenStack Services on OpenShift 18.0, Deploying Red Hat OpenStack Services on OpenShift
- URL: https://docs.redhat.com/en/documentation/red_hat_openstack_services_on_openshift/18.0/html/deploying_red_hat_openstack_services_on_openshift/index

### 2. IPI behavior
Must cover that with installer-provisioned infrastructure, the installation program provisions infrastructure where supported and OpenShift manages cluster machines and operating system lifecycle as described by Red Hat documentation.

Required source:
- OpenShift Container Platform 4.18 Installation overview
- URL: https://docs.redhat.com/en/documentation/openshift_container_platform/4.18/html/installation_overview/ocp-installation-overview

### 3. UPI behavior
Must cover that with user-provisioned infrastructure, the user provisions infrastructure such as machines, networking, load balancing, storage, and related resources.

Required sources:
- OpenShift Container Platform 4.18 Installation overview
- URL: https://docs.redhat.com/en/documentation/openshift_container_platform/4.18/html/installation_overview/ocp-installation-overview
- OpenShift Container Platform 4.18 Installing on bare metal, User-provisioned infrastructure
- URL: https://docs.redhat.com/en/documentation/openshift_container_platform/4.18/html/installing_on_bare_metal/user-provisioned-infrastructure

### 4. Platform-agnostic behavior
Must cover installing on any platform and the use of RHCOS with Ignition configuration files generated by the installation program.

Required source:
- OpenShift Container Platform 4.18 Installing a cluster on any platform
- URL: https://docs.redhat.com/en/documentation/openshift_container_platform/4.18/html/installing_on_any_platform/installing-platform-agnostic

### 5. Machine API and scale-out
Must distinguish automated Machine API workflows from manual user-provisioned infrastructure workflows. Do not assume Machine API is available in every UPI/platform-agnostic deployment.

Required source:
- OpenShift Container Platform 4.18 Machine management, Manually scaling a compute machine set
- URL: https://docs.redhat.com/en/documentation/openshift_container_platform/4.18/html/machine_management/manually-scaling-machineset
- OpenShift Container Platform 4.18 Machine management, Managing user-provisioned infrastructure manually
- URL: https://docs.redhat.com/en/documentation/openshift_container_platform/4.18/html/machine_management/managing-user-provisioned-infrastructure-manually

### 6. Upgrades and node lifecycle
Must cover Cluster Version Operator, Machine Config Operator, node cordon/drain behavior, machine config pools, and update sequencing only as documented.

Required source:
- OpenShift Container Platform 4.18 Updating clusters
- URL: https://docs.redhat.com/en/documentation/openshift_container_platform/4.18/html-single/updating_clusters/index

### 7. Container runtime and node configuration
Must cover CRI-O, kubelet, systemd, kernel, and machine configuration only through MachineConfig, KubeletConfig, ContainerRuntimeConfig, or documented mechanisms.

Required source:
- OpenShift Container Platform 4.18 Machine configuration
- URL: https://docs.redhat.com/en/documentation/openshift_container_platform/4.18/html-single/machine_configuration/index

### 8. Storage and CSI
Must cover CSI as OpenShift’s mechanism to consume persistent storage from storage back ends implementing the CSI interface. Do not claim a specific CSI driver is required for RHOSO unless RHOSO documentation states it.

Required sources:
- OpenShift Container Platform 4.18 Storage documentation
- URL: https://docs.redhat.com/en/documentation/openshift_container_platform/4.18/html-single/storage/index
- RHOSO 18.0 Planning your deployment
- URL: https://docs.redhat.com/en/documentation/red_hat_openstack_services_on_openshift/18.0/html-single/planning_your_deployment/index

### 9. Network operations
Must distinguish platform networking required for OpenShift installation from RHOSO service networking. Include DNS, load balancer, API, application ingress, and any RHOSO networks only when directly documented.

Required sources:
- OpenShift Container Platform 4.18 Installation overview
- URL: https://docs.redhat.com/en/documentation/openshift_container_platform/4.18/html/installation_overview/ocp-installation-overview
- OpenShift Container Platform 4.18 Installing on bare metal, User-provisioned infrastructure
- URL: https://docs.redhat.com/en/documentation/openshift_container_platform/4.18/html/installing_on_bare_metal/user-provisioned-infrastructure
- RHOSO 18.0 Planning your deployment
- URL: https://docs.redhat.com/en/documentation/red_hat_openstack_services_on_openshift/18.0/html-single/planning_your_deployment/index

## Source index to use first

| Area | Official source | URL |
|---|---|---|
| OpenShift installation overview | OpenShift Container Platform 4.18 Installation overview | https://docs.redhat.com/en/documentation/openshift_container_platform/4.18/html/installation_overview/ocp-installation-overview |
| Installation method selection | OpenShift Container Platform 4.18 Selecting a cluster installation method and preparing it for users | https://docs.redhat.com/en/documentation/openshift_container_platform/4.18/html/installation_overview/installing-preparing |
| Platform-agnostic install | OpenShift Container Platform 4.18 Installing a cluster on any platform | https://docs.redhat.com/en/documentation/openshift_container_platform/4.18/html/installing_on_any_platform/installing-platform-agnostic |
| Bare-metal UPI | OpenShift Container Platform 4.18 User-provisioned infrastructure | https://docs.redhat.com/en/documentation/openshift_container_platform/4.18/html/installing_on_bare_metal/user-provisioned-infrastructure |
| Machine management | OpenShift Container Platform 4.18 Machine management | https://docs.redhat.com/en/documentation/openshift_container_platform/4.18/html-single/machine_management/index |
| Machine configuration | OpenShift Container Platform 4.18 Machine configuration | https://docs.redhat.com/en/documentation/openshift_container_platform/4.18/html-single/machine_configuration/index |
| Updates | OpenShift Container Platform 4.18 Updating clusters | https://docs.redhat.com/en/documentation/openshift_container_platform/4.18/html-single/updating_clusters/index |
| Storage | OpenShift Container Platform 4.18 Storage | https://docs.redhat.com/en/documentation/openshift_container_platform/4.18/html-single/storage/index |
| RHOSO planning | RHOSO 18.0 Planning your deployment | https://docs.redhat.com/en/documentation/red_hat_openstack_services_on_openshift/18.0/html-single/planning_your_deployment/index |
| RHOSO deployment | RHOSO 18.0 Deploying Red Hat OpenStack Services on OpenShift | https://docs.redhat.com/en/documentation/red_hat_openstack_services_on_openshift/18.0/html/deploying_red_hat_openstack_services_on_openshift/index |

## Quality gate before final output

Claude must check the final Markdown against this list before returning it:

- [ ] Every factual claim has a Red Hat official reference.
- [ ] No unsupported recommendation is presented as fact.
- [ ] IPI, UPI, and platform-agnostic are compared in every required topic.
- [ ] RHOSO installation is separated from OpenShift installation.
- [ ] Tables include evidence strength.
- [ ] Limitations are explicitly sourced or marked `Not confirmed`.
- [ ] Workflow steps are numbered and source-backed.
- [ ] No non-Red Hat sources are used.
- [ ] Source versions are visible.
