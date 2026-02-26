# WordPress Production Migration – AWS EC2 (Ubuntu 24)

## Environment
- Cloud Provider: AWS
- OS: Ubuntu 24
- Web Server: Nginx
- Database: MySQL
- SSL: Existing Production Certificate (Manual Configuration)

## 1. File Migration
- Transferred WordPress files via SCP
- Verified directory structure inside /var/www/
- Fixed file ownership:
  sudo chown -R www-data:www-data /var/www/

## 2. Database Restoration
- Created new MySQL database
- Restored backup using:
  mysql -u root -p db_name < backup.sql
- Verified tables using:
  SHOW TABLES;

## 3. WordPress Configuration
- Updated wp-config.php with new database credentials
- Verified DB_HOST and DB_NAME

## 4. Nginx Configuration
- Created server block inside:
  /etc/nginx/sites-available/
- Configured multiple domain virtual hosts
- Created symbolic link:
  ln -s /etc/nginx/sites-available/example.conf /etc/nginx/sites-enabled/
- Tested configuration:
  nginx -t
- Restarted service:
  systemctl restart nginx

## 5. SSL Manual Setup
- Installed provided SSL certificate (.crt)
- Installed private key (.key)
- Configured HTTPS listener (port 443)
- Implemented HTTP → HTTPS redirection
- Verified certificate validity in browser

## 6. AWS Network Validation
- Ensured Security Group allowed:
  - Port 22 (SSH)
  - Port 80 (HTTP)
  - Port 443 (HTTPS)
- Verified public IP accessibility

## 7. Post-Migration Testing
- Homepage load test
- WordPress admin login validation
- Database connection testing
- HTTPS secure connection validation
