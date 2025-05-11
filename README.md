# Run Ansible playbook GitHub Action

An Action that executes given Ansible playbook on selected hosts.

Should work on any OS, if `ansible-playbook` command is available in `PATH`.

## Usage

```yaml
- name: Run playbook
  uses: 21JumpClick/ansible-playbook@1.0.1
  with:
    # Required, playbook filepath
    playbook: deploy.yml
    # Optional, directory where playbooks live
    directory: ./
    # Optional, SSH private key
    key: ${{secrets.SSH_PRIVATE_KEY}}
    # Optional, inventory file
    inventory_file: .ansible/inventory
    # Optional, literal inventory file contents
    inventory: |
      [all]
      example.com

      [group1]
      example.com
    # Optional, SSH known hosts file content
    known_hosts: .known_hosts
    # Optional, encrypted vault password
    vault_password: ${{secrets.VAULT_PASSWORD}}
    # Optional, galaxy requirements filepath
    requirements: galaxy-requirements.yml
    # Optional, additional flags to pass to ansible-playbook
    options: |
      --inventory .hosts
      --limit group1
      --extra-vars hello=there
      --verbose
```
