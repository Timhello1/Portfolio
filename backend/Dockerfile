# Dockerfile

# Use an official Ruby runtime as a parent image
FROM ruby:3.2

# Install dependencies
RUN apt-get update -qq && apt-get install -y nodejs npm

# Set the working directory in the container
WORKDIR /app

# Copy the Gemfile and Gemfile.lock into the working directory
COPY Gemfile Gemfile.lock ./

# Install Rails gems
RUN gem install bundler && bundle install

# Copy the Rails application code into the container
COPY . .

# Expose port 3000 for the Rails server
EXPOSE 3000

# Set environment variables
ENV RAILS_ENV=development

# Run the Rails server
CMD ["rails", "server", "-b", "0.0.0.0"]
