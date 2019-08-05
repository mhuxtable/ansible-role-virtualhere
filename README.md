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
virtualhere__server_binary_path: "{{ virtualhere__server_binary_path }}/vhusbd{{ ansible_architecture }}"
```

The paths at which the daemon will be installed.

```
virtualhere__server_enabled: yes
```

Whether the server daemon is enabled for installation. If disabled, the daemon and any configuration files written by this role will be uninstalled.

```
virtualhere__server_config_file_path: /etc/virtualhere/config.ini
```

The path to the VirtualHere configuration file (see next section to configure its directives).

## Configuration file

```
virtualhere__server_name: "{{ ansible_hostname }}"

# virtualhere__device_nicknames is a list of nicknames in the following format:
# - nickname: "Friendly Name"
#   vendor: "<vendor hex value>"
#   product: "<product hex value>"
#   address: "<address decimal>"
virtualhere__device_nicknames: {}
virtualhere__use_avahi: yes

virtualhere__allowed_devices: []
virtualhere__ignored_devices: []
```

Options for the VirtualHere configuration file, which will be generated and copied to the host when server mode is enabled.

License
-------

MIT
