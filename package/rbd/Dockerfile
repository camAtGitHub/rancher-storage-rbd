FROM ceph/ceph:v12
#RUN yum-config-manager --disable tcmu-runner-noarch; ls /etc/yum.repos.d
#RUN yum check-update && yum install jq -y
#RUN jq --help
COPY storage common/* rbd/rancher-rbd /usr/bin/
CMD ["start.sh", "storage", "--driver-name", "rancher-rbd"]
