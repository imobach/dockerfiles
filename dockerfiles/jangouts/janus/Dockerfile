# janus
#
# VERSION               0.0.1
#
# Janus Gateway server
#
# Example: docker run --rm --name janus0 -v `pwd`/data:/var/lib/jenkins -p 8000:22 jangouts/janus

FROM opensuse:tumbleweed
MAINTAINER Imobach González Sosa <igonzalezsosa@suse.com>

RUN zypper ar -f --no-gpgcheck -r http://download.opensuse.org/repositories/home:/mlin7442:/hackweek11/openSUSE_13.2/home:mlin7442:hackweek11.repo
RUN zypper -n in janus-gateway


RUN mkdir /etc/janus/certs
RUN openssl req -x509 -sha256 -nodes -days 365 -newkey rsa:2048 -keyout /etc/janus/certs/mycert.key \
    -out /etc/janus/certs/mycert.pem -subj "/C=DE/ST=/L=/O=/CN=jangouts.local"

COPY janus.cfg /etc/janus/janus.cfg
RUN chown root:janus /etc/janus/janus.cfg
RUN chmod 0640 /etc/janus/janus.cfg

VOLUME ["/etc/janus"]
EXPOSE 7088
EXPOSE 8088
EXPOSE 8188
EXPOSE 8989
CMD ["janus"]
