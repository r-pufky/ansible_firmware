# Firmware
Firmware update management.

## [Requirements][i]
Requires [r_pufky.deb][g] galaxy-ng collection.

## Role Variables
Detailed variable use documented in defaults. See usage for role operation.

* [defaults][j] - User configurable options.

## Usage

### Example Playbooks
Add additional firmware repositories if needed. This will install firmware
packages and apply firmware updates for hardware.

``` yaml
- name: 'Update intel-microcode, remove firmware-bnx2x firmware, reboot.'
  ansible.builtin.include_role:
    name: 'r_pufky.deb.firmware'
  vars:
    firmware_srv_packages:
      - 'intel-microcode'
    firmware_srv_packages_absent:
      - 'firmware-bnx2x'
    firmware_srv_timeout: 600
    firmware_srv_poll: 5
```

## Development
Configure [environment][a].

``` bash
# Run all tests.
molecule test --all
```

### [Releases][b]

  Release | Debian | Ansible | Notes
 ---------|--------|---------|-------
  2.x.x   | 13     | 2.20    | Ansible 2.20, semantic versioning.
  1.x.x   | 13     | 2.18    | Migrate to Debian Trixie.
  0.x.x   | 12     | 2.18    | Migration from private repository.

## Issues
Create a bug and provide as much information as possible.

Associate pull requests with a submitted bug.

## License
[AGPL-3.0 License][c] | [direct link][f]

## Author Information
PGP: [466EEC2B67516C7117C85CE3A0BC35D16698BAB9][d] | [github gist][e]

[a]: https://r-pufky.github.io/ansible_docs
[b]: https://semver.org/spec/v2.0.0
[c]: https://www.tldrlegal.com/license/gnu-affero-general-public-license-v3-agpl-3-0
[d]: https://keys.openpgp.org/vks/v1/by-fingerprint/466EEC2B67516C7117C85CE3A0BC35D16698BAB9
[e]: https://gist.github.com/r-pufky/a8df36977c55b5bb20829267c4c49d22

[f]: https://github.com/r-pufky/ansible_firmware/blob/main/LICENSE
[g]: https://github.com/r-pufky/ansible_collection_deb
[i]: https://github.com/r-pufky/ansible_firmware/blob/main/defaults/main.yml
[j]: https://github.com/r-pufky/ansible_firmware/tree/main/defaults/main/main.yml