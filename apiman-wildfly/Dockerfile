FROM jboss/wildfly
MAINTAINER Jorge Morales <jmorales@redhat.com>

ENV APIMAN_VERSION 1.2.2.Final

RUN cd $JBOSS_HOME \
 && curl http://downloads.jboss.org/overlord/apiman/$APIMAN_VERSION/apiman-distro-wildfly10-$APIMAN_VERSION-overlay.zip -o apiman-distro-wildfly10-$APIMAN_VERSION-overlay.zip \
 && bsdtar -xf apiman-distro-wildfly10-$APIMAN_VERSION-overlay.zip \
 && rm apiman-distro-wildfly10-$APIMAN_VERSION-overlay.zip

RUN /opt/jboss/wildfly/bin/add-user.sh admin admin1234 --silent
CMD ["/opt/jboss/wildfly/bin/standalone.sh", "-b", "0.0.0.0", "-bmanagement", "0.0.0.0", "-c", "standalone-apiman.xml"]


