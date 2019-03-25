FROM alpine

RUN apk update \
    && apk add --no-cache build-base cmake pkgconf boost-dev boost-static gstreamer-dev gst-plugins-base-dev gst-plugins-good-gtk gst-plugins-bad-dev rsync gdb openssh \
    && sed -i s/#PermitRootLogin.*/PermitRootLogin\ yes/ /etc/ssh/sshd_config \
    && echo "root:root" | chpasswd \
    && ssh-keygen -A

EXPOSE 22

ENTRYPOINT ["/usr/sbin/sshd", "-D"]
