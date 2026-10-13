# Wazuh Security Monitoring

## Objective

Document the operational checks used to validate the Wazuh deployment and its security monitoring pipeline.

## Main Components

- **Wazuh Manager:** Processes agent data and security events.
- **Wazuh Indexer:** Stores and indexes security data.
- **Wazuh Dashboard:** Provides the interface for querying and visualizing security information.
- **Wazuh Agent:** Collects and forwards endpoint data to the manager.

## Operational Validation

The following checks should be performed during routine troubleshooting:

1. Confirm that the Wazuh containers are running.
2. Verify that the Wazuh Dashboard is accessible.
3. Check the agent inventory and connection status in the Dashboard.
4. Confirm that recent events are being indexed.
5. Investigate service logs when agents or events are missing.

## Example Commands

Check container status:

```bash
sudo docker compose ps
```

Review recent logs for a service:

```bash
sudo docker compose logs --tail=100 wazuh.manager
```

Check the Docker service:

```bash
sudo systemctl status docker --no-pager
```

Run these commands from the directory containing the Wazuh Docker Compose configuration.

## Troubleshooting Questions

- Are all required containers running?
- Can the Dashboard reach the Indexer?
- Is the agent configured with the correct manager address?
- Are the required network ports reachable?
- Are recent events arriving and being indexed?

## Security Considerations

Do not publish raw production logs, credentials, API tokens, private keys, or sensitive endpoint information in this repository.

## Validation Status

The checks above are documented as operational procedures. Their successful execution should be recorded only after they have been performed and verified.
