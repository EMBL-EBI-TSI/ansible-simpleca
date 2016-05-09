SimpleCA
========
Transfer SimpleCA certificates between GridFTP servers and clients.

SimpleCA certificates are generated when installing the globus-gsi
package. This role will create rpm packages from with the contents of the certificates to be installed on GridFTP clients.

Because of the way the transfer of the rpm package works the transfer  needs to occur in order using two different plays (see example below). The first play will generate the rpm package on the server and copy it to the local ansible machine. The second play then pushes the rpm package to the clients where it gets installed.

Requirements
------------
See `meta/main.yml`.

Role Variables
--------------
See `defaults/main.yml`.

Dependencies
------------
None.

Example Playbook
----------------
Example:
```
- hosts: gridftp-servers
  roles:
    - {role: simpleca, simpleca_mode: server}

- hosts: gridftp-clients
  roles:
    - {role: simpleca, simpleca_mode: client}
```

TODO
----
- Support transfer between servers.

Licence
-------
Licensed under [CC-BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/).

Author Information
------------------
Luis Gracia <luis.gracia@ebi.ac.uk>
