# GCP minimal network

This module will create a single VPC network in a single GCE [Region] for single-leg
deployments. A NAT is not included in this module, so instances are required to
have a public IP address to access the internet.

![gcp-min.png](gcp-min.png)

To use this module within a solutions context:

```hcl
module "network_min" {
    source = "../../../../../google/terraform/network/min/"
    gcpProjectId = var.gcpProjectId
    gcpRegion = var.gcpRegion
    projectPrefix = var.projectPrefix
    buildSuffix = var.buildSuffix
}
```

<!-- markdownlint-disable no-inline-html -->
<!-- BEGINNING OF PRE-COMMIT-TERRAFORM DOCS HOOK -->
## Requirements

| Name | Version |
|------|---------|
| terraform | ~> 0.14.5 |
| google | ~> 3.54 |

## Providers

No provider.

## Inputs

| Name | Description | Type | Default | Required |
|------|-------------|------|---------|:--------:|
| buildSuffix | random build suffix for resources | `string` | n/a | yes |
| gcpProjectId | gcp project id | `string` | n/a | yes |
| gcpRegion | region where gke is deployed | `string` | n/a | yes |
| projectPrefix | prefix for resources | `string` | `"demo"` | no |

## Outputs

| Name | Description |
|------|-------------|
| subnets | A map of subnetworks created by module, keyed by usage context. |
| vpcs | A map of VPC networks created by module, keyed by usage context. |

<!-- END OF PRE-COMMIT-TERRAFORM DOCS HOOK -->
<!-- markdownlint-enable no-inline-html -->
