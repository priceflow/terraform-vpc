# terraform-vpc
vpc terraform module
## Inputs

| Name | Description | Type | Default | Required |
|------|-------------|:----:|:-----:|:-----:|
| amazon\_side\_asn | The Autonomous System Number (ASN) for the Amazon side of the gateway. By default the virtual private gateway is created with the current default Amazon ASN. | string | `64512` | no |
| assign\_generated\_ipv6\_cidr\_block | Requests an Amazon-provided IPv6 CIDR block with a /56 prefix length for the VPC. You cannot specify the range of IP addresses, or the size of the CIDR block | string | `false` | no |
| azs | A list of availability zones in the region | list | `<list>` | no |
| cidr | The CIDR block for the VPC. Default value is a valid CIDR, but not acceptable by AWS and should be overridden | string | `0.0.0.0/0` | no |
| create\_database\_internet\_gateway\_route | Controls if an internet gateway route for public database access should be created | string | `false` | no |
| create\_database\_subnet\_group | Controls if database subnet group should be created | string | `true` | no |
| create\_database\_subnet\_route\_table | Controls if separate route table for database should be created | string | `false` | no |
| create\_elasticache\_subnet\_route\_table | Controls if separate route table for elasticache should be created | string | `false` | no |
| create\_redshift\_subnet\_route\_table | Controls if separate route table for redshift should be created | string | `false` | no |
| create\_vpc | Controls if VPC should be created (it affects almost all resources) | string | `true` | no |
| database\_route\_table\_tags | Additional tags for the database route tables | map | `<map>` | no |
| database\_subnet\_group\_tags | Additional tags for the database subnet group | map | `<map>` | no |
| database\_subnet\_suffix | Suffix to append to database subnets name | string | `db` | no |
| database\_subnet\_tags | Additional tags for the database subnets | map | `<map>` | no |
| database\_subnets | A list of database subnets | list | `<list>` | no |
| dhcp\_options\_domain\_name | Specifies DNS name for DHCP options set | string | `` | no |
| dhcp\_options\_domain\_name\_servers | Specify a list of DNS server addresses for DHCP options set, default to AWS provided | list | `<list>` | no |
| dhcp\_options\_netbios\_name\_servers | Specify a list of netbios servers for DHCP options set | list | `<list>` | no |
| dhcp\_options\_netbios\_node\_type | Specify netbios node_type for DHCP options set | string | `` | no |
| dhcp\_options\_ntp\_servers | Specify a list of NTP servers for DHCP options set | list | `<list>` | no |
| dhcp\_options\_tags | Additional tags for the DHCP option set | map | `<map>` | no |
| elasticache\_route\_table\_tags | Additional tags for the elasticache route tables | map | `<map>` | no |
| elasticache\_subnet\_suffix | Suffix to append to elasticache subnets name | string | `elasticache` | no |
| elasticache\_subnet\_tags | Additional tags for the elasticache subnets | map | `<map>` | no |
| elasticache\_subnets | A list of elasticache subnets | list | `<list>` | no |
| enable\_dhcp\_options | Should be true if you want to specify a DHCP options set with a custom domain name, DNS servers, NTP servers, netbios servers, and/or netbios server type | string | `false` | no |
| enable\_dns\_hostnames | Should be true to enable DNS hostnames in the VPC | string | `false` | no |
| enable\_dns\_support | Should be true to enable DNS support in the VPC | string | `true` | no |
| enable\_dynamodb\_endpoint | Should be true if you want to provision a DynamoDB endpoint to the VPC | string | `false` | no |
| enable\_nat\_gateway | Should be true if you want to provision NAT Gateways for each of your private networks | string | `false` | no |
| enable\_s3\_endpoint | Should be true if you want to provision an S3 endpoint to the VPC | string | `false` | no |
| enable\_vpn\_gateway | Should be true if you want to create a new VPN Gateway resource and attach it to the VPC | string | `false` | no |
| external\_nat\_ip\_ids | List of EIP IDs to be assigned to the NAT Gateways (used in combination with reuse_nat_ips) | list | `<list>` | no |
| igw\_tags | Additional tags for the internet gateway | map | `<map>` | no |
| instance\_tenancy | A tenancy option for instances launched into the VPC | string | `default` | no |
| intra\_route\_table\_tags | Additional tags for the intra route tables | map | `<map>` | no |
| intra\_subnet\_tags | Additional tags for the intra subnets | map | `<map>` | no |
| intra\_subnets | A list of intra subnets | list | `<list>` | no |
| map\_public\_ip\_on\_launch | Should be false if you do not want to auto-assign public IP on launch | string | `true` | no |
| name | Name to be used on all the resources as identifier | string | `` | no |
| nat\_eip\_tags | Additional tags for the NAT EIP | map | `<map>` | no |
| nat\_gateway\_tags | Additional tags for the NAT gateways | map | `<map>` | no |
| one\_nat\_gateway\_per\_az | Should be true if you want only one NAT Gateway per availability zone. Requires `var.azs` to be set, and the number of `public_subnets` created to be greater than or equal to the number of availability zones specified in `var.azs`. | string | `false` | no |
| private\_route\_table\_tags | Additional tags for the private route tables | map | `<map>` | no |
| private\_subnet\_suffix | Suffix to append to private subnets name | string | `private` | no |
| private\_subnet\_tags | Additional tags for the private subnets | map | `<map>` | no |
| private\_subnets | A list of private subnets inside the VPC | list | `<list>` | no |
| propagate\_private\_route\_tables\_vgw | Should be true if you want route table propagation | string | `false` | no |
| propagate\_public\_route\_tables\_vgw | Should be true if you want route table propagation | string | `false` | no |
| public\_route\_table\_tags | Additional tags for the public route tables | map | `<map>` | no |
| public\_subnet\_suffix | Suffix to append to public subnets name | string | `public` | no |
| public\_subnet\_tags | Additional tags for the public subnets | map | `<map>` | no |
| public\_subnets | A list of public subnets inside the VPC | list | `<list>` | no |
| redshift\_route\_table\_tags | Additional tags for the redshift route tables | map | `<map>` | no |
| redshift\_subnet\_group\_tags | Additional tags for the redshift subnet group | map | `<map>` | no |
| redshift\_subnet\_suffix | Suffix to append to redshift subnets name | string | `redshift` | no |
| redshift\_subnet\_tags | Additional tags for the redshift subnets | map | `<map>` | no |
| redshift\_subnets | A list of redshift subnets | list | `<list>` | no |
| reuse\_nat\_ips | Should be true if you don't want EIPs to be created for your NAT Gateways and will instead pass them in via the 'external_nat_ip_ids' variable | string | `false` | no |
| secondary\_cidr\_blocks | List of secondary CIDR blocks to associate with the VPC to extend the IP Address pool | list | `<list>` | no |
| single\_nat\_gateway | Should be true if you want to provision a single shared NAT Gateway across all of your private networks | string | `false` | no |
| tags | A map of tags to add to all resources | map | `<map>` | no |
| vpc\_tags | Additional tags for the VPC | map | `<map>` | no |
| vpn\_gateway\_id | ID of VPN Gateway to attach to the VPC | string | `` | no |
| vpn\_gateway\_tags | Additional tags for the VPN gateway | map | `<map>` | no |

