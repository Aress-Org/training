# Task: Set Up Apache and Load an Index Page

Set up Apache on a Linux server, create a simple web page, and verify that it loads in a browser or with `curl`. A basic Apache setup should install the web server, start the service, place an `index.html` file in the document root, and confirm that the page is reachable locally.

## Objectives

- Install Apache on a Linux server.
- Start and enable the Apache service.
- Create a simple `index.html` page.
- Place the file in the web server document root.
- Verify that the page loads successfully from the server.

## Requirements

- Use a Linux VM or server.
- Apache must be running after setup.
- The default page should be accessible at `http://localhost` or the server IP.
- The page should contain a short custom message such as "Welcome to my page".

## Suggested Steps

1. Install Apache.
2. Start the Apache service.
3. Enable it to start on boot.
4. Create or edit `index.html` in the Apache document root.
5. Open port 80 if a firewall is enabled.
6. Test the page in a browser or with `curl`.

## Verification

- `systemctl status apache2` (Debian/Ubuntu) or `systemctl status httpd` (RHEL/CentOS) shows the service is **active (running)**.
- `curl http://localhost` returns the HTML content.
- Visiting the server IP in a browser shows the custom index page.

## Example Deliverable

- A working Apache installation.
- A screenshot of the browser showing the index page.
- The `index.html` file content used for testing.

## Reference Commands

### Debian / Ubuntu

```bash
sudo apt update
sudo apt install -y apache2
sudo systemctl start apache2
sudo systemctl enable apache2
echo '<h1>Welcome to my page</h1>' | sudo tee /var/www/html/index.html
curl http://localhost
```

### RHEL / CentOS / Rocky / AlmaLinux

```bash
sudo dnf install -y httpd
sudo systemctl start httpd
sudo systemctl enable httpd
echo '<h1>Welcome to my page</h1>' | sudo tee /var/www/html/index.html
curl http://localhost
```

## Sample index.html

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>My Apache Page</title>
</head>
<body>
  <h1>Welcome to my page</h1>
  <p>Apache is running successfully.</p>
</body>
</html>
```

## Notes

- Default document root on most distros: `/var/www/html/`
- If a firewall is enabled, allow HTTP traffic on port 80 (`ufw allow 80/tcp` on Ubuntu with UFW, or `firewall-cmd --add-service=http --permanent` on firewalld).
- Package and service names differ by distro: `apache2` vs `httpd`.
