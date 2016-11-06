# Jenkins
FROM ubuntu:14.04
MAINTAINER jacky_cser@163.com
ENV REFRESHED_AT 2016-11-06

RUN apt-get update -yqq && apt-get install -yqq curl apt-transport -https
RUN apt-key adv --keyserver hkp://p80.pool.sks-keyserver.net:80 --recv-keys /
    58118E89F3A912897C070ADBF76221572C52609D
RUN echo deb https://apt.dockerproject.org/repo ubuntu-trusty main > /etc/apt/sources.list.d/docker.list
RUN apt-get update -qq && apt-get install -yqq iptables cacertificates openjdk-7-jdk git-core docker-engine

ENV JENKINS_HOME /opt/jenkins/data
ENV JENKINS_MIRROR http://mirrors.jenkins-ci.org

RUN mkdir -p $JENKINS_HOME/plugins
RUN curl -sf -o /opt/jenkins/jenkins.war -L $JENKINS_MIRROR/warstable/lastest/jenkins.war

RUN for plugin in chucknorris greenballs scm-api git-client git
    ws-cleanup ;\
        do curl -sf -o $JENKINS_HOME/plugins/${plugin}.hpi
        ; done
ADD ./dockerjenkins.sh /usr/local/bin/dockerjenkins.sh
RUN chomod +x /usr/local/bin/dockerjenkins.sh

VOLUME /var/lib/docker

EXPOSE 8080

ENTRYPOINT [ "/usr/local/bin/dockerjenkins.sh" ]

