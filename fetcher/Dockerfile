# fetcher
FROM ubuntu:14.04
MAINTAINER Jacky <jacky_cser@163.com>
ENV REFRESHED_AT 2016-11-01

RUN apt-get -yqq update
RUN apt-get -yqq install wget

VOLUME [ "/var/lib/tomcat7/webapps" ]
WORKDIR /var/lib/tomcat7/webapps/

ENTRYPOINT [ "wget" ]
CMD [ "-?" ]

