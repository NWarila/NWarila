# Nicholas R. Warila

[![CI](https://github.com/NWarila/NWarila/actions/workflows/ci.yml/badge.svg)](https://github.com/NWarila/NWarila/actions/workflows/ci.yml)

Principal DevSecOps Engineer focused on cleared defense and Intelligence Community environments. I build secure delivery platforms, hardened infrastructure frameworks, and accreditation-aligned automation for teams that need repeatability, auditability, and real operational depth.

Career highlights include 5 accredited systems delivered, 100K+ endpoints standardized across 45+ networks, 700+ critical and high vulnerabilities remediated, and 99.999 percent availability sustained in mission-critical environments.

- **Clearance:** TS/SCI + (CI) Polygraph
- **Location:** North Springfield, VA
- **Contact:** [LinkedIn](https://linkedin.com/in/NWarila) | [Jobs@NicholasWarila.com](mailto:Jobs@NicholasWarila.com) | [Full background](RESUME.md)

## Current Focus

- Standardizing Terraform, Ansible, and Packer implementation patterns so secure infrastructure delivery is reusable instead of tribal knowledge.
- Building hardened Linux image and provisioning workflows, including ephemeral credential handling and CI/CD guardrails.
- Turning RMF, continuous monitoring, and release evidence into engineering systems instead of manual document drills.

## Selected Projects

- [Secure Packer Bootstrapper](https://github.com/nwarila-platform/secure-packer-bootstrapper): Per-build credential bootstrapper for Packer that generates ephemeral access material for STIG-compliant build workflows.
- [Proxmox Packer Framework](https://github.com/nwarila-platform/proxmox-packer-framework): Repeatable, STIG-compliant Linux VM template builds for Proxmox across multiple distributions.
- [Proxmox Terraform Framework](https://github.com/nwarila-platform/proxmox-terraform-framework): Terraform framework for deploying and configuring Proxmox VM templates and supporting infrastructure.
- [Ansible Framework](https://github.com/nwarila-platform/ansible-framework): Reusable Ansible framework for secure configuration, drift detection, remediation, and baseline enforcement.

More public work: [nwarila-platform](https://github.com/nwarila-platform) | [NWarila](https://github.com/NWarila?tab=repositories)

### Additional Public Work

- [Talos Cluster](https://github.com/nwarila-platform/talos-cluster): Bare-metal Talos Linux Kubernetes platform with GitOps bootstrap, policy-as-code, and hardware-first operational documentation.
- [GitHub Terraform Framework](https://github.com/nwarila-platform/github-terraform-framework): Terraform framework for managing GitHub repositories, rulesets, security defaults, and shared account-level governance as code.

### Framework Templates and Deployer

Canonical type-templates that the production frameworks above derive from. Each template owns a machine-readable contract, reusable workflows pinned by SHA, OPA policy, drift gating against [`NWarila/.github`](https://github.com/NWarila/.github), and Diátaxis-organized documentation with ADRs at org, template, and repo tiers.

- [terraform-runner-template](https://github.com/NWarila/terraform-runner-template): Canonical thin-runner pattern for Terraform consumers — data-only deployers that overlay inventory into a SHA-pinned framework at deploy time. Contract validator + negative fixtures enforce the boundary.
- [terraform-framework-template](https://github.com/NWarila/terraform-framework-template): Do-nothing reference Terraform framework. Demonstrates the framework module shape (variables, locals composition, dynamic blocks, terraform test) without provider semantics.
- [ansible-framework-template](https://github.com/NWarila/ansible-framework-template): Reference Ansible framework with a production-shaped role-loader pattern (state machine, OS overlay precedence, override merge, secure temp-dir lifecycle) running credential-free against localhost.
- [packer-framework-template](https://github.com/NWarila/packer-framework-template): Reference Packer framework with rigorous input validation (path-traversal, injection-safety), build-aware OPA policy, and a credential-free reference build that exercises the manifest contract.
- [github-terraform-runner](https://github.com/NWarila/github-terraform-runner): Real consumer of `terraform-runner-template` — the deployer that manages every repository in this portfolio as code, with org and template baselines drift-gated on every PR.

## Selected Certifications

- **Security and compliance:** CompTIA SecurityX (CE), Security+ (CE), Certified Ethical Hacker (CEH), Certified Network Defense Architect (CNDA)
- **Cloud and platform:** AWS Certified Solutions Architect - Professional, AWS Certified DevOps Engineer - Professional, HashiCorp Terraform Associate, HashiCorp Vault Associate, GitLab Certified CI/CD Associate
- **Systems:** CompTIA Linux+, LPIC-1 Linux Administrator, Network+, A+

## Core Technical Stack

- **Infrastructure and automation:** Terraform, Ansible, Packer, Python, PowerShell, Bash
- **Delivery and platform engineering:** GitLab CI/CD, GitHub Actions, Jenkins, ArgoCD, policy-as-code, test and release gates
- **Cloud and virtualization:** AWS, AWS GovCloud, Azure, Proxmox, VMware vSphere, Docker, Kubernetes
- **Security and compliance:** DISA STIG, SCAP remediation, NIST RMF, ICD 503, JSIG, Zero Trust, vulnerability remediation, eMASS
- **Systems and identity:** Windows Server, RHEL, Ubuntu, Active Directory, Group Policy, PKI, DNS, DHCP, MFA

## Inside This Repo

- [`RESUME.md`](RESUME.md): assembled long-form professional background, auto-synced from a private resume repository
- [`.github/workflows/resume-sync.yml`](.github/workflows/resume-sync.yml): manual workflow used to sync resume release artifacts until the automated release flow is ready
- [`DESIGN.md`](DESIGN.md): why this repo is structured the way it is
- Community health defaults live in [`NWarila/.github`](https://github.com/NWarila/.github); this repo intentionally avoids duplicating those standards locally
