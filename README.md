# ansible users play
Ansible driven mass local user creation and management.

Tested with:
- Ubuntu
- Debian
- Centos


Variables:
##`users.yml` 
`users ` List of dictionaries
`sudoers ` List of users to add sudoers
`rewoke_sudoers ` List of users to remove from sudoers
Example:  
###Add user
```yaml
users:  
  - name: captain
    state: present #optional
    shell: /bin/bash #optional 
    password: password123  #optional
    group: captain #optional
    groups:   #optional with auto append
      - sudo
      - admin
    pubkeys: "ssh-rsa xxxxxxxxxxxxxxxB capt@host
      ssh-ed25519 xcvbn12345 capt@host2"

sudoers:
  - captain

rewoke_sudoers: []

```
###Remove user:
```yaml
users:  
  - name: captain
    state: absent
    remove_homedir: yes

sudoers: []

rewoke_sudoers: 
  - captain

```


