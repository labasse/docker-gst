# docker-gst
Base image for gstreamer application

## Tags
- Alpine: `alpine-dev`, `alpine-build`, `alpine-run`
- Ubuntu: `ubuntu-build`, `ubuntu-run`

## Editions
- `dev` with gcc, libc, make, cmake and pkgconf for build; boost, ggtest and gstreamer as libraries; rsync, ssh and gdb for debug 
- `build` same as dev without debugging tools
- `run` gstreamer and boost libraries only.

## For `alpine-dev` only

Environment variables are inherited from the base image, see [hermsi/alpine-sshd](https://hub.docker.com/r/hermsi/alpine-sshd).

The exposed port is 22 for ssh 

Example of use:
```
docker run -d --rm -p 2222:22 -e ROOT_PASSWORD=sshpassword --security-opt seccomp:unconfined labasse/dev-gst
```
The option `--security-opt seccomp:unconfined` avoid troubles with gdb remote debugging.