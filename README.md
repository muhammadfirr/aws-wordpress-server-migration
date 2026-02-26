# AWS WordPress Production Migration

## Project Overview
This repository documents a full WordPress production migration performed on an Ubuntu 24 EC2 instance hosted in AWS.
The project demonstrates skills in file transfer, MySQL database restoration, Nginx configuration, SSL setup, and AWS networking validation.

---

## Environment

- **Cloud Provider:** AWS
- **Operating System:** Ubuntu 24
- **Web Server:** Nginx
- **Database:** MySQL (local to EC2)
- **SSL:** Existing certificate provided in backup
- **VPC:** 10.100.0.0/16 with NAT Gateway
- **Security:** SSH (22), HTTP (80), HTTPS (443)

---

## Architecture
See [`docs/architecture.md`](docs/architecture.md) for detailed diagram and explanation of the infrastructure setup.

---

## Migration Steps
See [`docs/migration-guide.md`](docs/migration-guide.md) for full step-by-step migration process including file transfer, database restoration, Nginx configuration, and SSL setup.

---

## Troubleshooting
See [`docs/troubleshooting.md`](docs/troubleshooting.md) for common issues encountered during migration and solutions applied.

---

## Key Skills Demonstrated

- Linux server administration
- WordPress production migration
- MySQL database restoration via CLI
- Nginx multi-domain virtual host configuration
- Manual SSL certificate installation
- AWS Security Group and network validation
- Post-migration testing & validation

---

## Security Considerations

- Real SSL private keys and certificates excluded
- Real domains replaced with placeholders
- Database backups excluded for security compliance
- Sensitive configuration files sanitized
