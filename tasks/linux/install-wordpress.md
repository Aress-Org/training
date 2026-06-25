# Task: Install WordPress on a Linux Server

Install WordPress on a Linux server with Apache, MariaDB, and PHP. Download the WordPress files, create a database, complete the web-based setup, and verify that the site loads in a browser.

## Objectives

- Install Apache, MariaDB (or MySQL), and PHP on a Linux server.
- Create a database and database user for WordPress.
- Download WordPress and place it in the web server document root.
- Configure WordPress and complete the installation wizard.
- Verify that the WordPress site loads successfully.

## Requirements

- Use a Linux VM or server (Ubuntu/Debian recommended for this task).
- Apache, MariaDB, and PHP must be running after setup.
- WordPress must be reachable at `http://localhost` or the server IP.
- Complete the installation with a custom site title such as "My Training Site".
- Log in to the WordPress admin dashboard after setup.

## Suggested Steps

1. Install Apache, MariaDB, and PHP with required extensions.
2. Start and enable the web server and database services.
3. Create a WordPress database and a dedicated database user.
4. Download WordPress and extract it into the Apache document root.
5. Set correct ownership and permissions on the WordPress files.
6. Open `http://localhost` (or the server IP) in a browser.
7. Complete the WordPress installation wizard (site title, admin username, password, email).
8. Log in to `/wp-admin` and confirm the dashboard loads.

## Verification

- `systemctl status apache2` and `systemctl status mariadb` show both services are **active (running)**.
- `curl -I http://localhost` returns HTTP `200` or `301`/`302`.
- The WordPress front page loads in a browser with your chosen site title.
- You can log in at `http://localhost/wp-admin` with the admin account you created.

## Example Deliverable

- A working WordPress installation.
- A screenshot of the WordPress front page after installation.
- A screenshot of the WordPress admin dashboard.
- The site title and admin username used during setup (do not share passwords).

## Reference Commands

### Debian / Ubuntu

```bash
# Install LAMP stack
sudo apt update
sudo apt install -y apache2 mariadb-server php libapache2-mod-php \
  php-mysql php-xml php-curl php-gd php-mbstring php-zip unzip wget

# Start and enable services
sudo systemctl start apache2 mariadb
sudo systemctl enable apache2 mariadb

# Secure MariaDB (optional but recommended)
sudo mysql_secure_installation

# Create database and user
sudo mysql -u root -p <<'SQL'
CREATE DATABASE wordpress DEFAULT CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci;
CREATE USER 'wpuser'@'localhost' IDENTIFIED BY 'ChangeMe_StrongPassword123';
GRANT ALL PRIVILEGES ON wordpress.* TO 'wpuser'@'localhost';
FLUSH PRIVILEGES;
SQL

# Download and install WordPress
cd /tmp
wget https://wordpress.org/latest.tar.gz
tar -xzf latest.tar.gz
sudo rm -rf /var/www/html/*
sudo mv wordpress/* /var/www/html/
sudo chown -R www-data:www-data /var/www/html
sudo find /var/www/html -type d -exec chmod 755 {} \;
sudo find /var/www/html -type f -exec chmod 644 {} \;

# Test Apache
curl -I http://localhost
```

Then open `http://localhost` in a browser and complete the setup wizard using:

- **Database name:** `wordpress`
- **Username:** `wpuser`
- **Password:** the password you set above
- **Database host:** `localhost`
- **Table prefix:** `wp_` (default)

### RHEL / CentOS / Rocky / AlmaLinux

```bash
sudo dnf install -y httpd mariadb-server php php-mysqlnd php-xml php-curl \
  php-gd php-mbstring php-zip unzip wget
sudo systemctl start httpd mariadb
sudo systemctl enable httpd mariadb
```

Follow the same database and WordPress download steps above. On RHEL-based systems, use `apache` as the web user instead of `www-data`:

```bash
sudo chown -R apache:apache /var/www/html
```

## Sample wp-config.php values

After the web installer runs, WordPress creates `wp-config.php` automatically. If configuring manually, these are the key settings:

```php
define( 'DB_NAME', 'wordpress' );
define( 'DB_USER', 'wpuser' );
define( 'DB_PASSWORD', 'ChangeMe_StrongPassword123' );
define( 'DB_HOST', 'localhost' );
define( 'DB_CHARSET', 'utf8mb4' );
define( 'DB_COLLATE', '' );
```

## Notes

- This task builds on [Set Up Apache and Load an Index Page](./set-up-apache-and-load-index-page.md). Complete that task first if Apache is not already installed.
- Default document root: `/var/www/html/`
- If a firewall is enabled, allow HTTP on port 80 (`sudo ufw allow 80/tcp`).
- Use a strong admin password during the WordPress setup wizard.
- For production systems, also configure HTTPS and harden MariaDB; this task focuses on a basic local/training install only.
