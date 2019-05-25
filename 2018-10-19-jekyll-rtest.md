---
layout: post
title:  Jekyll RTest
date:   2018-10-19 16:34:17 +0200
category: Dev
tags: Jekyll, TDD
---

## Rspec

<https://medium.com/espark-engineering-blog/testing-your-jekyll-site-the-ruby-way-ccfa386a8318>

<http://chromedriver.storage.googleapis.com/2.9/chromedriver_win32.zip>

# Examples

## Rspec

```ruby
# Gemfile
source "https://rubygems.org"

gem "jekyll", "~> 3.8.4"

gem "minima", "~> 2.0"

# If you have any plugins, put them here!
group :jekyll_plugins do
  gem "jekyll-feed", "~> 0.6"
end

# Windows does not include zoneinfo files, so bundle the tzinfo-data gem
gem "tzinfo-data", platforms: [:mingw, :mswin, :x64_mingw, :jruby]

# Performance-booster for watching directories on Windows
gem "wdm", "~> 0.1.0" if Gem.win_platform?

group :development, :test do
  gem "rspec"
  gem "selenium-webdriver"
  gem "chromedriver-helper"
  # Ajout de puma (server
  # Failures:

  # 1) sample has the page title
  #    Failure/Error: raise LoadError, 'Capybara is unable to load `puma` for its server, please add `puma` to your project or specify a different server via something like `Capybara.server = :webrick`.'
  gem "puma"
  gem "capybara"
  gem "rack-jekyll"
  gem "pry"
end
```

```ruby
# spec/spec_helper.rb
# Require all of the necessary gems
require 'rspec'
require 'capybara/rspec'
require 'rack/jekyll'
require 'rack/test'
require 'pry'

RSpec.configure do |config|
  config.expect_with :rspec do |expectations|
    expectations.include_chain_clauses_in_custom_matcher_descriptions = true
  end

  config.mock_with :rspec do |mocks|
    mocks.verify_partial_doubles = true
  end

  # Configure Capybara to use Selenium.
  Capybara.register_driver :selenium do |app|
    # Configure selenium to use Chrome.
    Capybara::Selenium::Driver.new(app, :browser => :chrome)
  end

  # Configure Capybara to load the website through rack-jekyll.
  # (force_build: true) builds the site before the tests are run,
  # so our tests are always running against the latest version
  # of our jekyll site.
  Capybara.app = Rack::Jekyll.new(force_build: true)
end
```

```ruby
# Rakefile
task :default => :rspec

task :install do
  sh "bundle install --path ../vendor/bundle"
end

task :update do
  sh "bundle update"
end

task :rspec do
  sh "bundle exec rspec"
end
```
