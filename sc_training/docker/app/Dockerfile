FROM ruby:2.7.1 as ruby
RUN apt-get update && \
    apt-get install -y nodejs default-mysql-client
RUN mkdir /sc_training
WORKDIR /sc_training
COPY Gemfile /sc_training/Gemfile
COPY Gemfile.lock /sc_training/Gemfile.lock
RUN bundle install
COPY . /sc_training

# Add a script to be executed every time the container starts.
COPY ./docker/app/entrypoint.sh /usr/bin/
RUN chmod +x /usr/bin/entrypoint.sh
ENTRYPOINT ["entrypoint.sh"]
EXPOSE 3001

# Start the main process.
CMD ["rails", "server", "-b", "0.0.0.0"]