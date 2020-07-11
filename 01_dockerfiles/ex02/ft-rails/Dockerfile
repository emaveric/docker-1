FROM ruby

RUN apt-get update && apt-get upgrade -y

RUN apt-get install -y nodejs sqlite3

RUN gem update && gem install bundler rails

ONBUILD COPY app /opt/app

ONBUILD WORKDIR /opt/app

ONBUILD EXPOSE 3000

ONBUILD RUN gem install bundler:1.17.2

ONBUILD RUN gem install bundler:2.1.2

ONBUILD RUN bundle install

ONBUILD RUN rake db:migrate

ONBUILD RUN rake db:seed
