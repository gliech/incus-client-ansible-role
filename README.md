# [Incus Client Ansible Role][1]

[![test & release][2]][3]

This Ansible role installs Incus and configures one or more other hosts from the
Ansible inventory as remotes.

## Requirements

This role requires the Incus remotes to be defined in the same inventory as the
clients that are being configured. That is because it uses the ansible
connections with the servers as trusted channel to transfer the users client
certificates to the remotes.

This also means that, if the Incus servers are provisioned in the same playbook
as the clients, the installation of the servers is a prerequisite step for this
role to run.

## Role Variables

<table>
<tr><th>Name</th><th>Required</th><th>Type / Choices</th><th>Description</th></tr>
<tr><td><code>incus_client_remotes</code></td>
<td>yes</td>
<td>list(string)</td>
<td>

List of Ansible inventory hostnames of machines that should be configured as
Incus remotes. The ansible user on these machines should be a member of the
incus group so that it can configure client certificates on the server.

**Example:** `"{{ groups.incus_servers }}"`
</td></tr>


<tr><td><code>incus_client_default_remote</code></td>
<td>no</td>
<td>string</td>
<td>

Name of an Incus remote that will be configured as default-remote in the incus
client config. Defaults to the first entry in the `incus_client_remotes`
variable.

**Default:** `incus_client_remotes[0]`
</td></tr>


<tr><td><code>incus_client_users</code></td>
<td>no</td>
<td>list(string)</td>
<td>

List of OS users, on the client machines which should be configured to access
the Incus remotes. If no list is supplied, only the Ansible user will be set up
to reach the remotes.

**Default:** `["{{ ansible_user_id }}"]`
</td></tr>
</table>

## Dependencies

None.

## Example Playbook

```yaml
- hosts: incus_servers
  tasks:
    - name: Configure Incus servers
      ansible.builtin.import_role:
        name: gliech.incus
      vars:
        incus_config:
          config: {}
          networks: []
          storage_pools:
            - config:
                source: /var/lib/incus/storage-pools/default
              description: ""
              name: default
              driver: dir
          profiles:
            - config:
                security.privileged: "true"
              description: Default Incus profile
              devices:
                root:
                  path: /
                  pool: default
                  type: disk
              name: default
          projects:
            - config:
                features.images: "true"
                features.networks: "true"
                features.networks.zones: "true"
                features.profiles: "true"
                features.storage.buckets: "true"
                features.storage.volumes: "true"
              description: Default Incus project
              name: default

- hosts: localhost
  tasks:
    - name: Configure Incus client
      ansible.builtin.import_role:
        name: gliech.incus_client
      vars:
        incus_client_remotes: "{{ groups.incus_servers }}"
```

## License

This project is licensed under the terms of the [GNU General Public License v3.0](LICENSE)

[1]: https://galaxy.ansible.com/ui/standalone/roles/gliech/incus_client/
[2]: https://github.com/gliech/incus-client-ansible-role/actions/workflows/release.yml/badge.svg
[3]: https://github.com/gliech/incus-client-ansible-role/actions/workflows/release.yml
[4]: https://github.com/gliech/semantic-release-config-github-ansible-role
