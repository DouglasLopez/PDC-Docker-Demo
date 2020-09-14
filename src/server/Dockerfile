FROM ruby:2.5
RUN apt-get update -qq && apt-get install -y nodejs
RUN mkdir /server
WORKDIR /server
COPY Gemfile /server/Gemfile
COPY Gemfile.lock /server/Gemfile.lock
RUN gem install bundler
RUN bundle install
EXPOSE 3000
RUN cd /server
ENTRYPOINT ["rails", "server", "-b", "0.0.0.0"]