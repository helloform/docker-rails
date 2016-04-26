## Why does this exist?

This docker image is meant to be used as a base to a stable ruby on rails-based
development (or production) environment. It uses the latest Ubuntu LTS (16.04 at
the time of this writing), and includes common tools used by Ruby on Rails
developers.

## How to use

Use this image as a base for your docker-based Ruby on Rails projects. Here is
an example of a `Dockerfile` which uses this image:

```
# Setup the base image
FROM helloform/ruby:latest

# Configure the app folder
ENV APP_HOME /yourapp
RUN mkdir $APP_HOME
WORKDIR $APP_HOME

# Bundle, then add the rest of the project files
ADD Gemfile* $APP_HOME/
RUN bundle install
ADD . $APP_HOME
```

## Contributing

If you have anything to contribute to `helloform/rails`, feel free to send in a
pull request with your proposed changes. You can always get in touch with the
maintainer at @f (the single character `f`) on twitter. Thank you!
