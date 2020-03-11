# brewmaster-backend

[![Build Status](https://travis-ci.org/brewmajsters/ansible-role-brewmaster-backend.svg?branch=master)](https://travis-ci.org/brewmajsters/ansible-role-brewmaster-backend)

Download and install brewmajsters/brewmaster-backend with setup systemd service for flask server.

## Requirements

setup TimescaleDB instance accessible on 5432/tcp
- [ansible-role-timescaledb](https://github.com/brewmajsters/ansible-role-timescaledb)

## Role Variables

Refer to the [default variables](defaults/main.yml).

    repo:
      dest: <str, absolute or relative path of github repo destination directory>
      version: <str, branch name or commit to clone>
    develop: <bool, if false (default) the application is install with '--deploy --system' flags>
    backend_service:
      name: <str, systemd service name>
    backend_environments: <dict, environment variables to be modified in '.env' file>

## Dependencies

None

## Example Playbook

    - hosts: servers
      roles: ansible-role-brewmaster-backend
        vars:
          repo:
            dest: realtive/path/to/dest
          develop: true
          backend_environments:
            DATABASE_HOST: 192.168.127.22

## License

None

## Author Information

Tomas Bellus
