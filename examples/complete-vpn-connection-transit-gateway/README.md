# Complete VPN Connection with Transit Gateway

Configuration in this directory creates two VPN Connections (one per Customer Gateway) linked to Transit Gateway which is connected to private subnets of VPC.

## Usage

To run this example you need to execute:

```bash
$ terraform init
$ terraform plan
$ terraform apply
```

Run `terraform destroy` when you don't need these resources.

<!-- BEGINNING OF PRE-COMMIT-TERRAFORM DOCS HOOK -->
## Requirements

| Name | Version |
|------|---------|
| terraform | >= 0.12.21 |
| aws | >= 3.22 |

## Providers

| Name | Version |
|------|---------|
| aws | >= 3.22 |

## Modules

| Name | Source | Version |
|------|--------|---------|
| vpc | terraform-aws-modules/vpc/aws | ~> 2.0 |
| vpn_gateway_1 | ../../ |  |
| vpn_gateway_2 | ../../ |  |

## Resources

| Name |
|------|
| [aws_ec2_transit_gateway](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/ec2_transit_gateway) |
| [aws_ec2_transit_gateway_vpc_attachment](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/ec2_transit_gateway_vpc_attachment) |

## Inputs

| Name | Description | Type | Default | Required |
|------|-------------|------|---------|:--------:|
| vpc\_private\_subnets | List of private subnets | `list(string)` | <pre>[<br>  "10.10.11.0/24",<br>  "10.10.12.0/24",<br>  "10.10.13.0/24"<br>]</pre> | no |
| vpc\_public\_subnets | List of public subnets | `list(string)` | <pre>[<br>  "10.10.1.0/24",<br>  "10.10.2.0/24",<br>  "10.10.3.0/24"<br>]</pre> | no |

## Outputs

| Name | Description |
|------|-------------|
| vpn\_connection\_id | VPN id |
| vpn\_connection\_transit\_gateway\_attachment\_id | VPN TGW attachment id |
| vpn\_connection\_tunnel1\_address | Tunnel1 address |
| vpn\_connection\_tunnel1\_cgw\_inside\_address | Tunnel1 CGW address |
| vpn\_connection\_tunnel1\_vgw\_inside\_address | Tunnel1 VGW address |
| vpn\_connection\_tunnel2\_address | Tunnel2 address |
| vpn\_connection\_tunnel2\_cgw\_inside\_address | Tunnel2 CGW address |
| vpn\_connection\_tunnel2\_vgw\_inside\_address | Tunnel2 VGW address |
<!-- END OF PRE-COMMIT-TERRAFORM DOCS HOOK -->
