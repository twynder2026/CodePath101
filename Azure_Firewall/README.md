# Azure Firewall ARM Template

This ARM template deploys an Azure Firewall with custom DNAT, network, and application rules.

# Purpose
This project shows what I’ve learned about Azure network security and how to automate infrastructure. Sharing this helps me demonstrate my skills and what I’m capable of doing in real-world cloud security.

## How to deploy

Use the Azure CLI command:

bash:
az deployment group create \
  --name DeployFirewall \
  --resource-group Test-FW-RG \
  --template-file azurefirewall.json

## Overview
This project demonstrates how to manage Azure Firewall as infrastructure-as-code. The template allows you to redeploy the same firewall setup consistently across environments using version-controlled infrastructure.

## Architecture
Firewall Name: Test-FW01

Region: East US

SKU: AZFW_VNet (Standard Tier)

Availability Zones: 1, 2, 3

Threat Intelligence: Alert Mode

Private IP Address: 10.0.1.4

Public IP: Associated (fw-pip)

Virtual Network: Test-FW-VN

Subnet: AzureFirewallSubnet

Firewall Policy: fw-test-policy
