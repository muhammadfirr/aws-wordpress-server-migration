# Migration Troubleshooting Guide

## Common Issues

### 1. Nginx 500 Internal Server Error
- Cause: Wrong file ownership or permissions
- Fix: 
- sudo chown -R www-data:www-data /var/www/
- sudo chmod -R 755 /var/www/
- sudo systemctl restart nginx

### 2. Error establishing database connection
- Cause: Incorrect wp-config.php credentials or DB server down
- Fix:
- Verify DB_NAME, DB_USER, DB_PASSWORD
- Test MySQL connection: `mysql -u user -p db_name`
- Restart MySQL if needed: `sudo systemctl restart mysql`

### 3. SSL Not Working / Mixed Content
- Cause: Certificate not correctly referenced in Nginx
- Fix:
- Verify `ssl_certificate` and `ssl_certificate_key` paths
- Test Nginx config: `nginx -t`
- Restart Nginx: `systemctl restart nginx`

### 4. Website Not Accessible
- Cause: Security Group missing ports
- Fix:
- Ensure AWS Security Group allows 22, 80, 443
- Verify public IP / Elastic IP assigned
