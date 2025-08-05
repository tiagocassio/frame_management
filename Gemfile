source 'https://rubygems.org'


gem 'rails', '~> 8.0.2' # Bundle edge Rails instead: gem "rails", github: "rails/rails", branch: "main"
gem 'pg', '~> 1.1' # Use postgresql as the database for Active Record
gem 'puma', '>= 5.0' # Use the Puma web server [https://github.com/puma/puma]
gem 'jbuilder' # Build JSON APIs with ease [https://github.com/rails/jbuilder]
gem 'bcrypt', '~> 3.1.7' # Use Active Model has_secure_password [https://guides.rubyonrails.org/active_model_basics.html#securepassword]
gem 'tzinfo-data', platforms: %i[ windows jruby ] # Windows does not include zoneinfo files, so bundle the tzinfo-data gem
gem 'solid_cache' # Use the database-backed adapters for Rails.cache, Active Job, and Action Cable
gem 'solid_queue' # Use the database-backed adapters for Rails.cache, Active Job, and Action Cable
gem 'solid_cable' # Use the database-backed adapters for Rails.cache, Active Job, and Action Cable
gem 'bootsnap', require: false # Reduces boot times through caching; required in config/boot.rb
gem 'kamal', require: false # Deploy this application anywhere as a Docker container [https://kamal-deploy.org]
gem 'thruster', require: false # Add HTTP asset caching/compression and X-Sendfile acceleration to Puma [https://github.com/basecamp/thruster/]
gem 'rack-cors' # Use Rack CORS for handling Cross-Origin Resource Sharing (CORS), making cross-origin Ajax possible
gem 'rswag-api' # Rswag extends rspec-rails "request specs" with a Swagger-based DSL for describing and testing API operations.
gem 'rswag-ui' # Rswag extends rspec-rails "request specs" with a Swagger-based DSL for describing and testing API operations.
gem 'rails-i18n', '~> 8.0.0' # Centralization of locale data collection for Ruby on Rails. See [https://github.com/svenfuchs/rails-i18n]
gem 'ruby-units' # The 'Ruby units' gem is designed to simplify the handling of units for scientific calculations. See [https://github.com/olbrich/ruby-units]

group :development, :test do
  gem 'rspec-rails' # rspec-rails brings the RSpec testing framework to Ruby on Rails as a drop-in alternative to its default testing framework, Minitest. See [https://github.com/rspec/rspec-rails]
  gem 'factory_bot_rails' # Check this out! [https://github.com/thoughtbot/factory_bot]
  gem 'faker' # Faker is a port of Perl's Data::Faker library. It's a library for generating fake data such as names, addresses, and phone numbers. See [https://github.com/faker-ruby/faker]
  gem 'debug', platforms: %i[ mri windows ], require: 'debug/prelude' # See https://guides.rubyonrails.org/debugging_rails_applications.html#debugging-with-the-debug-gem
  gem 'brakeman', require: false # Static analysis for security vulnerabilities [https://brakemanscanner.org/]
  gem 'rubocop-rails-omakase', require: false # Omakase Ruby styling [https://github.com/rails/rubocop-rails-omakase/]
  gem 'rswag-specs' # Rswag extends rspec-rails "request specs" with a Swagger-based DSL for describing and testing API operations.
end

group :test do
  gem 'database_cleaner-active_record' # Database Cleaner is a set of gems containing strategies for cleaning your database in Ruby. See [https://github.com/DatabaseCleaner/database_cleaner]
  gem 'shoulda-matchers' # Shoulda Matchers provides RSpec and Minitest-compatible one-liners to test common Rails functionality that, if written by hand, would be much longer, more complex, and error-prone. See [https://github.com/thoughtbot/shoulda-matchers]
  gem 'simplecov', require: false # SimpleCov is a code coverage analysis tool for Ruby [https://github.com/simplecov-ruby/simplecov]
end
