# Kea

An Ansible role to install [Kea](https://kea.isc.org/) ([Gitlab](https://gitlab.isc.org/isc-projects/kea/))

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

```yaml
- hosts: dhcp_servers
  roles:
    - syaghoubi00.kea
```

## License

GPL-3.0-or-later

## Author Information

Created by Sebastian Yaghoubi
