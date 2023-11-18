# Common.NatGateway

Role for configuring NAT gateway via sumple iptables masquerading

Tested for AWS and YC

# Changelog 

## 2.1.0

- Make it work in AWS

## 2.0.0

- BREAKING CHANGE: Remove support for configure_ufw and ufw_allowed_ssh_ips
- BREAKING CHANGE: Accept array of cidrs

## 1.1.1

- Fix UFW configuration

## 1.1.0

- Add optional UFW configuration

# Documentation for 1.1.1

## Requirements

## Variables

### Non-secret

```yaml
nat_gateway:
  # Masquerading will be applied only to traffic that goes from this CIDR
  source_cidr: 172.18.0.0/16
  # Deprecated. Use security groups instead. False by default
  configure_ufw: false
  # Deprecated. Use security groups instead. Empty by default
  ufw_allowed_ssh_ips: 
  - "{{ lookup('dig', 'openvpn-pub.algobot.ru') }}"  
```  

### Secret

```yaml

```

# Documentation for 2.0.0

## Requirements

## Variables

### Non-secret

```yaml
nat_gateway:
  # Masquerading will be applied only to traffic that goes from this CIDRs
  source_cidrs: 
  - 172.18.0.0/16
  - 172.20.0.0/16
```  

### Secret

```yaml

```
