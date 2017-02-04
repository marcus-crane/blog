# If you have OpenSSL installed, we recommend updating
# the following line to use "https"
source 'https://rubygems.org'

require 'json'
require 'open-uri'
versions = JSON.parse(open('https://pages.github.com/versions.json').read)

group :development do
  gem 'html-proofer'
  gem 'jekyll'
  gem 'jekyll-paginate'
  gem 'sass'
  gem 'bourbon'
  gem 'pygments.rb'
end

gem 'github-pages', versions['github-pages']