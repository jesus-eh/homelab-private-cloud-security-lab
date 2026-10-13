# Troubleshooting: Wazuh IP Address Change

## Incident Summary

The Wazuh virtual machine changed its IPv4 address from `192.168.1.117` to `192.168.1.118`.

The Docker containers remained running, but the Docker Compose configuration still bound the published ports to the previous IP address.

## Symptoms

- The Wazuh containers appeared to be running.
- The virtual machine had a new IP address.
- Published ports still referenced the old address.
- Access to the Wazuh Dashboard using the new IP was initially unsuccessful.

## Investigation

The following checks were used to identify the cause:

1. Check the virtual machine's IPv4 configuration.
2. Check whether the Docker service is running.
3. Inspect the container status and published ports with `docker compose ps`.
4. Search the Docker Compose file for references to the previous IP address.
5. Validate the updated Compose configuration.

## Root Cause

The Docker Compose file used explicit host IP bindings.

These bindings were tied to `192.168.1.117`, which was no longer assigned to the virtual machine.

Running containers did not automatically update their published host IP bindings when the VM address changed.

## Resolution

The old IP address was replaced with the new address in the Docker Compose file.

The configuration was validated and the services were reconciled using Docker Compose.

Afterward, the published ports showed the new IP address and the Wazuh Dashboard became accessible again.

## Verification

The following checks confirmed the recovery:

- Docker service status reported `active (running)`.
- Wazuh Manager, Indexer, and Dashboard were running.
- Published ports referenced the new VM address.
- Dashboard access was restored.

## Lessons Learned

- Avoid relying on changing DHCP addresses for services with explicit IP bindings.
- Consider a DHCP reservation or a carefully planned static IP address.
- Validate Docker Compose configuration before applying changes.
- Verify both container health and host port bindings after network changes.
- Document recovery procedures to reduce future troubleshooting time.

## Security Considerations

This document uses example private IP addresses from a personal lab. Review network details before publishing them.

No credentials, tokens, private keys, or configuration secrets should be included in the repository.
