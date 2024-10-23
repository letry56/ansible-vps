# VPS with 3x-ui VPN panel and WireGuard for managing services on the server

## Configuration

Change in `inventory.yml`:
- `ansible_host`
- `ansible_user`
- `ansible_password`

Fill in the required values in `wireguard/wg0.conf`:

- `<server_private_key>`
- `<client_public_key>`
- `<preshared_key>`
- Change the name of the default interface (e.g., `enp0s3` or `eth0`) if necessary

Add new sudo user if necessary:

- `sudo adduser letry`
- `sudo usermod -aG sudo letry`
- `groups letry`

## Execution

To install required roles and run the playbook, execute the following commands:

```bash
ansible-galaxy install -r requirements.yml
ansible-playbook -i inventory.yml playbooks/vps.yml
