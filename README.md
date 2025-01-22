# Ansible role - user-access-windows

This role was specially designed for sandbox. It sets user-access public
SSH key as authorized key and optionally sets password to a user.

## Requirements

* This role requires root access, so you either need to specify `become` directive as a global or while invoking the role.

    ```yml
    become: yes
    ```

## Role parameters

Optional parameters.

* `user_access_username` - The name of the user to give SSH access to (default: `user-access`).
* `user_access_password` - The password of user `user_access_password` (omitted by default).
* `user_access_ssh_public_key` - The path on Ansible controller to SSH public key that will be set as authorized_key.
Currently, only one key can be set as authorized_key. (default: `global_ssh_public_user_key`).
* `user_access_admin` - A boolean value representing whether the user should have admin privileges (default: `False`).
* `user_access_rdp` - A boolean value representing whether the target system should enable RDP access (default: `True`).

## Example

The simplest example.

```yml
roles:
    - role: user-access-windows
```
