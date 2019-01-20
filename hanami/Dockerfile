FROM ruby:2.5-alpine
LABEL maintainer="Carlos Tiago N. Gomes <carlostiago88@gmail.com>"

ENV BUILD_PACKAGES bash curl-dev ruby-dev build-base
ENV RUBY_PACKAGES libxml2-dev libxslt-dev postgresql-dev postgresql libpq

RUN apk update && \
    apk upgrade && \
    apk add $BUILD_PACKAGES && \
    apk add $RUBY_PACKAGES && \
    gem install -N bundler && \
    rm -rf /var/cache/apk/*

WORKDIR /app
COPY . /app
RUN bundle install 
EXPOSE 2300
ENTRYPOINT ["bundle", "exec"]

