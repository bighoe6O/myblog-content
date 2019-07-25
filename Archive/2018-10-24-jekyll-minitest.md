Title:  Jekyll Minitest
Date:   2018-10-24 09:18:41 +0200
Category: Dev
Tags: Jekyll, TDD

## Liens

<https://dev.to/phansch/testing-your-jekyll-website-with-capybara>

<https://github.com/teamcapybara/capybara/blob/3.9_stable/README.md>


## Example

[Using minitest to regression-test your Jekyll static site](https://gist.github.com/thbar/10be2ea924b81f78d24ab800461bfee3)

```ruby
# Gemfile
source 'https://rubygems.org'

gem 'jekyll', '3.3.1'

group :test do
  gem 'capybara'
  gem 'rack'
  gem 'rack-jekyll'
  gem 'rake'
end
```

```ruby
# test/test_helper.rb
require 'minitest/autorun'

require 'bundler/setup'
require 'capybara/dsl'
require 'rack/jekyll'

Capybara.app = Rack::Jekyll.new(force_build: true)

class CapybaraTestCase < MiniTest::Test
  include Capybara::DSL

  def teardown
    Capybara.reset_sessions!
    Capybara.use_default_driver
  end
end
```

```ruby
# _plugins/tests.rb: permet d'executer les tests au build
Jekyll::Hooks.register :site, :post_write do |site|
  # NOTE: you may want to raise conditionally here to stop the deploy
  system("bundle exec ruby tests.rb")
end
```

```ruby
# test/features/this_blog_post_test.rb
require 'test_helper'

class ThisBlogPostTest < CapybaraTestCase
  def test_describes_how_to_write_tests
    visit '2017/03/02/testing-jekyll-websites/'
    assert page.has_content?('configured we can now start '\
      'writing Capybara tests as usual:')
  end
end
```