## Outputs

| Name | Description |
|------|-------------|
| database\_route\_table\_ids | List of IDs of database route tables |
| database\_subnet\_group | ID of database subnet group |
| database\_subnets | List of IDs of database subnets |
| database\_subnets\_cidr\_blocks | List of cidr_blocks of database subnets |
| default\_network\_acl\_id | The ID of the default network ACL |
| default\_route\_table\_id | The ID of the default route table |
| default\_security\_group\_id | The ID of the security group created by default on VPC creation |
| elasticache\_route\_table\_ids | List of IDs of elasticache route tables |
| elasticache\_subnet\_group | ID of elasticache subnet group |
| elasticache\_subnet\_group\_name | Name of elasticache subnet group |
| elasticache\_subnets | List of IDs of elasticache subnets |
| elasticache\_subnets\_cidr\_blocks | List of cidr_blocks of elasticache subnets |
| igw\_id | The ID of the Internet Gateway |
| intra\_route\_table\_ids | List of IDs of intra route tables |
| intra\_subnets | List of IDs of intra subnets |
| intra\_subnets\_cidr\_blocks | List of cidr_blocks of intra subnets |
| nat\_ids | List of allocation ID of Elastic IPs created for AWS NAT Gateway |
| nat\_public\_ips | List of public Elastic IPs created for AWS NAT Gateway |
| natgw\_ids | List of NAT Gateway IDs |
| private\_route\_table\_ids | List of IDs of private route tables |
| private\_subnets | List of IDs of private subnets |
| private\_subnets\_cidr\_blocks | List of cidr_blocks of private subnets |
| public\_route\_table\_ids | List of IDs of public route tables |
| public\_subnets | List of IDs of public subnets |
| public\_subnets\_cidr\_blocks | List of cidr_blocks of public subnets |
| redshift\_route\_table\_ids | List of IDs of redshift route tables |
| redshift\_subnet\_group | ID of redshift subnet group |
| redshift\_subnets | List of IDs of redshift subnets |
| redshift\_subnets\_cidr\_blocks | List of cidr_blocks of redshift subnets |
| vgw\_id | The ID of the VPN Gateway |
| vpc\_cidr\_block | The CIDR block of the VPC |
| vpc\_enable\_dns\_hostnames | Whether or not the VPC has DNS hostname support |
| vpc\_enable\_dns\_support | Whether or not the VPC has DNS support |
| vpc\_endpoint\_dynamodb\_id | The ID of VPC endpoint for DynamoDB |
| vpc\_endpoint\_dynamodb\_pl\_id | The prefix list for the DynamoDB VPC endpoint. |
| vpc\_endpoint\_s3\_id | The ID of VPC endpoint for S3 |
| vpc\_endpoint\_s3\_pl\_id | The prefix list for the S3 VPC endpoint. |
| vpc\_id | The ID of the VPC |
| vpc\_instance\_tenancy | Tenancy of instances spin up within VPC |
| vpc\_main\_route\_table\_id | The ID of the main route table associated with this VPC |
| vpc\_secondary\_cidr\_blocks | List of secondary CIDR blocks of the VPC |

