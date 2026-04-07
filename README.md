# gcp-vpc-terraform-infra
Designed and provisioned a scalable VPC architecture in Google Cloud using Terraform, including multi-region VM deployment, firewall configuration, and automated infrastructure setup.
# Diagram
# Components 
Network
Subnets
Firewalls
Routes

# Flow
A VPC is created with combination of Subnets, Routes, Firewalls and Also created two VM's in two different zones and tested them in all scenarios.

# Authentication
For authentication of cloud provider with the request from Source/User a method is used which consits of Service Account, Workload Identification Fedaration, and OIDC id. This method is used by GCP for not to have any data compromise. So in that way as the OIDC Based Authentication protects the data and will not have any data compromisation it is used in GCP.

# Step by Step Process
For OIDC Authentication the components like - Service Account, Workload Identificatoin Fedaration, Provider settings, Issuer are required at GCP Console side and at User/Source side some data like GCP Provider Id, GCP Workload Identification ID, and Service Account Email are stored. Now while sending the request all these details are send with a unique OIDC ID.

# In Terraform Scripting part the below are the mandatory and important keys with values to configure resources

# Virtual Network
name
auto_create_subnetworks

# firewall
name
network
allow = {} / deny = {}
source_ranges / source_tags / target_Service_accounts

# subnet
network
name
region
ip_cidr_range

# Routes
network
name
dest_range
next_hop_ip / next_hop_instance / next_hop_gateway / next_hop_vpn_tunnel

