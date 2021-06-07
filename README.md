# README

This README would normally document whatever steps are necessary to get the
application up and running.

Things you may want to cover:

**Ruby version**
  * 2.6.5

**System dependencies**
  * gem 'graphql', '1.9.17'
  * gem 'graphiql-rails', '1.7.0', group: :development

**Database creation**
  * rails db:create

**Configuration**
  * bundle install
  * bundle exec rails generate graphql:install 

**How to run the test suite**
  * bundle exec rails test

## Steps
  1. Setup GraphQL 
    * Add gem 'graphql', '1.9.17'
    * bundle install
    * bundle exec rails generate graphql:install
    * Update Gemfile gem 'graphiql-rails', '1.7.0', group: :development
    * bundle install

  2. Generate the link database model (This generates a link.rb file in app/models)
    * bundle exec rails generate model Link url:string description:text
    * bundle exec rails db:migrate
