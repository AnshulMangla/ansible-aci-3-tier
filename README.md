# Ansible ACI 3‑Tier Architecture Deployment

This repository contains Ansible playbooks to build a three‑tier (web /
app / db) architecture on a Cisco ACI fabric. It uses the official
cisco.aci Ansible Collection to automate tenant, VRF, BD, EPGs and
related ACI constructs.

## Prerequisites

-   Ansible v2.16 or newer.
-   Python 3.
-   Connectivity from your Ansible control node to the APIC.
-   Optional: Python virtual environment.

## Installing the ACI Ansible Module

``` bash
ansible-galaxy collection install cisco.aci
```

## Repository Structure

    .
    ├── external_vars.yml
    ├── three-tier-tenant-vrf.yml

## Configuration Steps

1.  Update `external_vars.yml`:

    -   Set `host` (APIC).
    -   Set `username`, `password`.
    -   Update tenant, VRF, BD, EPG variables as needed.

2.  Ensure facts gathering is disabled:

    ``` yaml
    gather_facts: false
    ```

## Running the Playbook

``` bash
ansible-playbook three-tier-tenant-vrf.yml -e @external_vars.yml
```

## Troubleshooting

-   Validate APIC reachability.

-   Check credentials.

-   List available modules:

    ``` bash
    ansible-doc -l | grep aci
    ```
