# docker-gst
Base image for gstreamer application

## Tags
- Alpine: `alpine-dev`, `alpine-build`, `alpine-run`
- Ubuntu: `ubuntu-build`, `ubuntu-run`

## Editions
- `dev` with gcc, libc, make, cmake and pkgconf for build; boost (static) and gstreamer as libraries; rsync, ssh and gdb for debug 
- `build` same as dev without debugging tools
- `run` gstreamer and libraries only.

## For `alpine-dev` only

The exposed port is 22 for ssh 

Example of use:
```
docker run -d -p 2020:22 --security-opt seccomp:unconfined labasse/gst:alpine-dev
```
The option `--security-opt seccomp:unconfined` avoid troubles with gdb remote debugging.