FROM almalinux:latest

ENV DEBIAN_FRONTEND=noninteractive

RUN yum -y update && \
    yum -y install sudo curl which iputils

COPY apps/almalinux/install.sh /install.sh
COPY apps/logo.sh /logo.sh
COPY apps/almalinux/install.sh /install.sh

RUN chmod +x /install.sh /logo.sh /test_lamp.sh

# Exécuter l'installation LAMP
RUN /install.sh --no-confirm

# Lancer le script de test (le build échoue si un test échoue)
RUN /install.sh

# Pour le mode interactif ou debug
CMD ["/usr/sbin/init"]