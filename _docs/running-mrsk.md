---
title: Running MRSK
order: 5
---

# Running MRSK from Docker

MRSK is packaged up in a Docker container similarly to [rails/docked](https://github.com/rails/docked). This will allow you to run MRSK (from your application directory) without having to install any dependencies other than Docker. Add the following alias to your profile configuration to make working with the container more convenient:

```bash
alias mrsk="docker run -it --rm -v '${PWD}:/workdir' -v '${SSH_AUTH_SOCK}:/ssh-agent' -v /var/run/docker.sock:/var/run/docker.sock -e 'SSH_AUTH_SOCK=/ssh-agent' ghcr.io/mrsked/mrsk:latest"
```

Since MRSK uses SSH to establish a remote connection, it will need access to your SSH agent. The above command uses a volume mount to make it available inside the container and configures the SSH agent inside the container to make use of it.
