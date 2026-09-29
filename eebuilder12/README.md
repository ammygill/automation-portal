# eebuilder12

just testing EE

## What's included

### Ansible collections

| Collection | Version | Source |
|---|---|---|
| opentraining.mta_dev_lightspeed | - | Github (github-public) |

### Python packages

- `BOTO3`

### System packages

- `gcc`

## Details

- **Tags:** `new`

- **Image registry:** `aap-aap.apps.cluster-rmw6v.dyn.redhatworkshops.io/eebuilder:eebuilder`

## Use this execution environment

If your EE uses collections from private sources (Automation Hub, private automation hub), update the token settings in `ansible.cfg` before building.


Log in to the registry and pull the image:

```bash
podman login aap-aap.apps.cluster-rmw6v.dyn.redhatworkshops.io
podman pull aap-aap.apps.cluster-rmw6v.dyn.redhatworkshops.io/eebuilder:eebuilder
```

If the registry uses a self-signed certificate, you may need to append `--tls-verify=false` to each `podman` command.

To use it in Ansible Automation Platform:

1. Go to **Automation Execution** > **Infrastructure** > **Execution Environments**.
2. Click **Create execution environment** and enter the image URL: `aap-aap.apps.cluster-rmw6v.dyn.redhatworkshops.io/eebuilder:eebuilder`
3. Select this execution environment in your job templates.

## Build details

- **Base image:** `registry.redhat.io/ansible-automation-platform/ee-minimal-rhel9:2.18`
- **Definition file:** `eebuilder12.yml`
- **Template file:** `eebuilder12-template.yml` - import this into Ansible automation portal to let others create EEs from the same starting point.

To make changes, use this EE's template in Ansible automation portal or rebuild manually with `ansible-builder` and the definition file.
