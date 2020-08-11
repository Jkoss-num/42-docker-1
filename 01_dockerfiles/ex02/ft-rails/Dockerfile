FROM ruby

MAINTAINER  otiffiny <otiffiny@student.21-school.ru>

RUN apt-get update -y && apt-get install -y build-essential libpq-dev nodejs sqlite3 gem
RUN gem install bundler:1.16.2 --no-document
RUN gem install rails --no-document
RUN gem install rake --no-document


ONBUILD COPY app /opt/app
ONBUILD WORKDIR /opt/app

ONBUILD EXPOSE 3000
ONBUILD RUn bundle update rake
ONBUILD RUN bundle install
ONBUILD RUN rake db:migrate
ONBUILD RUN rake db:seed



# cd ft-rails
# docker build -t ft-rails:on-build .
# cd ..
# docker build -t ex02 .
# docker run -it --rm -p 3000:3000 ex02

#ip:3000 in browser

# docker rm -f $(docker ps -a -q)