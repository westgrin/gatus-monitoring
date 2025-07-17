# Mini Project - Configuring Uptime Monitoring using Gatus

## Project Overview
This project sets up Gatus to monitor the uptime of websites and APIs, with Slack alerts and a customized dashboard. It builds on previous projects (e.g., Prometheus Node Exporter, Jul 14-15, 2025).

## Setup
- Initiated on Jul 17, 2025, 11:26 AM CAT.
- Used WSL Ubuntu, VS Code, and Git Bash in `/mnt/c/Users/User/Documents/Workspace/gatus-monitoring`.
- System: 2 CPUs, 2GB free memory, 20GB free disk space.
- Tools: Docker for running Gatus.

## Execution Steps
1. **Confirm Prerequisites**:
   - Verified Docker installation and port 8080 availability.
   - Set up Slack webhook for alerts.
   - [Screenshot: `docker_version_output_local.png` - Shows Docker version and service status.]
   - [Screenshot: `network_check_output_local.png` - Shows port availability.]
2. **Install Gatus**:
   - Pulled `twinproduction/gatus:v5.10.0` and started container.
   - Accessed dashboard at `http://localhost:8080`.
   - [Screenshot: `gatus_container_output_local.png` - Shows running container.]
   - [Screenshot: `gatus_dashboard_initial_output_local.png` - Shows initial dashboard.]
3. **Configure Endpoints**:
   - Created `config.yaml` to monitor `https://example.com`.
   - [Screenshot: `gatus_dashboard_example_output_local.png` - Shows dashboard with endpoint.]
4. **Test Live Endpoints**:
   - Added `https://github.com` and a non-existent endpoint.
   - Verified status on dashboard.
   - [Screenshot: `gatus_dashboard_endpoints_output_local.png` - Shows all endpoints.]
5. **Configure Alerts**:
   - Added Slack alerts to `config.yaml`.
   - Tested failure alerts for non-existent endpoint.
   - [Screenshot: `gatus_slack_alert_output_local.png` - Shows Slack notification.]
6. **Explore and Customize Dashboard**:
   - Viewed uptime statistics and customized header/logo.
   - Adjusted monitoring intervals and conditions.
   - [Screenshot: `gatus_dashboard_stats_output_local.png` - Shows GitHub statistics.]
   - [Screenshot: `gatus_dashboard_custom_output_local.png` - Shows customized dashboard.]
7. **Side Hustle Task**:
   - Automated setup with GitHub Actions.
   - Pushed to `https://github.com/westgrin/gatus-monitoring`.
   - [Screenshot: `github_actions_deploy_output_local.png` - Shows workflow run.]
8. **Clean Up (Optional)**:
    - Stopped and removed Gatus container and image.
    - [Screenshot: `gatus_cleanup_output_local.png` - Shows cleanup.]

## Learning Summary
This project introduced Gatus for uptime monitoring, complementing Prometheus-based monitoring (Jul 14-15, 2025). Learned endpoint configuration, alerting, and dashboard customization.

## Tools Used
- **WSL Ubuntu Terminal**: For Docker commands.
- **VS Code**: For editing `config.yaml` and `README.md`.
- **Git Bash**: For GitHub operations.
- **GitHub Actions**: For automation.
- **Docker**: For running Gatus.
- **Slack**: For alerts.

## Project Deliverables
- **Documentation**: This `README.md` with steps and learning summary.
- **Screenshots**:
  - `docker_version_output_local.png`
  - `network_check_output_local.png`
  - `gatus_container_output_local.png`
  - `gatus_dashboard_initial_output_local.png`
  - `gatus_dashboard_example_output_local.png`
  - `gatus_dashboard_endpoints_output_local.png`
  - `gatus_slack_alert_output_local.png`
  - `gatus_dashboard_stats_output_local.png`
  - `gatus_dashboard_custom_output_local.png`
  - `github_actions_deploy_output_local.png`
  - `gatus_cleanup_output_local.png` (if applicable)
- **Script Link**: [GitHub Repository](https://github.com/westgrin/gatus-monitoring)

## Local Development Instructions
1. Clone repository: `git clone https://github.com/westgrin/gatus-monitoring.git`
2. Install Docker: `sudo apt install docker.io -y`
3. Create config directory: `mkdir gatus-monitoring/config`
4. Copy `config.yaml` to `config/`
5. Run Gatus: `docker run -d -p 8080:8080 --name gatus -v $(pwd)/config:/config twinproduction/gatus:v5.10.0`
6. Verify: Access `http://localhost:8080`

## Troubleshooting
- Ensured Docker is running with `systemctl status docker`.
- Used specific Gatus version (`v5.10.0`) to avoid `latest` tag issues.
- Set DNS to `8.8.8.8` for network issues (from Docker project, Jul 4, 2025).
- Verified port 8080 availability with `netstat`.

## Conclusion
This project successfully set up Gatus for uptime monitoring, enhancing my DevOps monitoring skills with a lightweight tool.