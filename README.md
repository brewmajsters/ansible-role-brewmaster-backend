# brewmaster-backend

[![Build Status](https://travis-ci.org/brewmajsters/ansible-role-brewmaster-backend.svg?branch=master)](https://travis-ci.org/brewmajsters/ansible-role-brewmaster-backend)

Setup the environment for docker containers and install the TimescaleDB database in a docker container. Download and install brewmajsters/brewmaster-backend with setup systemd service for flask server.

## Requirements

None

## Role Variables

Refer to the [default variables](defaults/main.yml).

    repo:
      dest: <str, absolute or relative path of github repo destination directory>
      version: <str, branch name or commit to clone>
    develop: <bool, if false (default) the application is install with '--deploy --system' flags>
    backend_service:
      name: <str, systemd service name>
    timescaledb_docker:
      name: <str, docker image name>
      image: <str, timescaledb docker image[:tag]>
      volumes: <list, volumes to mount to the docker container>
      privileged: <bool, give extended privileges to the container>
      ports: <str, port mapping>
      env: <dict, docker container custom environments>


## Dependencies

None

## Example Playbook

    - hosts: servers
      roles: ansible-role-brewmaster-backend
        vars:
          repo:
            dest: realtive/path/to/dest
          develop: true

## License

None

## Author Information

Tomas Bellus
