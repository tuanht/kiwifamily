FROM ruby:2.7.2-alpine

RUN apk add --update git
RUN git clone https://github.com/tootsuite/mastodon.git /live
RUN git -C /live checkout v3.3.0

RUN apk add coreutils imagemagick ffmpeg libpq libxml2 libxslt \
  file libprotobuf protobuf nodejs autoconf make gcc g++ libgcc libstdc++ \
  bison

RUN gem install bundler --no-document
RUN cd /live \
  && bundle config deployment 'true' \
  && bundle config without 'development test'

WORKDIR /live
