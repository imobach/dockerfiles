# jenkins-slave
#
# VERSION               0.0.1
#
# Jenkins slave to be used through SSH.
#
# Example: docker run --rm --name slave0 -v `pwd`/data:/var/lib/jenkins -p 8000:22 jenkins-slave

FROM opensuse:tumbleweed
MAINTAINER Imobach González Sosa <igonzalezsosa@suse.com>

RUN zypper -n in openssh java-1_8_0-openjdk-headless
RUN mkdir /var/run/sshd
RUN echo 'root:linux123' | chpasswd

# Jenkins user
RUN useradd -m jenkins
RUN mkdir /var/lib/jenkins
RUN echo 'root:linux123' | chpasswd
RUN chown jenkins /var/lib/jenkins

# SSH
COPY run-sshd /usr/local/sbin/run-sshd
RUN chmod +x /usr/local/sbin/run-sshd

VOLUME ["/home/jenkins", "/var/lib/jenkins"]
EXPOSE 22
CMD ["/usr/local/sbin/run-sshd"]
