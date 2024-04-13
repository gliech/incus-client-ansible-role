## [1.0.1](https://github.com/gliech/incus-client-ansible-role/compare/v1.0.0...v1.0.1) (2024-04-13)


### Reverts

* **ci:** new jq requirement for incus server role ([6330a56](https://github.com/gliech/incus-client-ansible-role/commit/6330a569b94aec4634b23b5bd639b8c1014ae8b1))


### Continuous Integration

* **deps:** new jq requirement for incus server role ([b046ec4](https://github.com/gliech/incus-client-ansible-role/commit/b046ec4a396669cddc525eb74840653b171a38f6))

# 1.0.0 (2024-04-02)


### Features

* full client configuration ([42a888d](https://github.com/gliech/incus-client-ansible-role/commit/42a888d4e768c7172ace72d7fc88c1dad46fb0e0))
* initial commit ([61f7a94](https://github.com/gliech/incus-client-ansible-role/commit/61f7a942829a67b21e20f9391ee66124b765bcb3))
* rewrite role to use incus ([2190877](https://github.com/gliech/incus-client-ansible-role/commit/2190877aaaf9f7b296649011639992eb19a12037))


### Bug Fixes

* **defaults:** remove unused variable ([d386aa7](https://github.com/gliech/incus-client-ansible-role/commit/d386aa7ca7f8cf7ab8b63fa33475cd416620c678))
* replace most variable names that start with lxd_client_server_* with lxd_client_remote_* to avoid confusion ([9c7002d](https://github.com/gliech/incus-client-ansible-role/commit/9c7002d3a19ed8d945b86f617a27ea26b5bcbd7e))


### Documentation

* **meta:** archlinux support ([c6628c6](https://github.com/gliech/incus-client-ansible-role/commit/c6628c6c94ac6ac49733160177e214a37a3c9399))
* **readme:** more complete example playbook ([3b71591](https://github.com/gliech/incus-client-ansible-role/commit/3b71591a23ea455a2340ff1e73a7c48ef8c674db))
* **readme:** specify role requirements ([ff9ef0a](https://github.com/gliech/incus-client-ansible-role/commit/ff9ef0a33a3203af4facc28502547e957dcc5ffb))
* role readme ([6efd70f](https://github.com/gliech/incus-client-ansible-role/commit/6efd70f1c1d057242c34324f3cea6a0e156f9a3c))


### Styles

* ansible module fqdn ([220895d](https://github.com/gliech/incus-client-ansible-role/commit/220895df34d9c111ec6cae851ed1499b825a1778))


### Miscellaneous Chores

* change license to GPL3 ([c8edd1e](https://github.com/gliech/incus-client-ansible-role/commit/c8edd1e37b18f1eb3e16433e8e3c9e07f4e19f5c))


### Tests

* **molecule:** general updated to default scenario ([991cb06](https://github.com/gliech/incus-client-ansible-role/commit/991cb06a0fd7a5239d731d66a3e3f84eda5d5467))
* **molecule:** simplify verify test for github ([d53da59](https://github.com/gliech/incus-client-ansible-role/commit/d53da592ee256083340c6e709c1617f3e76d2810))


### Continuous Integration

* switch to remote gh actions workflow ([9e2bad5](https://github.com/gliech/incus-client-ansible-role/commit/9e2bad56fa6ea0490a6c136909f1efdf13797b94))


### BREAKING CHANGES

* rewrite role to use incus
* replace most variable names that start with lxd_client_server_* with lxd_client_remote_* to avoid confusion
* change license to GPL3
