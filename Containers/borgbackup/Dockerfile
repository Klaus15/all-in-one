FROM debian:bullseye-20221004-slim

RUN set -ex; \
    \
    apt-get update; \
    apt-get install -y --no-install-recommends \
        borgbackup \
        rsync \
        fuse \
        python3-llfuse \
        jq \
    ; \
    rm -rf /var/lib/apt/lists/*

VOLUME /root

COPY start.sh /usr/bin/
COPY backupscript.sh /
RUN chmod +x /usr/bin/start.sh; \
    chmod +x /backupscript.sh

USER root
ENTRYPOINT ["start.sh"]