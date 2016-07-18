add-ssh-keys-from-github
========================

Given a list of GitHub usernames, this Ansible role downloads their SSH public
keys from GitHub and adds them to `~/.ssh/authorized_keys`.

DEPRECATED
----------

Ansible 1.9 and later supports importing SSH keys from a URL, which means you can import keys directly from GitHub like this:

```yaml
- authorized_key: >
    user={{ ansible_user_id }}
    key=https://github.com/{{ item }}.keys
  with_items:
    - alice
    - bob
    - carol
```


Requirements
------------

* `httplib2` - installed automatically via PIP

Role Variables
--------------

    add_ssh_keys_from_github:
      usernames:
        - alice
        - bob
        - carol

License
-------

BSD

Author Information
------------------

George Miroshnykov <george.miroshnykov@gmail.com>
