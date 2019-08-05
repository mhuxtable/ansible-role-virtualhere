ansible-role-virtualhere
=========

Installs the [VirtualHere USB sharing daemon](https://virtualhere.com/home) to a Linux-based host.

Role Variables
--------------

Available variables are listed below, along with default values (see `defaults/main.yml`):

```
virtualhere__download_base_url: https://virtualhere.com/sites/default/files/usbserver/vhusbd
```

The base URL for downloading the VirtualHere daemon. The system architecture will be appended.

```
virtualhere__supported_archs: ['i386', 'x86_64', 'arm', 'arm64', 'mips', 'mipsel']
```

System architectures supported by the VirtualHere USB daemon, and, by extension, this role.

```
virtualhere__server_binary_dirpath: "/usr/local/bin"
virtualhere__server_binary_path: "{{ virtualhere__server_binary_path }}/vhusbd{{ ansible_architecture }}
```

The paths at which the daemon will be installed.

```
virtualhere__server_enabled: yes
```

Whether the server daemon is enabled for installation. If disabled, the daemon and any configuration files written by this role will be uninstalled.

License
-------

MIT
