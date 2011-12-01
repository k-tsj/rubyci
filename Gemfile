source 'http://rubygems.org'

gem 'rails', '3.1.1'

# Bundle edge Rails instead:
# gem 'rails',     :git => 'git://github.com/rails/rails.git'

# Gems used only for assets and not required
# in production environments by default.
group :assets do
  gem 'sass-rails', "  ~> 3.1.0"
  gem 'coffee-rails', "~> 3.1.0"
  gem 'uglifier'
end

gem 'jquery-rails'
gem 'execjs'
gem 'thin'

# Use unicorn as the web server
# gem 'unicorn'

# Deploy with Capistrano
# gem 'capistrano'

# To use debugger
# gem 'ruby-debug19', :require => 'ruby-debug'

hostname = `hostname`

group :test do
  # Pretty printed test output
  gem 'turn', :require => false
end

group :development do
  gem 'sqlite3' unless /mgk-/ =~ hostname
#  gem "mustang"
  gem "therubyracer"
end

group :production do
  case hostname
  when /mgk-/ # mogok
    gem "therubyracer"
    gem 'mysql2'
  else # :heroku
    p [:hostname, `hostname`]
    gem 'therubyracer-heroku'
    gem 'pg'
    gem 'newrelic_rpm'
  end
end
