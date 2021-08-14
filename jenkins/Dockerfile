FROM jenkins/jenkins:latest

ENV JAVA_OPTS -Djenkins.install.runSetupWizard=fals
ENV CONFIG_JENKINS_CONFIG /var/jenkins_home/config.yaml

COPY plugins.txt /usr/share/jenkins/ref/plugins.txt
RUN /usr/local/bin/install-plugins.sh < /usr/share/jenkins/ref/plugins.txt
COPY config.yaml /var/jenkins_home/config.yaml
