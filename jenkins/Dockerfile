# Jenkins LTS + client Docker + plugins minimaux, sans assistant de démarrage (pour le TP).
FROM jenkins/jenkins:lts-jdk21
USER root
RUN apt-get update \
 && apt-get install -y --no-install-recommends docker.io \
 && rm -rf /var/lib/apt/lists/*
USER jenkins
ENV JAVA_OPTS="-Djenkins.install.runSetupWizard=false"
RUN jenkins-plugin-cli --plugins workflow-aggregator git docker-workflow configuration-as-code job-dsl
