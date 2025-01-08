# Kea

An Ansible role to install [Kea](https://kea.isc.org/) ([Gitlab](https://gitlab.isc.org/isc-projects/kea/))

> [!IMPORTANT]
> There is a separate `role` branch for using this as a standalone role. Which
> requires resolving the `syaghoubi00.epel` role dependency separately. This is a
> limitation of Ansible I haven't found a workaround for.
>
> The `main` branch is included in the Ansible collection `syaghoubi00.homelab`

## Usage

**Using as a part of my homelab collection**:

`ansible-galaxy collection install syaghoubi00.homelab`

**As a standalone role**:

I was unable to import the role to `ansible-galaxy` because the branch
handling was broken, so just use the `git` repo. Additionally, I don't think
`ansible-galaxy` allows the role to be named when doing
`ansible-galaxy role install`, so a `requirements.yaml` file is needed.

`requirements.yaml`

```yaml
roles:
  - name: syaghoubi00.kea
    src: https://github.com/syaghoubi00/ansible-role-kea
    version: role
```

`ansible-galaxy role install -r requirements.yaml`

## Platforms

- RHEL 9

## Requirements

None.

## Role Variables

`kea_install_method: package` - The method to install `kea`, currently only
`package` is implemented.

## Dependencies

`syaghoubi00.epel` - To add EPEL in EL distros to get the package.

## Example Playbook

Using the `syaghoubi00.homelab` collection:

```yaml
- hosts: dhcp_servers
  roles:
    - syaghoubi00.homelab.kea
```

Using the standalone role after installing it (instructions above):

```yaml
- hosts: dhcp_servers
  roles:
    - syaghoubi00.kea
```

## License

GPL-3.0-or-later

## Author Information

Created by Sebastian Yaghoubi
