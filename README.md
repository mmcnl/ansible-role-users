## Example Playbook

    - hosts: all
      tasks:
      - import_role:
          name: mmcnl.users
        vars:
          root_console_password: sample_password
          root_console_password_salt: sample_salt
          users:
            - username: remote-backup
              extra_groups:
              pub_keys:
                - ssh-rsa AAAAA
            - username: matt
              extra_groups: www-data
              dotfiles:
                - path: ".config/bat/config"
                  content: |
                    --map-syntax conf:ini
                    --map-syntax cnf:ini
                    --theme TwoDark
                - path: ".bash_aliases"
                  content: |
                    alias gl="git log"
                    alias gs="git status"
              pub_keys:
                - ssh-rsa AAAA

## License

MIT

