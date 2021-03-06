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

  3. Create a couple of dummy Links
    * rails c
    * Link.create url: 'http://graphql.org/', description: 'The Best Query Language'
    * Link.create url: 'http://dev.apollodata.com/', description: 'Awesome GraphQL Client'
    * exit

  4. Crete a Query for returning Links
    * rails g graphql:object LinkType id:ID! url:String! description:String!

  5. Add into app/assets/config/manifest.js
    * //= link graphiql/rails/application.css
    * //= link graphiql/rails/application.js

  6. Add CreateLink file
    * Create file app/graphql/mutations/create_link.rb
    * Update app/graphql/types/mutation_type.rb to expose this mutation.
    * Add CreateLink test
    * bundle exec rails test

  7. Add Filters
    * gem 'search_object_graphql', '0.3.1'
    * bundle install
    * Add link search resolver
    * Edit links query types
