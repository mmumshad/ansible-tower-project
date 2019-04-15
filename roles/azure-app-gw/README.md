# Ansible Role: azure-app-gw

## Provision Application Gateway

**Pre-Requisites:**

The Application Gateway requires an empty subnet in the same Virtual Network as the target systems. The default subnet took up all the address space in the virtual network. So I had to create a new address space for the App Gateway and create new subnet using that.

The Application Gateway also requires certificates for SSL Termination. I created a self-signed certificate following the below steps:

```
openssl req -x509 -sha256 -nodes -days 365 -newkey rsa:2048 -keyout privatekey.key -out certificate.crt

openssl pkcs12 -export -out certificate.pfx -inkey privatekey.key -in certificate.crt

cat certificate.pfx | base64
```

Inputs:

1. **Backend Addresses:** The internal private addresses of the Ansible Tower instances.
2. **Subnet ID:** The subnet ID of the subnet created for Application Gateway. eg: `/subscriptions/e2fXXXX-XXXX-XXXX-XXXX-XXXXX092f4/resourceGroups/rg-ansible/providers/Microsoft.Network/virtualNetworks/vn-bastion-ansible/subnets/app-gw-subnet`.
3. **Certificate Data:** Base-64 encoded pfx certificate

> Note: Sometimes it may take up to 20 minutes for the Application Gateway to be provisioned.

```
app_gateway_name: test-app-gw-18
public_ip_address: app_gw_public_ip_18
subnet_id: /subscriptions/e2fXXXX-XXXX-XXXX-XXXX-XXXXX092f4/resourceGroups/rg-ansible/providers/Microsoft.Network/virtualNetworks/vn-bastion-ansible/subnets/app-gw-subnet
backend_addresses:
  - ip_address: 10.191.0.5
  - ip_address: 10.191.0.6
  - ip_address: 10.191.0.7
```
