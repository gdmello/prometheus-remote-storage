FROM busybox:1.27-1:glibc

COPY remote_storage_adapter /

RUN chmod 755 /remote_storage_adapter

ENTRYPOINT ["./remote_storage_adapter"]
