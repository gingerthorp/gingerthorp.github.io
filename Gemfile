source "https://rubygems.org"

gem "jekyll", ">= 4.2.0", "< 5.0"
gem 'nokogiri', '~> 1.11.0.rc4'

# plugins
group :jekyll_plugins do
  gem "jekyll-paginate"
  gem "jekyll-redirect-from", ">= 0.16.0"
  gem "jekyll-seo-tag", ">= 2.7.1"
  gem "jekyll-archives", ">= 2.2.1"
  gem "jekyll-sitemap", ">= 1.4.0"
end

group :test do
  gem "html-proofer", ">= 3.18.3"
end

# Windows and JRuby does not include zoneinfo files, so bundle the tzinfo-data gem
# and associated library.
install_if -> { RUBY_PLATFORM =~ %r!mingw|mswin|java! } do
  gem "tzinfo", "~> 1.2"
  gem "tzinfo-data"
end

# Performance-booster for watching directories on Windows
gem "wdm", "~> 0.1.1", :install_if => Gem.win_platform?
