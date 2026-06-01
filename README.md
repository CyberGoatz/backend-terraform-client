# cybergoatz-terraform-client

Terraform orchestration client for CyberGoatz Platform sandbox provisioning.

This package is a CyberGoatz-maintained fork of CyberRangeCZ's
`backend-terraform-client`. It keeps the existing `crczp.terraform_driver`
Python import namespace for compatibility with the CRCZP/CyberRangeCZ backend
ecosystem, while publishing the fork under the separate
`cybergoatz-terraform-client` distribution name.

## Installation

```bash
pip install cybergoatz-terraform-client
```

## Usage

```python
from crczp.terraform_driver import CrczpTerraformClient
```

The client coordinates Terraform/OpenTofu sandbox provisioning across the
supported cloud drivers:

- OpenStack through `crczp-openstack-lib`
- AWS through `crczp-aws-lib`
- Azure through `cybergoatz-azure-lib`

## Package contents

- `crczp/terraform_driver` -- Terraform client implementation
- `crczp/terraform_driver/templates` -- Terraform backend template assets
- `pyproject.toml` -- package metadata and build configuration
- `.github/workflows/publish.yml` -- PyPI release workflow

## Releasing

The package version is read from `pyproject.toml`.

To publish a release:

1. Update `project.version` in `pyproject.toml`.
2. Commit the change.
3. Create and push a matching tag, for example `v1.0.2`.
4. The `Publish to PyPI` GitHub Actions workflow builds the source
   distribution and wheel, validates them with Twine, and publishes via PyPI
   trusted publishing.

## Attribution

This project is derived from CyberRangeCZ's `backend-terraform-client` package.
The original work is credited to Masaryk University and CyberSecurity Hub,
z.s.; their copyright and MIT license notices are retained.

CyberGoatz-specific changes are maintained by Chainscore Labs.
