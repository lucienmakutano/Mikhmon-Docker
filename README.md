# Mikhmon-Docker

![Mikhmon Logo](https://raw.githubusercontent.com/laksa19/laksa19.github.io/master/img/mikhmonv3.png)

Mikhmon-Docker is a Docker implementation for Mikhmon (MikroTik Hotspot Monitor), a PHP-based application for monitoring and managing MikroTik hotspots.

## About the Project

Mikhmon-Docker packages the [Mikhmon](https://laksa19.github.io/?mikhmon/v3) application in a Docker container, making it easy to install and use Mikhmon without manually configuring a web server environment. This project allows you to:

- Run Mikhmon in an isolated environment
- Simplify deployment across various platforms
- Maintain configuration data with Docker volumes
- Access Mikhmon from a web browser on the configured port

## Features

- **Hotspot Management**: Monitor and manage MikroTik hotspot users
- **Voucher Management**: Create and print hotspot vouchers
- **Informative Dashboard**: View statistics and user information
- **User Management**: Add, edit, and delete user accounts
- **Reports**: Access usage and revenue reports
- **Multi-Router**: Manage multiple MikroTik routers in one application
- **Persistent Configuration**: Data stored in Docker volumes

## Requirements

- Docker and Docker Compose installed
- Network connection to MikroTik router
- MikroTik router with API enabled

## Usage

### Quick Start Method

1. Clone this repository:
   ```bash
   git clone https://github.com/rizkikotet-dev/mikhmon-docker.git
   cd mikhmon-docker
   ```

2. Run with Docker Compose:
   ```bash
   docker-compose up -d
   ```

3. Access Mikhmon via browser:
   ```
   http://localhost:80
   ```

### Docker Compose Configuration ( **Recommended** )

Available `docker-compose.yml` file:
```yaml
services:
  mikhmon:
    container_name: Mikhmon
    pull_policy: always
    image: rizkikotet/mikhmon:latest
    restart: unless-stopped
    ports:
      - "80:80"
      #- "443:443"
    environment:
      - PUID=1000
      - PGID=1000
      - TZ=Asia/Jakarta
```

### Initial Mikhmon Configuration

1. After accessing Mikhmon through your browser, you will see the login page.
2. Use the default credentials:
   - Username: `mikhmon`
   - Password: `1234`
3. Change the default password immediately after the first login.
4. Add a MikroTik router by clicking "Add Router":
   - Enter a name for the router
   - Enter the router's IP address
   - Enter the API username and password
   - Click "Save"

## Updates

To update to the latest version:

```bash
docker-compose down
git pull
docker-compose up -d --build
```

## Troubleshooting

- **Cannot connect to Mikhmon**: Make sure port 80 is not being used by another application
- **Cannot connect to router**: Verify that the MikroTik API is enabled and credentials are correct

## References and Sources

Mikhmon is developed by laksa19: [https://laksa19.github.io/?mikhmon/v3](https://laksa19.github.io/?mikhmon/v3)

This project is an unofficial Docker implementation to facilitate Mikhmon deployment.

## Contributing

Contributions are welcome! Please fork this repository and submit a pull request.

## License

This project is licensed under the [MIT License](LICENSE) with respect to the original Mikhmon project.

---

&copy; 2025 Mikhmon-Docker | Mikhmon &copy; [laksa19](https://github.com/laksa19)