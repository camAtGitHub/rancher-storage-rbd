FROM ceph/ceph:v12
COPY storage common/* rbd/rancher-rbd /usr/bin/
CMD ["start.sh", "storage", "--driver-name", "rancher-rbd"]
