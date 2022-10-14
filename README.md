# AllCom Alpine User Setup

Setup Alpine user

## Requirements

It should work on any latest alpine distribution

## Role Variables

| Variable                                  | Required | Default | Choices | Comments                   |
| ----------------------------------------- | -------- | ------- | ------- | -------------------------- |
| allcom_alpine_user\_\_username            | no       | allcom  |         | username                   |
| allcom_alpine_user\_\_authorized_keys     | yes      |         |         | authorized keys file       |
| allcom_alpine_user\_\_git_ssh_key_public  | yes      |         |         | git server public ssh key  |
| allcom_alpine_user\_\_git_ssh_key_private | yes      |         |         | git server private ssh key |
| allcom_alpine_user\_\_registry_server_key | yes      |         |         | registry server json key   |

## Dependencies

- eliseuvideira.allcom_alpine

## Example Playbook

    - hosts: alpine_servers
      roles:
        - role: eliseuvideira.allcom_alpine_user
          allcom_alpine_user__username: allcom
          allcom_alpine_user__authorized_keys: |
            ssh-ed25519 ...
            ssh-ed25519 ...
            ssh-ed25519 ...
            ssh-ed25519 ...
          allcom_alpine_user__git_ssh_key_public: |
            ssh-ed25519 ...
          allcom_alpine_user__git_ssh_key_private: |
            -----BEGIN OPENSSH PRIVATE KEY-----
            ...
            ...
            -----END OPENSSH PRIVATE KEY-----
          allcom_alpine_user__registry_server_key: |
            {
              "auths": {
                "registry.server.com": {
                  "auth": "..."
                }
              }
            }

## License

MIT
