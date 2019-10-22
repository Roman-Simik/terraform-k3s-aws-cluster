### Terraform K3S AWS Cluster

This module supports creating a k3s cluster with a postgres backend in AWS. By default it will also install Rancher Server.

<!-- BEGINNING OF PRE-COMMIT-TERRAFORM DOCS HOOK -->
## Inputs

| Name | Description | Type | Default | Required |
|------|-------------|:----:|:-----:|:-----:|
| agent\_image\_id | AMI to use for k3s agent instances | string | `"null"` | no |
| agent\_instance\_ssh\_user | Username for sshing into instances | string | `"ubuntu"` | no |
| agent\_instance\_type |  | string | `"m5.large"` | no |
| agent\_node\_count | Number of agent nodes to launch | number | `"3"` | no |
| aws\_azs | List of AWS Availability Zones in the VPC | list | `"null"` | no |
| aws\_profile | Name of the AWS Profile to use for authentication | string | `"null"` | no |
| aws\_region |  | string | `"null"` | no |
| certmanager\_version | Version of cert-manager to install | string | `"0.9.1"` | no |
| create\_external\_nlb | Boolean that defines whether or not to create an external load balancer | bool | `"true"` | no |
| db\_instance\_type |  | string | `"db.r5.large"` | no |
| db\_name | Name of database to create in RDS | string | `"null"` | no |
| db\_node\_count | Number of RDS database instances to launch | number | `"1"` | no |
| db\_pass | Password for RDS user | string | n/a | yes |
| db\_user | Username for RDS database | string | n/a | yes |
| domain |  | string | `"eng.rancher.space"` | no |
| extra\_agent\_security\_groups | Additional security groups to attach to k3s agent instances | list | `[]` | no |
| extra\_server\_security\_groups | Additional security groups to attach to k3s server instances | list | `[]` | no |
| install\_certmanager | Boolean that defines whether or not to install Cert-Manager | bool | `"true"` | no |
| install\_ingress | Boolean that defines whether or not to install nginx-ingress | bool | `"true"` | no |
| install\_k3s\_version | Version of K3S to install | string | `"0.9.1"` | no |
| install\_rancher | Boolean that defines whether or not to install Rancher | bool | `"true"` | no |
| k3s\_cluster\_secret | Override to set k3s cluster registration secret | string | `"null"` | no |
| letsencrypt\_email | LetsEncrypt email address to use | string | `"none@none.com"` | no |
| name | Name for deployment | string | `"rancher-demo"` | no |
| private\_subnets | List of private subnet ids. | list | `[]` | no |
| private\_subnets\_cidr\_blocks | List of cidr_blocks of private subnets | list | `[]` | no |
| public\_subnets | List of public subnet ids. | list | `[]` | no |
| public\_subnets\_cidr\_blocks | List of cidr_blocks of public subnets | list | `[]` | no |
| r53\_domain | DNS domain for Route53 zone (defaults to domain if unset) | string | `""` | no |
| rancher\_chart | Helm chart to use for Rancher install | string | `"rancher-stable/rancher"` | no |
| rancher\_password |  | string | n/a | yes |
| rancher\_version | Version of Rancher to install | string | `"2.3.1"` | no |
| registration\_command | Registration command to import cluster into Rancher. Should not be used when installing Rancher in this same cluster | string | `""` | no |
| server\_image\_id | AMI to use for k3s server instances | string | `"null"` | no |
| server\_instance\_ssh\_user | Username for sshing into instances | string | `"ubuntu"` | no |
| server\_instance\_type |  | string | `"m5.large"` | no |
| server\_node\_count | Number of server nodes to launch | number | `"1"` | no |
| skip\_final\_snapshot | Boolean that defines whether or not the final snapshot should be created on RDS cluster deletion | bool | `"true"` | no |
| ssh\_keys | SSH keys to inject into Rancher instances | list | `[]` | no |
| storage\_cafile | Location to download RDS CA Bundle | string | `"/srv/rds-combined-ca-bundle.pem"` | no |
| use\_default\_vpc | Should the default VPC for the region selected be used for Rancher | bool | `"true"` | no |
| vpc\_id | If use_default_vpc is false, the vpc id that Rancher should use | string | `"null"` | no |

## Outputs

| Name | Description |
|------|-------------|
| rancher\_admin\_password |  |
| rancher\_token |  |
| rancher\_url |  |

<!-- END OF PRE-COMMIT-TERRAFORM DOCS HOOK -->
