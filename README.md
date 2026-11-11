# AWS VPC with public and private subnets

This Terraform configuration creates a VPC (`10.0.0.0/16`) with:

- **SN1** (`10.0.0.0/24`), a public subnet routed to an internet gateway.
- **SN2** (`10.0.1.0/24`), a private subnet whose default route uses a NAT gateway in SN1.

Both subnets are placed in the first available Availability Zone in the selected region. The AWS region defaults to `us-east-1`; override it with `-var="aws_region=REGION"`.

Run `terraform init`, `terraform plan`, and `terraform apply` from this directory. Run `terraform destroy` when you no longer need the resources. A NAT gateway and its Elastic IP can incur AWS charges while allocated.