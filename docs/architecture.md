# AWS WordPress Migration Architecture

## Overview
This document describes the infrastructure setup for the WordPress production migration performed on AWS EC2 (Ubuntu 24).

## Components

### EC2 Instance
  - OS: Ubuntu 24
  - Web Server: Nginx
  - Database: MySQL (local)
  - SSL: Provided certificate (.crt + .key)
  - Public IP: Example: 43.217.xxx.xxx
  - Security: Open ports 22 (SSH), 80 (HTTP), 443 (HTTPS)

### Network
  - Hosted inside AWS VPC
  - VPC CIDR: 10.100.0.0/16
  - NAT Gateway configured for internet access

## Architecture Diagram

```text
          Internet
             ↓
       Public IP (Elastic IP)
             ↓
        ┌───────────┐
        │   EC2     │
        │ Ubuntu 24 │
        │───────────│
        │ Nginx     │
        │ PHP       │
        │ WordPress │
        │ MySQL     │
        │ SSL Cert  │
        └───────────┘
