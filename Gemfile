source "https://rubygems.org"

# gem "github-pages"
#
# Issue: github-pages Gem doesn't work with Ruby 3!
# This Gemfile should include the line commented out above.
# The lines below are added as a work around for Ruby 3.
# If you are doing serious customization and need to keep in sync with github-pages versions,
# Please use Ruby 2.7x,
# uncomment gem "github-pages" 
# and delete the lines below.


# frozen_string_literal: true

source 'https://rubygems.org'

# needed for Jekyll
gem 'jekyll'
gem 'webrick'
gem 'logger'
gem 'base64'
gem 'ostruct'
gem 'jekyll-toc'

# needed for Rake tasks
gem 'rake'
gem 'csv'
gem 'fileutils'
gem 'mini_magick'
unless Gem.win_platform?
  gem 'image_optim'
  gem 'image_optim_pack'
end