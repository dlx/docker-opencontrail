FROM muccg/openstackbase:kilo
MAINTAINER https://github.com/muccg/

RUN apt-get -qqy update && apt-get install -y --no-install-recommends \
  mysql-client \
  keystone \
  python-keystoneclient \
  python-memcache \
  python-mysqldb \
  && apt-get clean && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

COPY entrypoint.sh /

ENTRYPOINT ["/entrypoint.sh"]
LABEL net.juniper.contrail=common
LABEL net.juniper.openstack=common
LABEL net.juniper.node=controller
CMD ["/usr/bin/python","/usr/bin/keystone-all"]
