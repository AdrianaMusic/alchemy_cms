source 'https://rubygems.org'

gemspec

if ENV['RAILS_VERSION']
  gem 'rails', ENV['RAILS_VERSION']
end

gem 'sqlite3' if ENV['DB'].nil? || ENV['DB'] == 'sqlite'
gem 'mysql2', '~> 0.3.18' if ENV['DB'] == 'mysql'
gem 'pg'      if ENV['DB'] == 'postgresql'

gem 'mime-types', '< 3' # otherwise we can't build for Ruby 1.9

group :development, :test do
  gem 'jasmine-rails',        github: 'searls/jasmine-rails'
  gem 'jasmine-jquery-rails', github: 'travisjeffery/jasmine-jquery-rails'
  if ENV['TRAVIS']
    gem 'coveralls',          require: false
  else
    gem 'simplecov',          require: false
  end
  unless ENV['CI']
    gem 'launchy'
    gem 'annotate'
    gem 'bumpy'
    gem 'yard'
    gem 'redcarpet'
    gem 'pry'
    gem 'spring'
    gem 'spring-commands-rspec'
  end
end

# We need this if we want to start the dummy app in production, ie on Teatro.io
group :production do
  gem 'uglifier', '>= 1.0.3'
  gem 'therubyracer'
end
