FROM        alpine:latest
MAINTAINER  Naner Nunes

ARG         USERNAME=samba
ARG         PASSWORD=samba

RUN         apk --no-cache add samba samba-common-tools
ADD         smb.conf /etc/samba/

RUN         addgroup ${USERNAME} && adduser -D -G ${USERNAME} ${USERNAME}
RUN         echo -e "${PASSWORD}\n${PASSWORD}" | smbpasswd -a -s ${USERNAME}

EXPOSE      138/udp 139 445

VOLUME      /samba

ENTRYPOINT  ["smbd"]
CMD         ["-F", "-S"]
