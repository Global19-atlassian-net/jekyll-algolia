# encoding: utf-8

require 'rubygems'
require 'bundler'
begin
  Bundler.setup(:default, :development)
rescue Bundler::BundlerError => e
  $stderr.puts e.message
  $stderr.puts 'Run `bundle install` to install missing gems'
  exit e.status_code
end
require 'rake'

require 'jeweler'
require_relative 'lib/version'
Jeweler::Tasks.new do |gem|
  # gem is a Gem::Specification... see
  # http://guides.rubygems.org/specification-reference/ for more options
  gem.name = 'algoliasearch-jekyll'
  gem.version = AlgoliaSearchJekyllVersion.to_s
  gem.homepage = 'https://github.com/algolia/algoliasearch-jekyll'
  gem.license = 'MIT'
  gem.summary = 'AlgoliaSearch for Jekyll'
  gem.description = 'Index all your pages and posts to an Algolia index with ' \
                    '`jekyll algolia push`'
  gem.email = 'tim@pixelastic.com'
  gem.authors = ['Tim Carry']

  # dependencies defined in Gemfile
end
Jeweler::RubygemsDotOrgTasks.new

require 'rspec/core'
require 'rspec/core/rake_task'
RSpec::Core::RakeTask.new(:spec) do |spec|
  spec.rspec_opts = '--color --format documentation'
  spec.pattern = FileList['spec/**/*_spec.rb']
end
task test: :spec

desc 'Code coverage detail'
task :coverage do
  ENV['COVERAGE'] = 'true'
  Rake::Task['spec'].execute
end

task default: :test
