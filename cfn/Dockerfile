FROM jruby:9.0.4

MAINTAINER "Aaron Walker" <a.walker@base2services.com>

VOLUME ["/build"]
WORKDIR /build

ADD Gemfile /opt/cfndsl/Gemfile

RUN rm /bin/sh && ln -s /bin/bash /bin/sh \
  && cd /opt/cfndsl \
  && bundle install

ADD run.sh /usr/local/bin/run.sh
ADD bin/ /opt/cfn/bin
ADD lib/ /opt/cfn/lib

ENTRYPOINT ["/usr/local/bin/run.sh"]
CMD ["help"]
