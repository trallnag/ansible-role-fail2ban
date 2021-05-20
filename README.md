[![role](https://img.shields.io/ansible/role/54870)](https://galaxy.ansible.com/trallnag/fail2ban)
[![quality](https://img.shields.io/ansible/quality/54870)](https://galaxy.ansible.com/trallnag/fail2ban)
[![downloads](https://img.shields.io/ansible/role/d/54870?label=downloads)](https://galaxy.ansible.com/trallnag/fail2ban)

# Endlessh

Install fail2ban and configure it with arbitrary configuration.

Available on [Ansible Galaxy](https://galaxy.ansible.com/trallnag/fail2ban).

## Role Variables

```yaml
# Fail2ban has a quit extensive configuration. Therefore you can simply copy
# arbitrary files to the target host.
# 
# Important: The files on the target host will be overwritten if they already exist.
# In addition you can use Jinja2 syntax in the config files because every file
# is handled by Ansible template module.
fail2ban_config_files: []
# - src: "{{ playbook_dir }}/files/fail2ban/jail.local"
#   dest: /etc/fail2ban/jail.local
# - src: "{{ playbook_dir }}/files/fail2ban/action.d/route.conf"
#   dest: /etc/fail2ban/action.d/route.conf
```

## Example Playbook

```yaml
- name: Playbook
  hosts: myhost
  remote_user: myuser
  roles:
    - name: trallnag.fail2ban
      vars:
        fail2ban_config_files:
          - src: "{{ playbook_dir }}/files/fail2ban/jail.local"
            dest: /etc/fail2ban/jail.local
          - src: "{{ playbook_dir }}/files/fail2ban/action.d/route.conf"
            dest: /etc/fail2ban/action.d/route.conf
```

## Special Requirements

* Systemd must be used.

## Special Dependencies

None.

## License

Apache-2.0

## Author Information

Trallnag
